---
layout: post
title: How to add labels for track ball in WPF Sparkline control | Syncfusion®
description: The session describes how to add label and customize its appearance inside track ball of WPF spark line.
platform: wpf
control: SfSparkline
documentation: ug
---

# How to add labels for track ball in WPF Sparkline control

You can add labels for the track ball to show the corresponding values. To add labels for the track ball, subscribe to the `OnSparklineMouseMove` event. You can get the following data from the event argument.

{% tabs %}

{% highlight xaml %}

<Window.DataContext>
    <local:UsersViewModel/>
</Window.DataContext>

<Syncfusion:SfLineSparkline 
    ShowTrackBall="True" 
    OnSparklineMouseMove="SfLineSparkline_OnSparklineMouseMove" 
    x:Name="sparkline" 
    ItemsSource="{Binding UsersList}" 
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

ContentPresenter info;
private void SfLineSparkline_OnSparklineMouseMove(object src, SparklineMouseMoveEventArgs args)
{
    if(!args.RootPanel.Children.Contains(info))
    {
        info = new ContentPresenter();
        args.RootPanel.Children.Add(info);
        TextBlock.SetForeground(info, new SolidColorBrush(Colors.Red));
        TextBlock.SetFontSize(info, 25);
    }

    info.Content = args.Value.Y;

    info.Arrange(new Rect(args.Coordinate.X, args.Coordinate.Y, info.ActualWidth, info.ActualHeight));
}
		
{% endhighlight %}

{% endtabs %}

The following is a snapshot of the track ball labels.

![Custom label in Sparkline track ball](Add-labels-for-track-ball_images/Add-labels-for-track-ball_img1.png)