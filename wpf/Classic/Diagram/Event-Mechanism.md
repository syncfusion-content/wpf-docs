---
layout: post
title: Event Mechanism in WPF Diagram Control | Syncfusion
description: Learn here all about Event Mechanism support in Syncfusion WPF Diagram (classic) control, its elements and more details.
platform: wpf
control: Diagram
 documentation: ug
---

# Event Mechanism in WPF Diagram (classic)

This section describes several events triggered and handled while using Essential Diagram WPF in the following topic:

## Events for Nodes and Connections

Diagram control has several events which respond to several actions performed on nodes and connections.

The various events and their descriptions are explained in the following table.



<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
NodeClick</td><td>
Raised when the node is clicked.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeDoubleClick</td><td>
Raised when the node is clicked twice in succession.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeStartLabelEdit</td><td>
Raised when the label editing on the node is started.<br>Event cannot be canceled.</td><td>
NewLabelValue – The new label value.OldLabelValue – the old label value.Node - Node on which event is raised.</td></tr>
<tr>
<td>
NodeLabelChanged</td><td>
Raised when the node's label value is changed.<br>Event cannot be canceled.</td><td>
NewLabelValue – The new label value.OldLabelValue – the old label value.Node - Node on which event is raised.</td></tr>
<tr>
<td>
NodeDragStart</td><td>
Raised when the node is dragged.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeDragEnd</td><td>
Raised when the drag operation on node is complete.Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeResizing</td><td>
Raised when the resize operation is being performed.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeResized</td><td>
Raised after the node is resized.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeRotationChanging</td><td>
Raised when the node is being rotated.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeRotationChanged</td><td>
Raised after the node is rotated.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
ConnectorDoubleClick</td><td>
Raised when the Connector is clicked twice in succession.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.Head Node – Head Node of the connector.Tail Node – Tail Node of the connector.</td></tr>
<tr>
<td>
ConnectorStartLabelEdit</td><td>
Raised when the label editing on the Connector is started.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.Head Node – Head Node of the connector.Tail Node – Tail Node of the connector.OldLabelValue – the old label value.</td></tr>
<tr>
<td>
ConnectorLabelChanged</td><td>
Raised when the connector's label value is changed.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.Head Node – Head Node of the connector.Tail Node – Tail Node of the connector.OldLabelValue – the old label value.NewLabelValue – The new label value.</td></tr>
<tr>
<td>
ConnectorDragStart</td><td>
Raised when either ends of the connector is dragged.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.FixedNodeEnd – Node on which the connection is fixed.MovableNodeEnd – The old Node on which the Connector was connected.</td></tr>
<tr>
<td>
ConnectorDragEnd</td><td>
Raised when the drag operation is complete.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.FixedNodeEnd – Node on which the connection is fixed.HitNodeEnd – The new node on which the Connector is getting connected.</td></tr>
<tr>
<td>
NodeDrop</td><td>
Raised when a shape from the SymbolPalette is dropped on the page.<br>Event cannot be canceled.</td><td>
DroppedNode – The new node just dropped from SymbolPalette.SymbolPaletteItemName – The name of the SymbolPalette item, which is dropped on the page.</td></tr>
<tr>
<td>
HeadNodeChanged</td><td>
Raised when the HeadNode of the connector is changed<br>Event cannot be canceled.</td><td>
Connector – The connector whose HeadNode is changed.PreviousNode – The old Node on which the HeadNode of the Connector was connector.CurrentNode - The new Node on which the HeadNode of the Connector is connector.</td></tr>
<tr>
<td>
TailNodeChanged</td><td>
Raised when the TailNode of the connector is changed.<br>Event cannot be canceled.</td><td>
Connector – The connector whose HeadNode is changed.PreviousNode – The old Node on which the TailNode of the Connector was connector.CurrentNode - The new Node on which the TailNode of the Connector is connector.</td></tr>
<tr>
<td>
ConnectorDrop</td><td>
Raised when the connector is dropped on the page.<br>Event cannot be canceled.</td><td>
DroppedConnector – Connector on which the event is raised.</td></tr>
<tr>
<td>
BeforeConnectionCreate</td><td>
Raised when a new connection is being made.<br>Event cannot be canceled.</td><td>
Connector – The connector whose HeadNode is changed.</td></tr>
<tr>
<td>
AfterConnectionCreate</td><td>
Raised after the connection has been made.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.FixedNodeEnd – Node on which the connection is fixed.HitNodeEnd – The new node on which the Connector is getting connected.</td></tr>
<tr>
<td>
NodeSelected</td><td>
Raised when a node is selected.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeUnSelected</td><td>
Raised when a node is not selected.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
NodeDeleting</td><td>
Raised before a node is deleted from the model.<br>Event cannot be canceled.</td><td>
DeletedNode – Node which is going to get deleted.</td></tr>
<tr>
<td>
NodeDeleted</td><td>
Raised when a node is deleted from the model.<br>Event cannot be canceled.</td><td>
DeletedNode – Node which is deleted.</td></tr>
<tr>
<td>
ConnectorDeleting</td><td>
Raised before a line connector is deleted from the model.<br>Event cannot be canceled.</td><td>
DeletedLineConnector – LineConnector which is getting deleted.</td></tr>
<tr>
<td>
ConnectorDeleted</td><td>
Raised when a line connector is deleted from the model.<br>Event cannot be canceled.</td><td>
DeletedLineConnector – LineConnector which is deleted.</td></tr>
<tr>
<td>
PreviewNodeDrop</td><td>
Raised before a node is dropped on the page.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.</td></tr>
<tr>
<td>
PreviewConnectorDrop</td><td>
Raised before a line connector is dropped on the page.<br>Event cannot be canceled.</td><td>
Connector – Connector on which the event is raised.</td></tr>
<tr>
<td>
NodeMoved(event is fired before nudge operation is completed)</td><td>
Raised when the nudge operation on node is completed.<br>Event cannot be canceled.</td><td>
Node – Node on which event is raised.oldOffset – The old offset value before nudge operation.newOffset – The new offset value after performing nudge operation.</td></tr>
</table>


The events can be specified using DiagramView object as follows.

* For instance, NodeClick event can be specified in the following way.
{% highlight html %}




<sfdiagram:DiagramView Name="diagramView" NodeClick="diagramView_NodeClick">

</sfdiagram:DiagramView> 


{% endhighlight  %}
{% highlight c# %}




diagramView.NodeClick += new NodeEventHandler(diagramView_NodeClick);
{% endhighlight  %}
{% highlight vbnet %}






AddHandler diagramView.NodeClick, AddressOf diagramView_NodeClick

{% endhighlight %}

* And then the event handler can be specified in the code behind as follows.
{% highlight c# %}




//Event Handler

void diagramView_NodeClick(object sender, NodeRoutedEventArgs evtArgs)

{

//user specified code

}

{% endhighlight %}
{% highlight vbnet %}





'Event Handler

Private Sub diagramView_NodeClick(ByVal sender As Object, ByVal evtArgs As NodeRoutedEventArgs)

     'user specified code

End Sub

{% endhighlight %}

* As another example, the ConnectorDoubleClick event can be specified in the following way.
{% highlight html %}




<sfdiagram:DiagramView Name="diagramView" ConnectorDoubleClick="diagramView_ConnectorDoubleClick">

</sfdiagram:DiagramView>

{% endhighlight %}
{% highlight c# %}




diagramView.ConnectorDoubleClick += new ConnChangedEventHandler(diagramView_ConnectorDoubleClick);

{% endhighlight  %}
{% highlight vbnet %}




AddHandler diagramView.ConnectorDoubleClick, AddressOf diagramView_ConnectorDoubleClick

{% endhighlight %}

And then the event handler can be specified in the code behind as follows.
{% highlight c# %}




// Event Handler

void diagramView_ConnectorDoubleClick(object sender, ConnRoutedEventArgs evtArgs)

{

// user specified code

}

{% endhighlight %}
{% highlight vbnet %}





'Event Handler

Private Sub diagramView_ConnectorDoubleClick(ByVal sender As Object, ByVal evtArgs As ConnRoutedEventArgs)

     'user specified code

End Sub

{% endhighlight  %}

* NodeMoved and NodeDrop events
{% highlight c# %}




diagramView.NodeMoved += new NodeNudgeEventHandler(diagramView_NodeMoved);

void diagramView_NodeMoved(object sender, NodeNudgeEventArgs evtArgs)

{

}



diagramView.NodeDrop += new NodeNudgeEventHandler(diagramView_LineMoved);

void diagramView_NodeDrop(object sender, NodeNudgeEventArgs evtArgs)

{

}

{% endhighlight  %}
{% highlight vbnet %}





Private diagramView.NodeMoved += New NodeNudgeEventHandler(AddressOf diagramView_NodeMoved)

Private Sub diagramView_NodeMoved(ByVal sender As Object, ByVal evtArgs As NodeNudgeEventArgs)

End Sub



Private diagramView.NodeDrop += New NodeNudgeEventHandler(AddressOf diagramView_LineMoved)

Private Sub diagramView_NodeDrop(ByVal sender As Object, ByVal evtArgs As NodeNudgeEventArgs)

End Sub
{% endhighlight  %}

