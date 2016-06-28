---
layout: post
title: Theming| OlapGrid | Wpf | Syncfusion
description: theming
platform: wpf
control: OlapGrid
documentation: ug
---

# Theming

Theming is the process of applying particular settings to the visual elements of a control. This feature provides the following themes options:

*	Default
*	Blend
*	Metro
*	Office2010Blue
*	Office2010Black
*	Office2010Silver
*	Office2013LightGray
*	Office2013DarkGray
*	Office2013White
*	VS

The **"VisualStyle"** property allows you to set the theme for the OlapGrid control. The following code sample demonstrates how to add theming to the OlapGrid control.

{% tabs %}
  
{% highlight xaml %}

<syncfusion:OlapGrid  x:Name="olapGrid" VisualStyle="Transparent"/>

{% endhighlight %}

{% highlight c# %}

this.olapGrid.VisualStyle = OlapGridVisualStyle.Transparent;

{% endhighlight %}

{% endtabs %}

A sample demo available in the following link.

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Appearance\Visual Styles








