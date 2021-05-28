---
layout: post
title: Restricting level selection| Hierarchical Navigator | Wpf | Syncfusion
description: Restricting level selection in Syncfusion Essential Studio WPF Hierarchy Navigator control, its elements and more.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Restricting level selection

You can restrict the number of levels that can be selected in a navigation path.

Assigning a value for the MaxDrillDown property (integer) in the HierarchyNavigator control will set the maximum level. The default value is -1, which allows all levels to be shown.

{% tabs %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();hierarchyNavigator.MaxDrillDownLevel = 2;
{% endhighlight %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator Name="hierarchyNavigator1" MaxDrillDownLevel="2" />
{% endhighlight %}
{% endtabs %}

