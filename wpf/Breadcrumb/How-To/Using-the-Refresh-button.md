---
layout: post
title: Using Refresh Button in WPF HierarchyNavigator | Syncfusion®
description: Using Refresh Button in WPF HierarchyNavigator enables quick updates of displayed data, ensuring current information visibility.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Using Refresh Button in WPF HierarchyNavigator

The Refresh button is on the right side of the HierarchyNavigator control. Clicking the Refresh button will initiate the HierarchyNavigatorRefreshButtonClick event.

![Using-the-Refresh-button_images1](Using-the-Refresh-button_images/Using-the-Refresh-button_img1.png)

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" />
{% endhighlight %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);

private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)<br>
{<br>    
 //Occurs when Refresh Button Click<br>
 }
{% endhighlight  %}
{% endtabs %}


