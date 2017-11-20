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
SfBusyIndicator busyindicator = new SfBusyIndicator();
busyindicator.Header = "Loading..";
busyindicator.Foreground = Brushes.White;
busyindicator.Background = Brushes.CornflowerBlue;
busyindicator.ViewboxHeight = 200;
Grid1.Children.Add(busyindicator);

{% endhighlight %}

{% highlight VB %}

' To set the ViewboxHeight for SfBusyIndicator
Dim busyindicator As New SfBusyIndicator()
busyindicator.Header = "Loading.."
busyindicator.Foreground = Brushes.White
busyindicator.Background = Brushes.CornflowerBlue
busyindicator.ViewboxHeight = 200
Grid1.Children.Add(busyindicator)

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
SfBusyIndicator busyindicator = new SfBusyIndicator();
busyindicator.Header = "Loading..";
busyindicator.Foreground = Brushes.White;
busyindicator.Background = Brushes.CornflowerBlue;
busyindicator.ViewboxWidth = 50;
Grid1.Children.Add(busyindicator);

{% endhighlight %}

{% highlight VB %}

' To set the ViewBoxWidth for SfBusyIndicator
Dim busyindicator As New SfBusyIndicator()
busyindicator.Header = "Loading.."
busyindicator.Foreground = Brushes.White
busyindicator.Background = Brushes.CornflowerBlue
busyindicator.ViewboxWidth = 50
Grid1.Children.Add(busyindicator)

{% endhighlight %}

{% endtabs %}


![](Sizing_images/Sizing_img2.png)

Busy Indicator with height and width
{:.caption}
