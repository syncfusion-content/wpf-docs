---
layout: post
title: ToolTip in WPF Radial Menu Control | Syncfusion®
description: Learn about tooltip support in the Syncfusion® WPF Radial Menu (SfRadialMenu) control, its elements, and more.
platform: WPF
control: SfRadialMenu 
documentation: ug
---

# ToolTip in WPF Radial Menu (SfRadialMenu)

Tooltip support is available for radial menu items, appearing when hovering over the corresponding item.

### ToolTip Placement

The position of the tooltip relative to the Radial Menu can be customized using the `ToolTipPlacement` property. The following options are available:

- **None**: Tooltip is hidden from the display.
- **Left**: Tooltip is displayed to the left of the Radial Menu.
- **Top**: Tooltip is displayed on top of the Radial Menu.
- **Right**: Tooltip is displayed to the right of the Radial Menu.
- **Bottom**: Tooltip is displayed at the bottom of the Radial Menu.

{%highlight xaml%}

<navigation:SfRadialMenuItem ToolTip="Bold" ToolTipPlacement="Top" />

{% endhighlight %}

![ToolTip in Radial Menu](Concepts_images/Concepts_img6.png)
