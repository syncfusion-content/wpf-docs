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

![](Refresh-Button_images/Refresh-Button_img1.png)



<table>
<tr>
<td>
{% highlight xml %}<locals:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" />{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %}HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %}private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)<br>{<br>     //Occurs when Refresh Button Click<br>}{% endhighlight %}</td></tr>
</table>


