---
layout: post
title: Restricting-level-selection
description: restricting level selection
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Restricting level selection

You can restrict the number of levels that can be selected in a navigation path.

Assigning a value for the MaxDrillDown property (integer) in the HierarchyNavigator control will set the maximum level. The default value is -1, which allows all levels to be shown.


{% highlight c# %}
C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();hierarchyNavigator.MaxDrillDownLevel = 2;
{% endhighlight %}

{% highlight xml %}
XAML
<syncfusion:HierarchyNavigator Name="hierarchyNavigator1" MaxDrillDownLevel="2" />
{% endhighlight %}


