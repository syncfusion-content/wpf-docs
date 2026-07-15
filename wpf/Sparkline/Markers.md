---
layout: post
title: Markers in WPF Sparkline control | Syncfusion
description: Learn here all about Markers support in Syncfusion WPF Sparkline (SfSparkline) control, its elements and more.
platform: wpf
control: SfSparkline
documentation: ug
---

# Markers in WPF Sparkline (SfSparkline)

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
