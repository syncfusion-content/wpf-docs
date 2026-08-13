---
layout: post
title: Selected Item Changed in WPF HierarchyNavigator | Syncfusion®
description: Selected Item Changed in WPF HierarchyNavigator notifies applications of selection updates, enabling responsive actions.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Selected Item Changed in WPF HierarchyNavigator	

Users can handle selected item changed by using the methods Command (ICommand) property or HierarchyNavigatorSelectedItemChanged event in Hierarchy Navigator control.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator HierarchyNavigatorSelectedItemChanged="HierarchyNavigatorSelectedItemChanged" />
{% endhighlight  %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>hierarchyNavigator.HierarchyNavigatorSelectedItemChanged += new HierarchyNavigatorSelectedItemChangedEventHandler(HierarchyNavigatorSelectedItemChanged);

private void HierarchyNavigatorSelectedItemChanged(object sender, HierarchyNavigatorSelectedItemChangedEventArgs e)
{
<br> 
    //Occurs when Selected Item Changed
	}
{% endhighlight  %}
{% endtabs %}

Passing the argument “HierarchyNavigator item” in a method called SelectNavigationItem can change the selected item.


{% highlight c# %}



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.SelectNavigationItem(hierarchyitem);


{% endhighlight  %}
