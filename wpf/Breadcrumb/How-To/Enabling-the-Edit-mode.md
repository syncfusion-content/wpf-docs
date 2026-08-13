---
layout: post
title: Enabling Edit Mode in WPF HierarchyNavigator | Syncfusion®
description: Enabling edit mode in WPF HierarchyNavigator allows interactive modification of hierarchy items, supporting efficient data updates.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Enabling Edit Mode in WPF HierarchyNavigator

A navigation path can be edited by using the AutoComplete functionality. By default, editing is disabled (set to false). If the IsEnableEditMode Boolean property is set to True, then editing will be enabled.


{% highlight c# %}


HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.IsEnableEditMode = true;


{% endhighlight  %}


![Enabling-the-Edit-mode_images1](Enabling-the-Edit-mode_images/Enabling-the-Edit-mode_img1.png)



