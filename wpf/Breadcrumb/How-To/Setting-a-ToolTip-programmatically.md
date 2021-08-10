---
layout: post
title: ToolTip programmatically in WPF Hierarchical Navigator | Syncfusion
description: Setting a tooltip programmatically in Syncfusion Essential Studio WPF Hierarchy Navigator control, its elements and more.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Setting a ToolTip programmatically

Setting the ShowToolTip Boolean property to true in the HierarchyNavigator control enables ToolTips for all items. By default, this property is set to false, preventing ToolTips from being shown.

{% tabs %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigatorControl1 = new HierarchyNavigator();
hierarchyNavigatorControl1.ShowToolTip = true;
{% endhighlight %}
{% highlight xaml %}
XAML<syncfusion:HierarchyNavigator Name="hierarchyNavigator1" ShowToolTip="True" />
{% endhighlight  %}
{% endtabs %}

