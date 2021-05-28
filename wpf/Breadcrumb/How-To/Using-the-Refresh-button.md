---
layout: post
title: Using the Refresh button| Hierarchical Navigator | Wpf | Syncfusion
description: Using the refresh button in Syncfusion Essential Studio WPF Hierarchy Navigator control, its elements and more.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Using the Refresh button

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


