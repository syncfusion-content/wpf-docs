---
layout: post
title: Restricting Level Selection in WPF HierarchyNavigator | Syncfusion®
description: RestrictingLevel selection in WPF HierarchyNavigator enables control over selectable hierarchy levels to match application requirements.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Restricting Level Selection in WPF HierarchyNavigator

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

