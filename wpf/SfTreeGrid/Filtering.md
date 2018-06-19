---
layout: post
title: Filtering support in SfTreeGrid.
description: How to filter the nodes programmatically in SfTreeGrid .
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Filtering

## Overview

SfTreeGrid provides support for programmatic filtering. It can be achieved by setting [SfTreeGrid.View.Filter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridView~Filter.html) delegate and calling [SfTreeGrid.View.RefreshFilter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridView~RefreshFilter.html) method.

{% tabs %}
{% highlight c# %}

public bool FilerNodes(object o)
{
    var data = o as Employee;

    if (data.Salary > 70000)
        return true;
    return false;
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    treeGrid.View.Filter = FilerNodes;
    treeGrid.View.RefreshFilter();
}

{% endhighlight %}
{% endtabs %}

Here, `FilterNodes` delegate filters the data based on Salary. `FilterNodes` delegate is assigned to [SfTreeGrid.View.Filter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridView~Filter.html) predicate to filter the tree grid. After that, [SfTreeGrid.View.RefreshFilter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridView~RefreshFilter.html) method is called to refresh the nodes. If the node satisfies the filter conditions, true will be returned. Else false will be returned.

![](Filtering_images/Filtering_img1.png)

While filtering, if the node satisfies filter condition, [IsFiltered](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeNode~IsFiltered.html) property of [TreeNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeNode.html) will be set as false. Else, it will be true. If `IsFiltered` value is True, the node will not be displayed in view, else it will be displayed in view.

N> SfTreeGrid refreshes the filtering on property change if [SfTreeGrid.LiveNodeUpdateMode ](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~LiveNodeUpdateMode.html)property is set as `AllowDataShaping`.

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/FilteringDemo-587565594).

## FilterLevel

You can filter the nodes based on level by using [SfTreeGrid.FilterLevel](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~FilterLevel.html) property.

{% tabs %}
{% highlight c# %}

treeGrid.FilterLevel = FilterLevel.All;

{% endhighlight %}
{% endtabs %}

* Root - Filter will be applied to root nodes only in SfTreeGrid.

* All - Filter will be applied to all the nodes in SfTreeGrid.

* Extended - Filter will be applied to all the nodes. If a node matches the filter condition, it’s all ancestors will also be displayed, even though parent node does not match the filter condition.

**Root**

Filter will be applied to root nodes only in SfTreeGrid. For other nodes, `IsFiltered` value will be false and they always will be displayed in view.

**All**

Filter will be applied to all the nodes in SfTreeGrid. If the parent node does not match the filter condition, filter will not be applied for child nodes. Else, filter will be applied to its child nodes also.

**Extended**

Filter will be applied to all the nodes. If a node matches the filter condition, it’s all ancestors will also be displayed, even though parent node does not match the filter condition and parent node’s `IsFiltered` value will be set as false.

Note> It is also possible to change `FilterLevel` at runtime.

## Clear filters

You can clear the filters applied in tree grid by setting `SfTreeGrid.View.Filter` delegate as null and calling `SfTreeGrid.View.RefreshFilter` method.

{% tabs %}
{% highlight c# %}

treeGrid.View.Filter = null;
treeGrid.View.RefreshFilter();

{% endhighlight %}
{% endtabs %}

**HasVisibleChildNodes**

You can find whether particular node has child node(s) displayed in a view (matches filtering criteria) or not by using [HasVisibleChildNodes](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeNode~HasVisibleChildNodes.html) property in [TreeNode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeNode.html).

{% tabs %}
{% highlight c# %}

var treeNode=treeGrid.View.Nodes[0];
var hasVisibleChildNodes = treeNode.HasVisibleChildNodes;

{% endhighlight %}
{% endtabs %}
