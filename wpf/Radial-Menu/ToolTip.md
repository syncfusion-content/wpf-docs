---
layout: post
title: ToolTip | SfRadialMenu  | wpf | Syncfusion
description: tooltip 
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# ToolTip

Tooltip support available for the radial menu items. This will show when mouse over the corresponding item. 

ToolTip Placement

Position of the tooltip displayed relative to the Radial Menu can be customized using ToolTipPlacement property. This have the following options.

* None: Tooltip is hidden from the display.
* Left: Tooltip is displayed left of the Radial Menu. 
* Top: Tooltip is displayed on top of the Radial Menu.
* Right: Tooltip is displayed right of the Radial Menu.
* Bottom: Tooltip is displayed at the bottom of the Radial Menu.

{%highlight xaml%}



<navigation:SfRadialMenuItem  ToolTip="Bold" ToolTipPlacement="Top"  />

{%endhighlight%}

![](Concepts_images/Concepts_img6.png)



