---
layout: post
title: Tooltip in WPF HierarchyNavigator | Syncfusion®
description: Tooltip in WPF HierarchyNavigator display contextual information for items, improving usability and enhancing navigation.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Tooltip in WPF HierarchyNavigator

A ToolTip can be displayed for each HierarchyNavigator item.

Setting the ShowToolTip Boolean property to true in the HierarchyNavigator control will enable the ToolTips for all items.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator ShowToolTip="True" x:Name="hierarchyNavigator1" />
{% endhighlight %}

{% highlight C# %}
HierarchyNavigator hierarchyNavigatorControl1 = new HierarchyNavigator()
 { Height = 30 };
 hierarchyNavigatorControl1.ShowToolTip = true;
 {% endhighlight %}
{% endtabs %}


![Tooltip_images1](Tooltip_images/Tooltip_img1.png)



