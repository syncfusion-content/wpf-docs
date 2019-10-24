---
layout: post
title: Markers | SfSparkline | wpf | Syncfusion
description: markers
platform: wpf
control: SfSparkline
documentation: ug
---

# Markers

Markers are used to indicate the value point for line and area series, and we can customize with different template.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 

		    ItemsSource="{Binding UsersList}" 

			MarkerVisibility="Visible"

		    YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers",

	MarkerVisibility = Visibility.Visible

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for markers,

![](Markers_images/Markers_img1.png)