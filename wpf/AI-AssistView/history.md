---
layout: post
title: Conversation history in WPF AI AssistView | Syncfusion®
description: Learn how to display, navigate, and manage multiple conversations using conversation history in the Syncfusion® WPF AI AssistView control.
platform: wpf
control: SfAIAssistView
documentation: ug
---

# Conversation history in WPF AI AssistView

The `SfAIAssistView` supports conversation history for creating new chats, preserving previous conversations, and switching between archived conversations through a built-in navigation view.

## Conversation history

The `Conversations` property stores the archived conversations displayed in the navigation view. Each conversation is represented by an `AssistConversationItem` that contains a title, start date and time, and a collection of messages.

### Define the view model

Create a view model with an `ObservableCollection<AssistConversationItem>` and populate each conversation with its associated messages.

{% tabs %}
{% highlight c# tabtitle="AIAssistViewModel.cs" %}

using System;
using System.Collections.ObjectModel;
using Syncfusion.UI.Xaml.Chat;

namespace AIAssistViewHistoryWPF
{
    public class AIAssistViewModel
    {
        public ObservableCollection<object> Chats { get; set; }

        public Author CurrentUser { get; set; }

        public ObservableCollection<AssistConversationItem> Conversations { get; set; }

        public AIAssistViewModel()
        {
            CurrentUser = new Author() { Name = "User" };
            Chats = new ObservableCollection<object>();

            Conversations = new ObservableCollection<AssistConversationItem>()
            {
                CreateConversation(
                    "Scotland",
                    "Tell me about Scotland.",
                    "Scotland is known for its historic castles, landscapes, and cultural heritage.",
                    DateTime.Now.AddHours(-2)),

                CreateConversation(
                    "Coding practices",
                    "What are some good coding practices?",
                    "Use code reviews, unit testing, clear naming, and consistent coding standards.",
                    DateTime.Now.AddHours(-1)),

                CreateConversation(
                    "Syncfusion",
                    "What does Syncfusion provide?",
                    "Syncfusion provides UI controls and components for .NET applications.",
                    DateTime.Now)
            };
        }

        private AssistConversationItem CreateConversation(
            string title,
            string requestText,
            string responseText,
            DateTime dateTime)
        {
            return new AssistConversationItem()
            {
                Title = title,
                DateTime = dateTime,
                AssistItems = new ObservableCollection<object>()
                {
                    new TextMessage()
                    {
                        Text = requestText,
                        DateTime = dateTime,
                        Author = CurrentUser
                    },
                    new TextMessage()
                    {
                        Text = responseText,
                        DateTime = dateTime.AddMinutes(1),
                        Author = new Author() { Name = "Syncfusion AI" }
                    }
                }
            };
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Bind conversations to SfAIAssistView

Set the window's data context and bind the `Conversations` property to display the archived conversations in the navigation view. Set `ShowNavigationView` to `True` because the navigation view is hidden by default.

{% tabs %}
{% highlight xaml tabtitle="MainWindow.xaml" hl_lines="18 19 20 21" %}

<Window
    x:Class="AIAssistViewHistoryWPF.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:AIAssistViewHistoryWPF"
    xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Chat;assembly=Syncfusion.SfChat.Wpf"
    Title="AI AssistView Conversation History"
    Width="1000"
    Height="700">

    <Window.DataContext>
        <local:AIAssistViewModel >
    </Window.DataContext>

    <Grid Margin="20">
        <syncfusion:SfAIAssistView
            x:Name="aiAssistView"
            Messages="{Binding Chats}"
            CurrentUser="{Binding CurrentUser}"
            Conversations="{Binding Conversations}"
            ShowNavigationView="True"
            NavigationHeader="Chat History" >
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

Selecting an archived conversation replaces the current messages with the messages stored in its `AssistItems` collection. The built-in **New Chat** option clears the current conversation and preserves a conversation that contains a request in the history.

![Conversation history in WPF AI AssistView](aiassistview_images\wpf_aiassistview_history.png)

## Show or hide the navigation view

The `ShowNavigationView` property controls the visibility of the conversation history navigation view. Its default value is `false`.

{% tabs %}
{% highlight xaml tabtitle="MainWindow.xaml" hl_lines="2" %}

<syncfusion:SfAIAssistView x:Name="aiAssistView"
                           ShowNavigationView="True" >

{% endhighlight %}
{% highlight c# tabtitle="MainWindow.xaml.cs" hl_lines="8" %}

using System.Windows;

namespace AIAssistViewHistoryWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            aiAssistView.ShowNavigationView = true;
        }
    }
}

{% endhighlight %}
{% endtabs %}

The built-in hamburger button collapses or expands the navigation view when it is visible.

## Customize the navigation header

The `NavigationHeader` property sets the text displayed at the top of the navigation view. Its default value is `string.Empty`.

{% tabs %}
{% highlight xaml tabtitle="MainWindow.xaml" hl_lines="2" %}

<syncfusion:SfAIAssistView x:Name="aiAssistView"
                           NavigationHeader="Chat History" >

{% endhighlight %}
{% highlight c# tabtitle="MainWindow.xaml.cs" hl_lines="8" %}

using System.Windows;

namespace AIAssistViewHistoryWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            aiAssistView.NavigationHeader = "Chat History";
        }
    }
}

{% endhighlight %}
{% endtabs %}
