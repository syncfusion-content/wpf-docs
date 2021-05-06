---
layout: post
title: Tooltip in WPF Olap Grid control | Syncfusion
description: Learn about Tooltip support in Syncfusion WPF Olap Grid control and more.
platform: wpf
control: OlapGrid
documentation: ug
---

# Tooltip in WPF Olap Grid

The OLAP grid can additionally display the member information within a tooltip when the mouse pointer is moved over the header cells or value cells of the OLAP grid control.

## Header tooltip

The OLAP grid provides drill-down information through the header cell tooltip for hierarchical dimensions by enabling efficient preview of data before drilling down. It can be enabled using the following property of the OLAP grid.

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

![To display the header cells tooltip in OlapGrid](ToolTip_images/ToolTip_img1.png)

## Value cell tooltip

The OLAP grid provides cell information (measure, column header, row header, and value cell) when the mouse pointer is hovered over the value cells. This can be enabled using the following property of the OLAP grid.

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

![To display the value cells tooltip in OlapGrid](ToolTip_images/ToolTip_img2.png)


