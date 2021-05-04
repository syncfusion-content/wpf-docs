---
layout: post
title: Behavior Changes in WPF Wizard Control control | Syncfusion
description: Learn here all about Behavior Changes support in Syncfusion WPF Diagram (classic) control and more.
platform: wpf
control: Diagram
documentation: ug
---

# Behavior Changes in WPF Diagram (classic)

The following are the changes made from version 10.1.0.44: 

* The Bounds property of DiagramView will not have any effect and instead a new LayoutBounds property has been implemented with Horizontal and Vertical alignment of Diagram within rectangular bounds.
* Hereafter RefreshLayout has to be used to update the layout instead of calling StartNodeArrangement and PrepareActivity methods.
