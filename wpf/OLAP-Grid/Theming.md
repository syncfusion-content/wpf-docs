---
layout: post
title: Theming in WPF Olap Grid control | Syncfusion
description: Learn about Theming support in Syncfusion Essential Studio WPF Olap Grid control, its elements and more details.
platform: wpf
control: OlapGrid
documentation: ug
---

# Theming in WPF Olap Grid

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

The `VisualStyle` property allows you to set a theme for the OLAP grid control. The following code sample demonstrates how to add theming to the OLAP grid control.

{% tabs %}
  
{% highlight xaml %}

<syncfusion:OlapGrid  x:Name="olapGrid" VisualStyle="Transparent"/>

{% endhighlight %}

{% highlight c# %}

this.olapGrid.VisualStyle = OlapGridVisualStyle.Transparent;

{% endhighlight %}

{% endtabs %}

A sample demo available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Appearance\Visual Styles








