---
layout: post
title: Refresh Button in WPF HierarchyNavigator | Syncfusion®
description: Refresh Button in WPF HierarchyNavigator allows users to reload hierarchy data quickly and maintain up-to-date views.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Refresh Button in WPF HierarchyNavigator

The Refresh button enables the HierarchyNavigatorRefreshButtonClick event to initiate in the HierarchyNavigator control.

![Refresh-Button_img1](Refresh-Button_images/Refresh-Button_img1.png)


{% tabs %}
{% highlight xaml %}
<locals:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" />
{% endhighlight %}

{% highlight C# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>
hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);

private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)
<br>
{<br>     //Occurs when Refresh Button Click<br>}
{% endhighlight %}

{% endtabs %}

