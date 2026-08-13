---
layout: post
title: Setting Tooltips in WPF HierarchyNavigator | Syncfusion®
description: Setting Tooltips in WPF HierarchyNavigator allows informative hints to be displayed programmatically, improving usability and guidance.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Setting Tooltips in WPF HierarchyNavigator

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

