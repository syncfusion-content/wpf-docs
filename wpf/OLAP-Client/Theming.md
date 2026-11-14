---
layout: post
title: Theming in WPF OLAP Client | Syncfusion®
description: The theming support in OLAP Client applies visual themes like Office 2010 Blue, Black, and Silver to visual elements in the WPF control.
platform: wpf
control: OLAP Client
documentation: ug
---

# Theming in WPF OLAP Client

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

The `VisualStyle` property allows users to set the Visual Style of the OLAP Client control. The following code sample demonstrates how theming is added to the OLAP Client control.

{% tabs %}

{% highlight xaml %} 

<syncfusion:OlapClient  x:Name="olapClient" VisualStyle="Transparent"/>

{% endhighlight %}

{% highlight c# %}  

this.olapClient.VisualStyle = OlapClientVisualStyle.Transparent;

{% endhighlight %}

{% endtabs %}
