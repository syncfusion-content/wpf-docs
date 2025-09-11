---
layout: post
title: Drag and drop in WPF GanttControl | Syncfusion
description: Learn about drag and drop support in Syncfusion Essential Studio WPF GanttControl, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Drag and drop support in GanttControl
The WPF [GanttControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html) allows you to reorder rows and columns within the [GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttGrid.html) and rearrange nodes in the [GanttChart](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttChart.html) by dragging and dropping them. You can disable drag and drop by setting the [AllowDragDrop](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_AllowDragDrop) property to false. The default value is `true`.

![drag-and-drop-in-wpf-gantt-control](Drag-drop-images/drag-and-drop-in-wpf-gantt-control.gif)

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl" 
                         AllowDragDrop="False">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}
this.ganttControl.AllowDragDrop = false;
{% endhighlight  %}
{% endtabs %}

## Handle node drag starting in gantt grid
You can get the node details and handle whether the node can be draggable or not by using the [TreeGridNodeDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_TreeGridNodeDragStarting) event. This event will be triggered when the node is started dragging. The [TreeGridNodeDragStartingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDragStartingEventArgs.html) argument contains the [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDragStartingEventArgs.html#Syncfusion_Windows_Controls_Gantt_TreeGridNodeDragStartingEventArgs_Nodes) property which gets the nodes that contain the associated data while dragging the rows.

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         TreeGridNodeDragStarting="OnGanttControlTreeGridNodeDragStarting"> 
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}

this.ganttControl.TreeGridNodeDragStarting += OnGanttControlTreeGridNodeDragStarting;

...

private void OnGanttControlTreeGridNodeDragStarting(object sender, TreeGridNodeDragStartingEventArgs e)
{
    var nodes = e.Nodes;
    e.Cancel = true;
}

{% endhighlight  %}
{% endtabs %}

## Handle node dragging in gantt grid
You can get the dragging node details in gantt grid by using the [TreeGridNodeDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_TreeGridNodeDragging) event. This event will be continuously triggered when the node is being dragged. The [TreeGridNodeDraggingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDraggingEventArgs.html) argument contains the [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDraggingEventArgs.html#Syncfusion_Windows_Controls_Gantt_TreeGridNodeDraggingEventArgs_Nodes) property which gets the nodes that are being dragged.

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         TreeGridNodeDragging="OnGanttControlTreeGridNodeDragging">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}

this.ganttControl.TreeGridNodeDragging += OnGanttControlTreeGridNodeDragging;

...

private void OnGanttControlTreeGridNodeDragging(object sender, TreeGridNodeDraggingEventArgs e)
{
    var nodes = e.Nodes;
}

{% endhighlight  %}
{% endtabs %}

## Handle node drop in gantt grid
Using the [TreeGridNodeDrop](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_TreeGridNodeDrop) event you can get the dropping node details, target node, and you can handle whether the node can be dropped to the specific position or not. This event will trigger after dropping the node. The [TreeGridNodeDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDropEventArgs.html) argument contains the following properties.

* [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_TreeGridNodeDropEventArgs_Nodes) - Gets the item that contains the associated data.
* [TargetNode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_TreeGridNodeDropEventArgs_TargetNode) - Gets a value indicating the target node which is going to drop.
* [Position](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.TreeGridNodeDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_TreeGridNodeDropEventArgs_Position) - Gets the position where the dragged node is dropped relative to the target node.

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         TreeGridNodeDrop="OnGanttControlTreeGridNodeDrop">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}

this.ganttControl.TreeGridNodeDrop += OnGanttControlTreeGridNodeDrop;

...

private void OnGanttControlTreeGridNodeDrop(object sender, TreeGridNodeDropEventArgs e)
{
    var nodes = e.Nodes;
    var targetNode = e.TargetNode;
    e.Cancel = false;
}

{% endhighlight  %}
{% endtabs %}

## Handle drag and drop in gantt chart
You can get the dragging and dropping node details in gantt chart by using the [NodeDragDelta](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_NodeDragDelta) and [NodeDragCompleted](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_NodeDragCompleted) events. The [NodeDragAndDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html) argument contains the following properties.

* [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_Node) - Gets or sets the node.
* [HorizontalChange](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_HorizontalChange) - Gets or sets the horizontal change.
* [StartTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_StartTime) - Gets or sets the start time.
* [EndTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_EndTime) - Gets or sets the end time.
* [Start](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_Start) - Gets or sets the start.
* [End](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_End) - Gets or sets the end.
* [NodePresenter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.NodeDragAndDropEventArgs.html#Syncfusion_Windows_Controls_Gantt_NodeDragAndDropEventArgs_NodePresenter) - Gets the node parent.

### Handle node dragging in Gantt chart
{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         NodeDragDelta="OnGanttControlNodeDragDelta">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}

this.ganttControl.NodeDragDelta += OnGanttControlNodeDragDelta;

...

private void OnGanttControlNodeDragDelta(object sender, NodeDragAndDropEventArgs args)
{
    var node = args.Node;
}

{% endhighlight  %}
{% endtabs %}

### Handle node drop in gantt chart
{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         NodeDragCompleted="OnGanttControlNodeDragCompleted">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight c# %}

this.ganttControl.NodeDragCompleted += OnGanttControlNodeDragCompleted;

...

private void OnGanttControlNodeDragCompleted(object sender, NodeDragAndDropEventArgs args)
{
    var startTime = args.StartTime;
    var endTime = args.EndTime;
}

{% endhighlight  %}
{% endtabs %}