---
layout: post
title: Behaviour-Changes
description: behaviour changes
platform: wpf
control: Diagram
 documentation: ug
---

# Behavior Changes

The following are the changes made from version 10.1.0.44: 

* The Bounds property of DiagramView will not have any effect and instead a new LayoutBounds property has been implemented with Horizontal and Vertical alignment of Diagram within rectangular bounds.
* Hereafter RefreshLayout has to be used to update the layout instead of calling StartNodeArrangement and PrepareActivity methods.
