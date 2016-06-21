---
layout: post
title: Theming| OlapChart | Wpf | Syncfusion
description: Theming
platform: wpf
control: OlapChart
documentation: ug
---

# Theming

Theming is the process of applying particular settings to the visual elements of a product. This feature provides the following theming options:

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

The **VisualStyle** property allows the user to set the visual style of the OlapChart control. The following code sample demonstrate how theming is added to the OlapChart control.

{% tabs %}

{% highlight xaml %}

      <syncfusion:OlapChart  x:Name="olapChart" VisualStyle="Transparent"/> 

{% endhighlight %}

{% highlight c# %}
 
      this.olapChart.VisualStyle = OlapChartVisualStyle.Transparent;

{% endhighlight %}
 
{% endtabs %}

A sample demo is available at the following link:

[system drive]:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Appearance\Visual Styles demo