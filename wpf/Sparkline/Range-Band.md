---
layout: post
title: Range Band in WPF Sparkline control | Syncfusion
description: Learn here all about Range Band support in Syncfusion WPF Sparkline (SfSparkline) control and more.
platform: wpf
control: SfSparkline
documentation: ug
---

# Range Band in WPF Sparkline (SfSparkline)

Range band feature used to highlight the particular mentioned range along Y axis.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 

			ItemsSource="{Binding UsersList}" 

			BandRangeStart="2000”

			BandRangeEnd="-1000” RangeBandBrush="Green”

			YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers",

	BandRangeStart = 2000,

	BandRangeEnd = -1000,

	RangeBandBrush = new SolidColorBrush(Colors.Green)

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for range band,

![Range-Band_img1](Range-Band_images/Range-Band_img1.png)
