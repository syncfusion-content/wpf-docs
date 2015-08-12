---
layout: post
title: Using-the-Refresh-button
description: using the refresh button
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Using the Refresh button

The Refresh button is on the right side of the HierarchyNavigator control. Clicking the Refresh button will initiate the HierarchyNavigatorRefreshButtonClick event.

![](Using-the-Refresh-button_images/Using-the-Refresh-button_img1.png)


{% highlight xml %}

XAML
<syncfusion:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" />

{% endhighlight %}

{% highlight c# %}

C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);

{% endhighlight %}

{% highlight c# %}
C#
private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e) 
{
   //Occurs when Refresh Button Click
}

{% endhighlight %}

