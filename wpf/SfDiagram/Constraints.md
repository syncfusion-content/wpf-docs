---
layout: post
title: Enable/Disable the optional features.
description: How to enable/disable the optional features?
platform: wpf
control: SfDiagram
documentation: ug
---

#Constraints

`Constraints` are used to enable/disable certain behaviors of the diagram, Node and Connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (&, |, ~, <<, etc.). 
[Bitwise Operations](#bitwise-operations).

##GraphConstraints

Graph constraints allow to enable or disable the following behaviors.

* Page Editing
* Line Bridging
* Zoom and Pan
* Undo Redo

The GraphConstraints property is used to enable or disable all the behaviors or certain behaviors of the SfDiagram control. This property is applicable to the entire SfDiagram control.

| Constraints | Description |
|---|---|
| None | Disables all behaviors of the control. |
| Zoomable |  Enables zooming behavior. |
| PannableX | Enables panning in the horizontal direction. |
| PannableY | Enables panning in the vertical direction. |
| Pannable | Enables panning behavior. | 
| PanRailsX | Enables panning behavior on the x-axis in SfDiagram (horizontal panning). |
| PanRailsY | Enables panning actions on the y-axis in SfDiagram (vertical panning). |
| Undoable | Enables Redo or Undo behavior. |
| Virtualize | Enables Virtualizing behavior. |
| Relationship | Enables properties based on Node and Connector realactionships on dragging at run time. |
| Events | Enables all events of the control. |
| Bridging | Enables line bridging. |
| Routing | Enables line routing. |
| AutoScroll | Enables AutoScroll behavior |
| PanRails | Enables panning actions on the x-axis (horizontal panning) and y-axis (vertical panning) in SfDiagram. |
| Selectable | Enables Selecting behavior. |
| Draggable | Enables Dragging behavior. |
| Connectable | Enables Connecting behavior. |
| Drop | Enables Drop behavior. |
| Resizable | Enables Resizing behavior. |
| Rotatable | Enable Rotating behavior. |
| ContextMenu | Enables ContextMenu. |
| Commands | Enable Commands. |
| DrawingTool | Enagbles DrawingTool. |
| PageEditing | Enables PageEditing. |
| Default | Enables all behaviors of the control. |

The default value for GraphConstraints property is `Default`.

**Example** 

The following example illustrates how to disable page editing

{% highlight C# %}

diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.PageEditing;

{% endhighlight %}

##NodeConstraints

NodeConstraints allow to enable or disable the following behaviors of Node

* Selection
* Deletion
* Drag
* Resize
* Rotate
* Connect
* Annotation Dragging

NodeConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Node of the SfDiagram control.

| Constraints | Description |
|---|---|
| None | Disables all behaviors of the control. |
| Selectable | Enables a Node to be selected. |
| Draggable | Enables the Node to be gragged. |
| Resizable | Enables a Node to be resized. |
| Rotatable |Enables a Node to be rotated. |
| InConnect | Enables connecting to the incoming Connector. |
| OutConnect | Enables connecting the outgoing Connector. |
| SnapToHorizontalLines | Enables Nodes to snap to horizontal gridlines. |
| SnapToVerticalLines | Enables Nodes to snap to vertical gridlines. |
| SnapAngle | Enables snap while rotating. |
| SnapToLines | Enables Nodes to snap gridlines. |
| Connectable | Enables a Node to connect to the Connector. |
| AllowPan | Enables panning on the Node. |
| InheritSnapping | Enables to inherit the value of SnapToLines and SnapAngle from the SfDiagram by SnapConstraints in SnapSettings. |
| InheritSnapToObject | Enables to inherit the value to SnapToObject from the SfDiagram by SnapConstraints in SnapSettings. |
| InheritPortVisibility | Enables to inherit the value for PortVisibility from the SfDiagram. |
| Inherit | Enables to inherit all the Snapping, SnapToObject, and PortVisibility from the SfDiagram. |
| AspectRatio | Enables Node to be Resized in all the direction. |
| Default | Enables all behaviors of the control. |
| ResizeNorthEast | Enables or disables resizing Nodes in the north east. |
| ResizeEast | Enables or disables resizing Nodes in the east. |
| ResizeSouthEast | Enables or disables resizing Nodes in the south east. |
| ResizeSouth | Enables or disables resizing Nodes in the south. |
| ResizeSouthWest | Enables or disables resizing Nodes in the south west. |
| ResizeWest | Enables or disables resizing Nodes in the west. |
| ResizeNorthWest | Enables or disables resizing Nodes in the north west. |
| ResizeNorth | Enables or disables resizing Nodes in the north. |
| Menu | Enables or disables the Menu. |
| InheritMenu | Enables to inherit the Menu. |
| Drag Annotation | Enables or disables Node Annotation to be dragged. |


The default value for NodeContraints property is `Default`.

**Example**

The following code illustrates how to disable rotation.

{% highlight C# %}

ObservableCollection<Node> nodes = new ObservableCollection<Node>();

Node node = new Node()
{
  Constraints = NodeConstraints.Default & ~NodeConstraints.Rotatable,
  UnitWidth = 50,
  UnitHeight = 50,
  OffsetX = 100,
  OffsetY = 100,
  Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
  ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

##ConnectorConstraints

ConnectorConstraints allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection
* Deletion
* Drag
* Segment editing
* Bridging
* Annotation dragging

| Constraint | Description |
|---|---|
| None | Disables a behavior of control. |
| Selectable | Enables to Connectors to be selected. |
| SourceDraggable | Enables the source end to be dragged. |
| TargetDraggable | Enables the target end of a Connector to be dragged. |
| EndDraggable | Enables both the source and target ends of a Connector to be dragged. |
| Draggable | Enables to Connectors to be dragged. |
| EndThumbs | Enables end points on line Connectors for editing, such as source points and target points. |
| SegmentThumbs | Enables control points and end points of every segment in a line Connector for editing. |
| Thumbs | Enables both EndThumbs and SegmentThumbs. |
| Bridging | Enables line bridging. |
| Routing | Enables line routing. |
| SnapToHorizontalLines | Enables Connectors to be snapped horizontal gridlines. |
| SnapToVerticalLines | Enables Connectors to be snapped vertical gridlines. |
| SnapToLines | Enables Connectors to be snapped to gridlines. |
| InheritBridging | Enables to inherit the bridging behavior from Node. |
| InhertiRouting | Enables to inherit the Routing behavior from Node. |
| InheritSnapping | Enables to inherit the Snapping behavior from Node. |
| InheritSnapToObject | Enables to inherit the SnapToObject behavior from Node. |
| InheritSmoothness | Enables to inherit the smoothness behavior from Node. |
| Menu | Enables or disables the Menu. |
| InheritMenu | Enables to inherit the Menu. |
| InheritPortVisibility | Enables to inherit the value for PortVisibility from the SfDiagram. |
| Inherit | Enables to inherit the connecting behavior from Node. |
| DragAnnotation | Enables or Disables Annotation to be dragged. |
| InConnect | Enables or Disables connecting to the incoming Connector. |
| OutConnect | Enables or Disables connecting the outgoing Connector. |
| Connectable | Enables or Disables a Node to connect to the Connector. |
| Default | Enables all behavior of the control. |



**Example**

The following code illustrates how to disable selection.

{% highlight C# %}

ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();

Connector connector1 = new Connector()
{
	Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.Selectable
};

connectors.Add(connector1);
diagram.Connectors = connectors;

{% endhighlight %}

##PortConstraints

You can enable or disable certain behaviors of port. They are as follows.

* Connect

PortConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Port of the SfDiagram control.

| Constraints | Description |
|---|---|
| Connectable | Enables connection with the Connector. |
| InConnect | Enables connection with the incoming Connector. |
| OutConnect | Enables connection with the outgoing Connector. |
| InheritConnectable | Enables to inherit the connecting behavior from Node (incoming or outgoing). |
| InheritPortVisibility | Enables to inherit the value for PortVisibility from the Node. |
| Inherit | Enables to inherit both connecting behavior and the value for PortVisibility from the Node. |
| None | Disables all behaviors of the control. |
| Default | Enables all constraints. |


The default value for PortConstraints property is `Inherit`.

Example

The following code illustrates how to disable creating connections with a port.

{% highlight C# %}

Node node = new Node()
{
	Ports = new ObservableCollection<INodePort>()
	{
		new NodePort()
		{
			Constraints = PortConstraints.None
		}
	},
	UnitWidth = 50,
	UnitHeight = 50,
	OffsetX = 100,
	OffsetY = 100,
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

##SelectorConstraints

Selector visually represents the selected elements with certain editable thumbs. The visually of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer
* Rotator
* Quick Commands


| Constraints | Description |
|---|---|
| None | Disables the constraints for Selector. |
| Resizer | Enables or Disables the Resizer. |
| Rotator | Enables or Disables the Rotator. |
| TooltipPosition | Enables or Disables the Tooltip information based on the position of the selected Node. |
| TooltipSize | Enables or Disables the Tooltip information based on the size of the selected Node. |
| TooltipAngle | Enables or Disables the Tooltip information based on the angle of the selected Node. |
| Tooltip | Enables or Disables the Tooltip information based on the selected Node. |
| QuickCommands | Enables or Disables the QuickCommands. |
| Default | By default, position, size, and angle information are shown in the Tooltip and Quick Commands. |


**Example**

The following code illustrates how to hide rotator.

{% highlight C# %}

(diagram.SelectedItems as SelectorViewModel).SelectorConstraints = (diagram.SelectedItems as  SelectorViewModel).SelectorConstraints & ~SelectorConstraints.Rotator;

{% endhighlight %}

##SnapConstraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only Horizontal or Vertical Gridlines
* Show both Horizontal or Vertical Gridlines
* Show to either Horizontal or Vertical Gridlines
* Show to both Horizontal or vertical gridlines


| Constraints | Description |
|---|---|
| None | Disable gridlines and disable snapping |
| HorizontalLines | Display horizontal gridlines. |
| VerticalLines | Show vertical gridlines. |
| ShowLines | Show both horizontal and vertical gridlines. |
| SnapToHorizontalLines | Snap to horizontal gridlines. |
| SnapToVerticalLines | Snap to vertical gridlines. |
| Rotation | Enable rotation behavior. |
| SnapToLines | Enable both horizontal and vertical lines. |
| All | Show and snap to both horizontal and vertical gridlines. |


**Example**

The following code illustrates how to show only Horizontal Gridlines

{% highlight C# %}

diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToHorizontalLines;

{% endhighlight %}

###Inherit behaviors

Some of the behaviors can be defined through both the specific object (Node/Connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram.

{% highlight C# %}

diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;

ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();

Connector connector1 = new Connector()
{
	SourcePoint=new Point(100,100),
	TargetPoint=new Point(200,200),
	Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging
};

connectors.Add(connector1);
diagram.Connectors = connectors;

{% endhighlight %}

##Bitwise Operations

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In the section, Bitwise Operations are illustrated by using Node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

###Add Operation

You can add or enable multiple values at a time	 by using Bitwise ‘|’ (OR) operator.

{% highlight C# %}

node.Constraints = NodeConstraints.Selectable | NodeConstraints.Rotatable;

{% endhighlight %}

In the above example, you can do both the selection and rotation.

###Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

{% highlight C# %}

node.Constraints = node.Constraints & ~(NodeConstraints.Rotatable);

{% endhighlight %}

In the above example, Rotation is disabled but other constraints are enabled.

###Check Operation

You can check any value by using Bitwise ‘&’ (AND) operator.

{% highlight C# %}

if ((node.Constraints & (NodeConstraints.Rotatable)) == (NodeConstraints.Rotatable))

{% endhighlight %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.

