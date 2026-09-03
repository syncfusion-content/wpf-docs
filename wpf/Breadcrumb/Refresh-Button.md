---
layout: post
title: Refresh Button in WPF BreadCrumb | Syncfusion®
description: Refresh Button in WPF BreadCrumb allows users to reload hierarchy data quickly and maintain up-to-date views.
platform: wpf
control: BreadCrumb
documentation: ug
---

# Refresh Button in WPF BreadCrumb

The Refresh button enables the HierarchyNavigatorRefreshButtonClick event to initiate in the BreadCrumb control.

![Refresh Button in WPF BreadCrumb control](Refresh-Button_images/Refresh-Button_img1.png)


{% tabs %}
{% highlight xaml %}
<locals:HierarchyNavigator HierarchyNavigatorRefreshButtonClick="HierarchyNavigatorRefreshButtonClick" />
{% endhighlight %}

{% highlight C# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.HierarchyNavigatorRefreshButtonClick += new EventHandler(HierarchyNavigatorRefreshButtonClick);

//Occurs when Refresh Button Click
private void HierarchyNavigatorRefreshButtonClick(object sender, EventArgs e)
{

}
    
{% endhighlight %}
{% endtabs %}

