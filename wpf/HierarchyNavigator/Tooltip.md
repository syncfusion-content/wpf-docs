---
layout: post
title: Tooltip
description: tooltip
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Tooltip

A ToolTip can be displayed for each HierarchyNavigator item.

Setting the ShowToolTip Boolean property to true in the HierarchyNavigator control will enable the ToolTips for all items.

<table>
<tr>
<td>
{highlight xml %}<syncfusion:HierarchyNavigator ShowToolTip="True" x:Name="hierarchyNavigator1" />{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %}HierarchyNavigator hierarchyNavigatorControl1 = new HierarchyNavigator() { Height = 30 };hierarchyNavigatorControl1.ShowToolTip = true;{% endhighlight %}</td></tr>
</table>


![](Tooltip_images/Tooltip_img1.png)



