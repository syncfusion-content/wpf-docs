---
layout: post
title: Selected-Hierarchy-Navigator-Item-Changed
description: selected hierarchy navigator item changed
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Selected Hierarchy Navigator Item Changed

Users can handle selected item changed by using the methods Command (ICommand) property or HierarchyNavigatorSelectedItemChanged event in Hierarchy Navigator control.

{% highlight xml %}
XAML
<syncfusion:HierarchyNavigator HierarchyNavigatorSelectedItemChanged="HierarchyNavigatorSelectedItemChanged" />

{% endhighlight %}

{% highlight c# %}
C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.HierarchyNavigatorSelectedItemChanged += new HierarchyNavigatorSelectedItemChangedEventHandler(HierarchyNavigatorSelectedItemChanged);

{% endhighlight %}

{% highlight c# %}
C#private void HierarchyNavigatorSelectedItemChanged(object sender, HierarchyNavigatorSelectedItemChangedEventArgs e)
{
     //Occurs when Selected Item Changed
}

{% endhighlight %}

Passing the argument “HierarchyNavigator item” in a method called SelectNavigationItem can change the selected item.

{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.SelectNavigationItem(hierarchyitem);

{% endhighlight %}

