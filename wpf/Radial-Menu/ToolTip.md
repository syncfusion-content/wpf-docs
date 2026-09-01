---
layout: post
title: ToolTips in WPF Radial Menu | Syncfusion®
description: Display tooltips for WPF Radial Menu items and customize tooltip placement around the WPF Radial Menu control.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# ToolTips in WPF Radial Menu (SfRadialMenu)

Tooltip support available for the WPF Radial Menu items. This will show when mouse over the corresponding item. 

ToolTip Placement

Position of the tooltip displayed relative to the WPF Radial Menu can be customized using ToolTipPlacement property. This have the following options.

* None: Tooltip is hidden from the display.
* Left: Tooltip is displayed left of the WPF Radial Menu. 
* Top: Tooltip is displayed on top of the WPF Radial Menu.
* Right: Tooltip is displayed right of the WPF Radial Menu.
* Bottom: Tooltip is displayed at the bottom of the WPF Radial Menu.

{%highlight xaml%}



<navigation:SfRadialMenuItem  ToolTip="Bold" ToolTipPlacement="Top"  />

{%endhighlight%}

![Concepts_img6](Concepts_images/Concepts_img6.png)



