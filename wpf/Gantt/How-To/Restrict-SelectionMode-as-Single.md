---
layout: post
title: Restrict SelectionMode as Single | Gantt | Wpf | Syncfusion
description: This section describes how to restrict the SelectionMode behavior as Single in GanttControl for WPF platform.
platform: wpf
control: Gantt
 documentation: ug
---

## Restrict SelectionMode as Single

To restrict the selection mode to single, set the ListBoxSelectionMode options of GanttGrid’s Model in the GanttControl loaded event. 

The following codes illustrate this

{% tabs %}
{% highlight xaml %}

…
<gantt:GanttControl x:Name="Gantt"
                    ItemsSource="{Binding TaskDetails}"
                    VisualStyle="Metro"
                    Loaded="Gantt_Loaded">
</gantt:GanttControl>
…

{% endhighlight  %}
{% highlight c# %}

…
private void Gantt_Loaded(object sender, RoutedEventArgs e)
{
    this.Gantt.GanttGrid.Model.Options.ListBoxSelectionMode = Syncfusion.Windows.Controls.Grid.GridSelectionMode.One;
}
…

{% endhighlight  %}
{% endtabs %}