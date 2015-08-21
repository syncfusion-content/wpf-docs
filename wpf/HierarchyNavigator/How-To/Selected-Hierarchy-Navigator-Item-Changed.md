---
layout: post
title: Selected-Hierarchy-Navigator-Item-Changed
description: selected hierarchy navigator item changed
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Selected Hierarchy Navigator Item Changed

Users can handle selected item changed by using the methods Command (ICommand) property or HierarchyNavigatorSelectedItemChanged event in Hierarchy Navigator control.

{% highlight xml %}
<syncfusion:HierarchyNavigator HierarchyNavigatorSelectedItemChanged="HierarchyNavigatorSelectedItemChanged" />
{% endhighlight  %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.HierarchyNavigatorSelectedItemChanged += new HierarchyNavigatorSelectedItemChangedEventHandler(HierarchyNavigatorSelectedItemChanged);

private void HierarchyNavigatorSelectedItemChanged(object sender, HierarchyNavigatorSelectedItemChangedEventArgs e){<br>     //Occurs when Selected Item Changed}
{% endhighlight  %}

Passing the argument “HierarchyNavigator item” in a method called SelectNavigationItem can change the selected item.
{% highlight c# %}



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.SelectNavigationItem(hierarchyitem);


{% endhighlight  %}
