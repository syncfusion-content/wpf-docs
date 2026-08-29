---
layout: post
title: Getting Started with WPF SfAIAssistView | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF SfAIAssistView control. Explore setup, features, examples, and customization options.
platform: wpf
control: AI AssistView
documentation: ug
---

# Getting Started with WPF SfAIAssistView

This section explains the steps required to add the WPF [SfAIAssistView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Chat.SfAIAssistView.html) control with its basic features.

## Structure of SfAIAssistView

The following diagram illustrates the layout of the SfAIAssistView control, including the header, message list, and input area.

![WPF SfAIAssistView Structure](aiassistview_images/wpf_aiassistview_control_structure.png)

## Adding WPF SfAIAssistView via XAML

1. Create a [Wpf desktop app for C# and .NET 6](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio?view=netdesktop-9.0).
2. Add reference to [Syncfusion.SfChat.Wpf](https://www.nuget.org/packages/Syncfusion.SfChat.Wpf) NuGet. 
3. Import the control namespace `Syncfusion.UI.Xaml.Chat` in XAML or C# code.
4. Initialize the [SfAIAssistView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Chat.SfAIAssistView.html) control.

{% tabs %}
{% highlight xaml %}

<Window
    x:Class="GettingStarted.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:GettingStarted"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Chat;assembly=Syncfusion.SfChat.Wpf"
    mc:Ignorable="d">
    <Grid x:Name="grid">
      <syncfusion:SfAIAssistView />
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## Adding WPF SfAIAssistview via C#

1. Create a [Wpf desktop app for C# and .NET 6](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio?view=netdesktop-9.0).
2. Add reference to [Syncfusion.SfChat.Wpf](https://www.nuget.org/packages/Syncfusion.SfChat.Wpf) NuGet. 
3. Import the control namespace `Syncfusion.UI.Xaml.Chat` in XAML or C# code.
4. Initialize the [SfAIAssistView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Chat.SfAIAssistView.html) control.

{% tabs %}
{% highlight C# %}

using Syncfusion.UI.Xaml.Chat;

namespace GettingStarted
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            this.InitializeComponent();
            // Creating an instance of the AIAssistView control
            SfAIAssistView assistView = new SfAIAssistView();
            grid.Children.Add(assistView);
        }
    }
}
           
{% endhighlight %}
{% endtabs %}


## Creating the ViewModel for the AI AssistView

Create a simple chat collection as shown in the following code example, and save it in a new class file named `ViewModel.cs`.

{% tabs %}
{% highlight C# %}

 public class ViewModel : INotifyPropertyChanged
 {
     private ObservableCollection<object> chats;
     private Author currentUser;
     public ViewModel()
     {
         this.Chats = new ObservableCollection<object>();          
         this.CurrentUser = new Author { Name="John"};
         this.GenerateMessages();
     }

     private async void GenerateMessages()
     {
         this.Chats.Add( new TextMessage { Author = CurrentUser, Text = "What is WPF?" } );        
         await Task.Delay(1000);
         this.Chats.Add( new TextMessage { Author = new Author { Name = "Bot" }, Text = "WPF is a user interface layer that contains modern controls and styles for building Windows apps." });
     }

     public ObservableCollection<object> Chats
     {
         get
         {
             return this.chats;
         }
         set
         {
             this.chats = value;
             RaisePropertyChanged("Messages");
         }
     }

     public Author CurrentUser
     {
         get
         {
             return this.currentUser;
         }
         set
         {
             this.currentUser = value;
             RaisePropertyChanged("CurrentUser");
         }
     }


     public void RaisePropertyChanged(string propName)
     {
         if (PropertyChanged != null)
         {
             PropertyChanged(this, new PropertyChangedEventArgs(propName));
         }
     }


     public event PropertyChangedEventHandler PropertyChanged;
  }

{% endhighlight %}
{% endtabs %}

## Binding Messages to the AI AssistView

Set the ViewModel as the `DataContext` for the AI AssistView or the parent window. This allows data binding between the UI and the ViewModel properties.
To populate the AI AssistView, bind the chats in the ViewModel to the `Messages` property of the AI AssistView.

{% tabs %}
{% highlight xaml %}

<Window
    x:Class="GettingStarted.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:GettingStarted"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Chat;assembly=Syncfusion.SfChat.Wpf"
    mc:Ignorable="d">
    <Grid x:Name="grid">
     <Grid.DataContext>
        <local:ViewModel/>
     </Grid.DataContext>
      <syncfusion:SfAIAssistView   CurrentUser="{Binding CurrentUser}"  
                                   Messages="{Binding Chats}"/>
    </Grid>
</Window>

{% endhighlight %} 
{% endtabs %}

![WPF AI AssistView control getting started](aiassistview_images/wpf_aiassistview_gettingstarted.png)