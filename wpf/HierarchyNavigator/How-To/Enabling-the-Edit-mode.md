---
layout: post
title: Enabling-the-Edit-mode
description: enabling the edit mode
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

### Enabling the Edit mode

A navigation path can be edited by using the AutoComplete functionality. By default, editing is disabled (set to false). If the IsEnableEditMode Boolean property is set to True, then editing will be enabled.

C#



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.IsEnableEditMode = true;





{ ![](Enabling-the-Edit-mode_images/Enabling-the-Edit-mode_img1.png) | markdownify }
{:.image }


