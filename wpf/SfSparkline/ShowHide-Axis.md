---
layout: post
title: ShowHide Axis | SfSparkline | wpf | Syncfusion
description: show/hide axis
platform: wpf
control: SfSparkline
documentation: ug
---

# Show/Hide Axis

Following code used to enable the axis and this feature applicable for all the sparkline except WinLoss sparkline, also you can style the axis by AxisStyle property and position the axis by AxisOrigin property.

{% highlight xaml %}

<Syncfusion:SfLineSparkline ShowAxis="True" ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

</Syncfusion:SfLineSparkline>

{% endhighlight %}

Following is the snapshot for axis visibility,

![](ShowHide-Axis_images/ShowHide-Axis_img1.png)