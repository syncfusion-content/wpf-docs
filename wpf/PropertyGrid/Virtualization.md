---
layout: post
title: Virtualization of the items in WPF PropertyGrid control | Syncfusion
description: This section describes how large sets of data can be loaded in PropertyGrid control using Virtualization.
platform: wpf
control: CheckListBox
documentation: ug
---

# Virtualization in WPF PropertyGrid

You can reduce the loading time of `PropertyGrid` items regardless of items count by UI Virtualization support which is enabled by default in `PropertyGrid`. It allows the users to load large sets of data without affecting loading or scrolling performance.

{% tabs %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.IsVirtualizing = true;
propertyGrid.EnableGrouping = true;
propertyGrid.PropertyExpandMode = PropertyExpandModes.NestedMode;
propertyGrid.SelectedObject = new Button();

{% endhighlight %}
{% highlight XAML %}

<syncfusion:PropertyGrid x:Name="propertyGrid" IsVirtualizing="True" PropertyExpandMode="NestedMode" EnableGrouping="True">
    <syncfusion:PropertyGrid.SelectedObject>
        <Button />
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% endtabs %}

![PropertyGrid in the Virtualization mode](Virtualization-images/Virtualization.png)

N> When Virtualization is enabled, you can only load a set of items in view at a time.  
