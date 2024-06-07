---
layout: post
title: Filtering and sorting in WPF Gantt control | Syncfusion
description: Learn about Filtering and sorting support in Syncfusion Essential Studio WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Filtering and sorting support in Gantt control

## Filtering
Gantt control provides Excel-inspired filtering UI with various filter options to filter the data easily. Filtering can be enabled by setting the `AllowFiltering` property of `GanttControl` to `true`. This allows to open the filter UI by clicking the filter icon on the column header to filter the nodes. The default value of `AllowFiltering` property is `false`.

![WPF Gantt control filtering](Filtering-sorting-images/Filtering.gif)

{% tabs %}
{% highlight xaml %}
<sync:GanttControl x:Name="control" 
                   AllowFiltering="True"
                   ItemsSource="{Binding TaskCollection}"> 
 <sync:GanttControl.DataContext>
    <local:ViewModel/>
 </sync:GanttControl.DataContext>          
</Sync:GanttControl>
{% endhighlight %}
{% highlight c# %}

    //Initializing Gantt
    GanttControl control = new GanttControl();
    control.DataContext = new ViewModel();
    control.SetBinding(GanttControl.ItemsSourceProperty,"TaskCollection");
    control.AllowFiltering = true;

{% endhighlight  %}
{% endtabs %}

N> By default, the WPF GanttControl utilizes the `Extended` filter level. This setting ensures that all parent nodes of any node that meets the filter criteria are shown, regardless of whether those parent nodes themselves satisfy the filter conditions.

## Sorting
Gantt control allows you to sort the column data either in ascending or descending order. When sorting is applied, the rows are rearranged based on sort criteria. You can the data by touching or clicking the column header. Sorting can be enabled by setting the `AllowSorting` property to `true`.

![WPF Gantt control sorting](Filtering-sorting-images/Sorting.gif)

{% tabs %}
{% highlight xaml %}
<sync:GanttControl x:Name="control"
                   AllowSorting="True"
                   ItemsSource="{Binding TaskCollection}"> 
 <sync:GanttControl.DataContext>
    <local:ViewModel/>
 </sync:GanttControl.DataContext>          
</Sync:GanttControl>
{% endhighlight %}
{% highlight c# %}

    //Initializing Gantt
    GanttControl control = new GanttControl();
    control.DataContext = new ViewModel();
    control.SetBinding(GanttControl.ItemsSourceProperty,"TaskCollection");
    control.AllowSorting = true;

{% endhighlight  %}
{% endtabs %}

N> By default, the `AllowSorting` property is set to `false`.