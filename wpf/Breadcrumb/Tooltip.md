---
layout: post
title: Tooltip in WPF BreadCrumb | Syncfusion®
description: Tooltip in WPF BreadCrumb display contextual information for items, improving usability and enhancing navigation.
platform: wpf
control: BreadCrumb
documentation: ug
---

# Tooltip in WPF BreadCrumb

- A ToolTip can be displayed for each _HierarchyNavigatorItem_.
- Setting the `ShowToolTip` property to true in the BreadCrumb control will enable the ToolTips for all items.

{% tabs %}
{% highlight xaml %}

<syncfusion:HierarchyNavigator ShowToolTip="True" x:Name="hierarchyNavigator1" />

{% endhighlight %}
{% highlight C# %}

HierarchyNavigator hierarchyNavigatorControl1 = new HierarchyNavigator() { Height = 30 };
hierarchyNavigatorControl1.ShowToolTip = true;

{% endhighlight %}
{% endtabs %}

![Tooltip support in WPF BreadCrumb control](Tooltip_images/Tooltip_img1.png)



