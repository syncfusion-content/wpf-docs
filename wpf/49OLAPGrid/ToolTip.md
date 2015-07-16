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

[C#]



// Enabling HeaderCell Tooltip

this.OlapGrid1.ShowHeaderCellsToolTip = true;





[VB]



' Enabling HeaderCell Tooltip

Me.OlapGrid1.ShowHeaderCellsToolTip = True





{ ![](ToolTip_images/ToolTip_img1.png) | markdownify }
{:.image }


## ValueCellToolTip

OlapGrid provides cell information (Measure, Column Header Value, Row Header Value and Cell Value) when the mouse pointer is hovered on the Value Cells. This property can be enabled by:

[C#]



// Enabling Valuecell Tooltip

this.OlapGrid1.ShowValueCellToolTip = true;





[VB]



' Enabling Valuecell Tooltip

Me.OlapGrid1.ShowValueCellToolTip = True



{ ![](ToolTip_images/ToolTip_img2.png) | markdownify }
{:.image }


