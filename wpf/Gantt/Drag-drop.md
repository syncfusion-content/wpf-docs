---
layout: post
title: Drag and drop in WPF Gantt control | Syncfusion
description: Learn about Drag and drop support in Syncfusion Essential Studio WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Drag and drop support in Gantt control
Gantt control allows you to reorder rows and columns within the Gantt control by dragging and dropping them. You can enable drag and drop by setting `AllowDragDrop` property of `GanttControl` to `true`. The default value of is `AllowDragDrop` is `true`.

![WPF Gantt control drag and drop](Drag-drop-images/Dragdrop.gif)

{% tabs %}
{% highlight xaml %}

<sync:GanttControl x:Name="control" 
                   AllowDragDrop="False"
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
    control.AllowDragDrop = false;

{% endhighlight  %}
{% endtabs %}

## Handle node drag starting
You can get the node details and handle whether the node can be draggable or not by using the `TreeGridNodeDragStarting` event. This event will be triggered when the node is started dragging. The `TreeGridNodeDragStartingEventArgs` argument contains the `Nodes` property which gets the nodes that contain the associated data while dragging the rows.

{% tabs %}
{% highlight c# %}

ganttControl.TreeGridNodeDragStarting += OnGanttControlTreeGridNodeDragStarting;

...

private void OnGanttControlTreeGridNodeDragStarting(object sender, TreeGridNodeDragStartingEventArgs e)
{
    var nodes = e.Nodes;
    e.Cancel = true;
}

{% endhighlight  %}
{% endtabs %}

## Handle node dragging
You can get the dragging node details by using the `TreeGridNodeDragging` event. This event will be continuously triggered when the node is being dragged. The `TreeGridNodeDraggingEventArgs` argument contains the `Nodes` property which gets the nodes that are being dragged.

{% tabs %}
{% highlight c# %}

ganttControl.TreeGridNodeDragging += OnGanttControlTreeGridNodeDragging;

...

private void OnGanttControlTreeGridNodeDragging(object sender, TreeGridNodeDraggingEventArgs e)
{
    var nodes = e.Nodes;
}

{% endhighlight  %}
{% endtabs %}

## Handle node drop
Using the `TreeGridNodeDrop` event you can get the dropping node details, target node, and you can handle whether the node can be dropped to the specific position or not. This event will trigger after dropping the node. The `TreeGridNodeDropEventArgs` argument contains the following properties.

`Nodes` - Gets the item that contains the associated data while dragging the rows.
`TargetNode` - Gets a value indicating the target node which is going to drop.

{% tabs %}
{% highlight c# %}

ganttControl.TreeGridNodeDrop += OnGanttControlTreeGridNodeDrop;

...

private void OnGanttControlTreeGridNodeDrop(object sender, TreeGridNodeDropEventArgs e)
{
    var nodes = e.Nodes;
    var targetNode = e.TargetNode;
    e.Cancel = false;
}

{% endhighlight  %}
{% endtabs %}