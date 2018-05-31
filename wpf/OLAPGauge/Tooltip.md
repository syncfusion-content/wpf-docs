---
layout: post
title: Tooltip
description: Tooltip
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Tooltip

OlapGauge provides the information about values when the mouse pointer is moved over the gauge.

## Pointer tooltip

OlapGauge provides value information when the mouse pointer is moved over the pointer. This is achieved by enabling `ShowPointersTooltip` property.

The following code snippet illustrates about how to show tooltip for pointers:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" ShowPointersTooltip="True"/>

{% endhighlight %}

{% highlight c# %}

this.OlapGauge1.ShowPointersTooltip = true;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.ShowPointersTooltip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/Pointer-tooltip.png)

## Marker tooltip

OlapGauge provides goal information when the mouse pointer is moved over the marker. This is achieved by enabling `ShowMarkersTooltip` property.

The following code snippet illustrates about how to show tooltip for markers:

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" ShowMarkersTooltip="True"/>

{% endhighlight %}

{% highlight c# %}

this.OlapGauge1.ShowMarkersTooltip = true;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.ShowMarkersTooltip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/Marker-tooltip.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Product ShowCase\KPI\