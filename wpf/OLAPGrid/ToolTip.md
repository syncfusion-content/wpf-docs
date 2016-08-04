---
layout: post
title: ToolTip| OlapGrid | Wpf | Syncfusion
description: tooltip
platform: wpf
control: OlapGrid
documentation: ug
---

# ToolTip

OlapGrid can additionally display the member information within a tooltip when the mouse pointer is moved over the header cells or value cells of the OlapGrid control.

## Header Tooltip

OlapGrid provides drill down information through the header cell tooltip for hierarchical dimensions, enabling efficient preview of data before drilling down. It can be enabled using the following property of OlapGrid.

{% tabs %}
  
{% highlight c# %}

// Enabling Header Cell Tooltip
this.OlapGrid1.ShowHeaderCellsToolTip = true;

{% endhighlight %}

{% highlight vbnet %}

' Enabling Header Cell Tooltip
Me.OlapGrid1.ShowHeaderCellsToolTip = True

{% endhighlight %}

{% endtabs %}

![](ToolTip_images/ToolTip_img1.png)

## Value Cell Tooltip

OlapGrid provides cell information (Measure, Column Header, Row Header and Value Cell) when the mouse pointer is hovered on the value cells. It can be enabled using the following property of OlapGrid.

{% tabs %}
  
{% highlight c# %}

// Enabling Value Cell Tooltip
this.OlapGrid1.ShowValueCellToolTip = true;

{% endhighlight %}

{% highlight vbnet %}

' Enabling Value Cell Tooltip
Me.OlapGrid1.ShowValueCellToolTip = True

{% endhighlight %}

{% endtabs %}

![](ToolTip_images/ToolTip_img2.png)


