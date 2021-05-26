---
layout: post
title: Add labels for track ball | SfSparkline | wpf | Syncfusion
description: The session describes how to add label and customize its appearance inside track ball of WPF spark line (SfSparkline).
platform: wpf
control: SfSparkline
 documentation: ug
---

# Add labels for track ball

We can add labels for track ball to show the corresponding values. In order to add labels for the trackball, you need to subscribe the event OnSparklineMouseMove and you can get the following data’s from event argument.

{% tabs %}

{% highlight xaml %}

<Page.DataContext>

	<local:UsersViewModel/>

</Page.DataContext>

<Syncfusion:SfLineSparkline ShowTrackBall="True" OnSparklineMouseMove="SfLineSparkline_OnSparklineMouseMove" x:Name="sparkline" ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

    ContentPresenter info;

        private void SfLineSparkline_OnSparklineMouseMove(object src, SparklineMouseMoveEventArgs args)

        {

            if (!args.RootPanel.Children.Contains(info))

            {

                info=new ContentPresenter();

                args.RootPanel.Children.Add(info);

                TextBlock.SetForeground(info, new SolidColorBrush(Colors.Red)); 
                
                TextBlock.SetFontSize(info, 25); 
            }

            info.Content = args.Value.Y;

            info.Arrange(new Rect(args.Coordinate.X,args.Coordinate.Y,info.ActualWidth,info.ActualHeight));

        }
		
{% endhighlight %}

{% endtabs %}

Following is the snapshot for track ball labels,

![custom label in Sparkline track ball](Add-labels-for-track-ball_images/Add-labels-for-track-ball_img1.png)