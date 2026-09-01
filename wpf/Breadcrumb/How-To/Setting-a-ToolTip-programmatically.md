---
layout: post
title: How to enable tooltips in WPF Hierarchical Navigator | Syncfusion
description: Learn how to enable tooltips in Syncfusion® WPF Hierarchical Navigator control using the ShowToolTip property to display item information.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# How to enable tooltips in WPF Hierarchical Navigator

Set the `ShowToolTip` property to `true` in the `HierarchyNavigator` control to display tooltips for all items. By default, this property is set to `false`.

{% tabs %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.ShowToolTip = true;
{% endhighlight %}

{% highlight xaml %}
<syncfusion:HierarchyNavigator
    Name="hierarchyNavigator1"
    ShowToolTip="True" />
{% endhighlight %}

{% endtabs %}