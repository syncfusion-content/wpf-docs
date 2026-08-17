---
layout: post
title: Theming in WPF OlapClient | Syncfusion®
description: The theming support in OlapClient applies visual themes like Office 2010 Blue, Black, and Silver to visual elements in the WPF control.
platform: wpf
control: OlapClient
documentation: ug
---

# Theming in WPF OlapClient

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

The `VisualStyle` property allows users to set the Visual Style of the OLAP client control. The following code sample demonstrates how theming is added to the OLAP client control.

{% tabs %}

{% highlight xaml %} 

<syncfusion:OlapClient  x:Name="olapClient" VisualStyle="Transparent"/>

{% endhighlight %}

{% highlight c# %}  

this.olapClient.VisualStyle = OlapClientVisualStyle.Transparent;

{% endhighlight %}

{% endtabs %}
