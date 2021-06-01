---
layout: post
title: Tooltip in WPF Olap Gauge control | Syncfusion
description: Learn about Tooltip support in Syncfusion Essential Studio WPF Olap Gauge control, its elements and more details.
platform: wpf
control: OLAP Gauge
 documentation: ug
---

# Tooltip in WPF Olap Gauge

The OLAP gauge provides the information about values when the mouse pointer is moved over the gauge.

## Pointer tooltip

The OLAP gauge provides value information when the mouse pointer is moved over the pointer. This can be achieved by enabling the `ShowPointersTooltip` property.

The following code snippet illustrates how to show a tooltip for pointers.

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

![Shows the tooltip of pointer in WPF OLAPGauge](Tooltip_images/Pointer-tooltip.png)

## Marker tooltip

The OLAP gauge provides goal information when the mouse pointer is moved over the marker. This can be achieved by enabling the `ShowMarkersTooltip` property.

The following code snippet illustrates how to show a tooltip for markers.

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

![Shows the tooltip of marker in WPF OLAPGauge](Tooltip_images/Marker-tooltip.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Product ShowCase\KPI\
