---
layout: post
title: Restrict SelectionMode as Single | Gantt | Wpf | Syncfusion
description: This section describes how to restrict the SelectionMode behavior as Single in GanttControl for WPF platform.
platform: wpf
control: Gantt
documentation: ug
---

# Restrict SelectionMode as Single in WPF Gantt

To restrict the selection mode to single, set the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_SelectionMode) of Gantt in the [GanttControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html) loaded event. 

The following codes illustrate this

{% tabs %}
{% highlight xaml %}

…
<gantt:GanttControl x:Name="Gantt"
                    ItemsSource="{Binding TaskDetails}"
                    Loaded="OnGanttLoaded">
</gantt:GanttControl>
…

{% endhighlight  %}
{% highlight c# %}

…
private void OnGanttLoaded(object sender, RoutedEventArgs e)
{
     this.Gantt.SelectionMode = GanttSelectionMode.Single;
}
…

{% endhighlight  %}
{% endtabs %}