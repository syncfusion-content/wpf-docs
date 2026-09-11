---
layout: post
title: EmptyView in WPF AIAssistView | Syncfusion®
description: EmptyView feature in WPF AIAssistView displays custom content when no messages are present, improving the user experience before a conversation starts.
platform: wpf
control: SfAIAssistView
documentation: ug
---

# EmptyView in WPF AI AssistView

By using the EmptyView and EmptyViewTemplate properties, the AssistView displays custom content (such as a welcome message, an image, or a call-to-action) when the conversation has no messages. This is useful for guiding the user before a chat begins.

The empty view is automatically shown when the `Messages` collection is empty and either `EmptyView` or `EmptyViewTemplate` is set. When a `BannerTemplate` is provided, the empty view is hidden and the banner is displayed instead.

## EmptyView

The `EmptyView` property accepts any object as its content, which is then displayed in the center of the assist view when there are no messages.

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
    <Grid>
        <syncfusion:SfAIAssistView x:Name="AiAssistView" 
                                EmptyView="How can I help you?"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## EmptyViewTemplate

The `EmptyViewTemplate` property allows you to fully customize the appearance of the empty view by providing a `DataTemplate`. This is helpful when you need to display richer content such as images, multiple text blocks, or styled layouts.

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
    <Grid>
        <syncfusion:SfAIAssistView x:Name="AiAssistView">
            <syncfusion:SfAIAssistView.EmptyViewTemplate>
                <DataTemplate>
                    <StackPanel>
                        <Image Source="Assets/Icon.png"
                        Width="40"
                        Height="40"/>
                        <TextBlock Text="Hi, How can I help you?"
                        FontSize="25"
                        FontWeight="SemiBold"/>
                        <TextBlock Text="Ask anything to get started."
                        Opacity="0.7"/>   
                    </StackPanel>
                </DataTemplate>
            </syncfusion:SfAIAssistView.EmptyViewTemplate>
        </syncfusion:SfAIAssistView>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![EmptyView feature in WPF AI AssistView control](aiassistview_images\wpf_aiassistview_emptyview.png)
