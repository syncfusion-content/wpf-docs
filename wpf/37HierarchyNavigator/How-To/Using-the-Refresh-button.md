---
layout: post
title: Using-the-Refresh-button
description: using the refresh button
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

### Using the Refresh button

The Refresh button is on the right side of the HierarchyNavigator control. Clicking the Refresh button will initiate the HierarchyNavigatorRefreshButtonClick event.

{ ![](Using-the-Refresh-button_images/Using-the-Refresh-button_img1.png) | markdownify }
{:.image }


<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" /&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);</td></tr>
<tr>
<td>
C#private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)<br>{<br>     //Occurs when Refresh Button Click<br>}</td></tr>
</table>


