---
layout: post
title: Refresh-Button
description: refresh button
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Refresh Button

The Refresh button enables the HierarchyNavigatorRefreshButtonClick event to initiate in the HierarchyNavigator control.

{ ![](Refresh-Button_images/Refresh-Button_img1.png) | markdownify }
{:.image }


<table>
<tr>
<td>
XAML&lt;locals:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" /&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);</td></tr>
<tr>
<td>
C#private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)<br>{<br>     //Occurs when Refresh Button Click<br>}</td></tr>
</table>


