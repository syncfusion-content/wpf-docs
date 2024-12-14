---
layout: post
title: Accessibility in WPF TreeMap control | Syncfusion
description: Learn here about Accessibility support with the Syncfusion WPF TreeMap (SfTreeMap) control, its elements and more.
platform: wpf
control: TreeMap
documentation: ug
---

#  Accessibility support in WPF TreeMap (SfTreeMap)

The TreeMap is designed to efficiently interact with its elements, offering voice descriptions for each item in the treemap.

## Keyboard shortcuts in WPF TreeMap (SfTreeMap)

The [Syncfusion WPF TreeMap](https://www.syncfusion.com/wpf-controls/treemap) supports keyboard shortcuts for user interaction. 
The following is a table outlining the various shortcuts and their associated functions:

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Tab<br/><br/></td><td> 
Moves the selection to the next item on the right side of the TreeMap.
<br/><br/></td></tr>
<tr>
<td>
Shift + Tab<br/><br/></td><td>
Moves the selection to the previous item on the left side of the TreeMap.
<br/><br/></td></tr>
</table>

N>
* When [`SelectionModes`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.SfTreeMap.html#Syncfusion_UI_Xaml_TreeMap_SfTreeMap_SelectionModes) is set to [`Default`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.TreeMapSelectionModes.html#Syncfusion_UI_Xaml_TreeMap_TreeMapSelectionModes_Default), each key press clears the previous focus and selects the new item. 
* When [`SelectionModes`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.SfTreeMap.html#Syncfusion_UI_Xaml_TreeMap_SfTreeMap_SelectionModes) is set to [`Multiple`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeMap.TreeMapSelectionModes.html#Syncfusion_UI_Xaml_TreeMap_TreeMapSelectionModes_Multiple), the previously focused item remains selected while new items are selected with each key press.