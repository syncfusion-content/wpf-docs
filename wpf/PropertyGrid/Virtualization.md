---
layout: post
title: Virtualization in WPF PropertyGrid control | Syncfusion
description: Learn about Virtualization support in Syncfusion Essential Studio WPF PropertyGrid control, its elements and more.
platform: wpf
control: CheckListBox
 documentation: ug
---

# Virtualization in WPF PropertyGrid

By loading only items that are within viewport, UI virtualization allows `PropertyGrid` to load faster. Virtualization is enabled by default.

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

N> When Virtualization is enabled, only properties that are in viewport will be in loaded state.  
