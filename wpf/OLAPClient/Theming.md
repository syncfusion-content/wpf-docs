---
layout: post
title: Theming| OlapClient  | Wpf | Syncfusion
description: theming
platform: wpf
control: OlapClient 
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

The **VisualStyle** property allows the user to set the visual style of the OlapClient control. The following code sample demonstrate how theming is added to the OlapClient control.

{% tabs %}

{% highlight xaml %} 

<syncfusion:OlapClient  x:Name="olapClient" VisualStyle="Transparent"/>

{% endhighlight %}

{% highlight c# %}  

this.olapClient.VisualStyle = OlapClientVisualStyle.Transparent;

{% endhighlight %}

{% endtabs %}
