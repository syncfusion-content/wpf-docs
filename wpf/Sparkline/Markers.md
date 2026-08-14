---
layout: post
title: Markers in WPF Sparkline | Syncfusion®
description: Markers in the WPF Sparkline highlight specific data points, making trends, values, and key points easier to identify and analyze.
platform: wpf
control: SfSparkline
documentation: ug
---

# Markers in WPF Sparkline 

Markers are used to indicate the value points for line and area sparklines, and can be customized with different templates.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 
	ItemsSource="{Binding UsersList}" 
	MarkerVisibility="Visible"
	YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
	ItemsSource = new UsersViewModel().UsersList,
	YBindingPath = "NoOfUsers",
	MarkerVisibility = Visibility.Visible
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the markers.

![Markers_img1](Markers_images/Markers_img1.png)
