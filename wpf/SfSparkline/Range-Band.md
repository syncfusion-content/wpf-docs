---
layout: post
title: Range Band | SfSparkline | wpf | Syncfusion
description: range band
platform: wpf
control: SfSparkline
documentation: ug
---

# Range Band

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

![](Range-Band_images/Range-Band_img1.png)