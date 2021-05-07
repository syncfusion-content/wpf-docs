---
layout: post
title: Theming in WPF Olap Chart control | Syncfusion
description: Learn about Theming support in Syncfusion Essential Studio WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
documentation: ug
---

# Theming in WPF Olap Chart

Theming is the process of applying particular settings to visual elements of a product. This feature provides the following theming options:

* Office 2010 Blue
* Office 2010 Black
* Office 2010 Silver
* Transparent
* Office 2007 Blue
* Office 2007 Black
* Office 2007 Silver
* Blend
* Metro
* Office 2003
* Default

The `VisualStyle` property allows users to set the visual style of the OLAP chart control. The following code sample demonstrates how theming is added to the OLAP chart control.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart  x:Name="olapChart" VisualStyle="Transparent"/> 

{% endhighlight %}

{% highlight c# %}
 
this.olapChart.VisualStyle = OlapChartVisualStyle.Transparent;

{% endhighlight %}
 
{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Appearance\Visual Styles demo
