---
layout: post
title: How to handle selected item changes in WPF Hierarchical Navigator | Syncfusion
description: Learn how to handle selected item changes in Syncfusion® WPF Hierarchical Navigator control using the HierarchyNavigatorSelectedItemChanged event and command support.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---


# How to handle selected item changes in WPF Hierarchical Navigator

You can handle selected item changes in the Hierarchical Navigator control by using the `Command` (`ICommand`) property or the `HierarchyNavigatorSelectedItemChanged` event.

{% tabs %}

{% highlight xaml %}
<syncfusion:HierarchyNavigator
    HierarchyNavigatorSelectedItemChanged="HierarchyNavigatorSelectedItemChanged" />
{% endhighlight %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.HierarchyNavigatorSelectedItemChanged +=
    new HierarchyNavigatorSelectedItemChangedEventHandler(
        HierarchyNavigatorSelectedItemChanged);

private void HierarchyNavigatorSelectedItemChanged(
    object sender,
    HierarchyNavigatorSelectedItemChangedEventArgs e)
{
    // Occurs when the selected item changes.
}
{% endhighlight %}

{% endtabs %}

You can change the selected item programmatically by passing a `HierarchyNavigatorItem` to the `SelectNavigationItem` method.

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.SelectNavigationItem(hierarchyItem);
{% endhighlight %}