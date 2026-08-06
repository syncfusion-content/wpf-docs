---
layout: post
title: Range Band in WPF Sparkline | Syncfusion®
description: Range band in the WPF Sparkline highlights a specified value range, helping emphasize thresholds, targets, and data variations.
platform: wpf
control: SfSparkline
documentation: ug
---

# Range Band in WPF Sparkline

The range band feature is used to highlight a particular range along the Y axis.

{% tabs %}

{% highlight xaml %}

 <Syncfusion:SfLineSparkline
     ItemsSource="{Binding UsersList}"
     BandRangeStart="2000"
     BandRangeEnd="-1000"
     RangeBandBrush="Green"
     YBindingPath="NoOfUsers">
 </Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    BandRangeStart = 2000,
    BandRangeEnd = -1000,
    RangeBandBrush = new SolidColorBrush(Colors.Green)
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the range band.

![Range-Band_img1](Range-Band_images/Range-Band_img1.png)
