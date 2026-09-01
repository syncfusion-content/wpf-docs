---
layout: post
title: How to restrict level selection in WPF Hierarchical Navigator | Syncfusion
description: Learn how to restrict level selection in Syncfusion® WPF Hierarchical Navigator control using the MaxDrillDownLevel property to limit navigation depth.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# How to restrict level selection in WPF Hierarchical Navigator

You can restrict the number of levels that can be selected in a navigation path.

Set the `MaxDrillDownLevel` property in the `HierarchyNavigator` control to specify the maximum level that can be selected. The default value is `-1`, which allows all levels to be displayed.

{% tabs %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.MaxDrillDownLevel = 2;
{% endhighlight %}

{% highlight xaml %}
<syncfusion:HierarchyNavigator
    Name="hierarchyNavigator"
    MaxDrillDownLevel="2" />
{% endhighlight %}

{% endtabs %}
