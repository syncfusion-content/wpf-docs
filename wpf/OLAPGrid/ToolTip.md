---
layout: post
title: ToolTip
description: tooltip
platform: wpf
control: OLAP Grid
documentation: ug
---

# ToolTip

OlapGrid can additionally display dimension member information within a tooltip when the mouse pointer is moved over the Header Cells or Value Cells of the Grid control.

## HeaderToolTip

OlapGrid provides drill down information through the Header Cell ToolTip for hierarchical dimensions, enabling efficient preview of data before drilling down. It can be enabled using the following property of OlapGrid.

{% tabs %}
  {% highlight c# %}

    



// Enabling HeaderCell Tooltip

this.OlapGrid1.ShowHeaderCellsToolTip = true;

    {% endhighlight %}




  {% highlight vbnet %}

    



' Enabling HeaderCell Tooltip

Me.OlapGrid1.ShowHeaderCellsToolTip = True

    {% endhighlight %}


{% endtabs %}





![](ToolTip_images/ToolTip_img1.png)


## ValueCellToolTip

OlapGrid provides cell information (Measure, Column Header Value, Row Header Value and Cell Value) when the mouse pointer is hovered on the Value Cells. This property can be enabled by:

{% tabs %}
  {% highlight c# %}

    



// Enabling Valuecell Tooltip

this.OlapGrid1.ShowValueCellToolTip = true;

    {% endhighlight %}





  {% highlight vbnet %}

    



' Enabling Valuecell Tooltip

Me.OlapGrid1.ShowValueCellToolTip = True

    {% endhighlight %}


{% endtabs %}


![](ToolTip_images/ToolTip_img2.png)


