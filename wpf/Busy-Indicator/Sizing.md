---
layout: post
title: Sizing | Busy Indicator | wpf | Syncfusion
description: sizing
platform: wpf
control: Busy Indicator
documentation: ug
---

# Sizing

## ViewBoxHeight

The ViewBoxHeight property allows the user to set the height of the ViewBox.

{% tabs %}

{% highlight xaml%}

 <!--To set the ViewboxHeight for SfBusyIndicator-->
<Notification:SfBusyIndicator Foreground="White" Header="Loading..." Background="CornflowerBlue" ViewboxHeight="200" >
</Notification:SfBusyIndicator>

{% endhighlight %}

{% highlight C# %}

// To set the ViewboxHeight for SfBusyIndicator
SfBusyIndicator SfBusyIndicator = new SfBusyIndicator();
SfBusyIndicator.Header = "Loading..";
SfBusyIndicator.Foreground = Brushes.White;
SfBusyIndicator.Background = Brushes.CornflowerBlue;
SfBusyIndicator.ViewboxHeight = 200;
Grid1.Children.Add(SfBusyIndicator);

{% endhighlight %}

{% highlight VB %}

' To set the ViewboxHeight for SfBusyIndicator
Dim SfBusyIndicator As New SfBusyIndicator()
SfBusyIndicator.Header = "Loading.."
SfBusyIndicator.Foreground = Brushes.White
SfBusyIndicatorBackground = Brushes.CornflowerBlue
SfBusyIndicator.ViewboxHeight = 200
Grid1.Children.Add(SfBusyIndicator)

{% endhighlight %}

{% endtabs %}


![](Sizing_images/Sizing_img1.png)


## ViewBoxWidth

ViewBoxWidth property allows the user to set the width of the ViewBox.

{% tabs %}

{% highlight xaml %}


<!--To set the ViewBoxWidth for SfBusyIndicator-->

<Notification:SfBusyIndicator Foreground="White" Header="Loading..." Background="CornflowerBlue" ViewboxWidth="50" >

</Notification:SfBusyIndicator>

{% endhighlight %}

{% highlight C# %}

// To set the ViewBoxWidth for SfBusyIndicator
SfBusyIndicator SfBusyIndicator = new SfBusyIndicator();
SfBusyIndicator.Header = "Loading..";
SfBusyIndicator.Foreground = Brushes.White;
SfBusyIndicator.Background = Brushes.CornflowerBlue;
SfBusyIndicator.ViewboxWidth = 50;
Grid1.Children.Add(SfBusyIndicator);

{% endhighlight %}

{% highlight VB %}

' To set the ViewBoxWidth for SfBusyIndicator
Dim SfBusyIndicator As New SfBusyIndicator()
SfBusyIndicator.Header = "Loading.."
SfBusyIndicator.Foreground = Brushes.White
SfBusyIndicator.Background = Brushes.CornflowerBlue
SfBusyIndicator.ViewboxWidth = 50
Grid1.Children.Add(SfBusyIndicator)

{% endhighlight %}

{% endtabs %}


![](Sizing_images/Sizing_img2.png)

Busy Indicator with height and width
{:.caption}




N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Sizing) in GitHub