---
layout: post
title: Refresh Button in WPF Breadcrumb | Syncfusion®
description: Use the refresh button to trigger navigation refresh actions and handle refresh-related events in the Breadcrumb control.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Refresh Button in WPF Breadcrumb (HierarchyNavigator)

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

