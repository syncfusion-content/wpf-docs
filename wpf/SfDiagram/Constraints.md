---
layout: post
title: Constraints | SfDiagram | wpf | Syncfusion
description: constraints
platform: wpf
control: SfDiagram
documentation: ug
---

## Constraints

Constraints are used to enable/disable certain behaviors of the diagram, Node and Connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (&, |, ~, <<, etc.). 

GraphConstraints

Graph constraints allow to enable or disable the following behaviors.

* Page Editing

* Line Bridging

* Zoom and Pan

* Undo Redo

The GraphConstraints property is used to enable or disable all the behaviors or certain behaviors of the SfDiagram control. This property is applicable to the entire SfDiagram control.

<table>
<tr>
<td>
Constraints</td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Disables all behaviors of the control.</td></tr>
<tr>
<td>
Zoomable</td><td>
Enables zooming behavior.</td></tr>
<tr>
<td>
PannableX</td><td>
Enables panning in the horizontal direction.</td></tr>
<tr>
<td>
PannableY</td><td>
Enables panning in the vertical direction.</td></tr>
<tr>
<td>
Pannable</td><td>
Enables panning behavior.</td></tr>
<tr>
<td>
PanRailsX</td><td>
Enables panning behavior on the x-axis in SfDiagram (horizontal panning).</td></tr>
<tr>
<td>
PanRailsY</td><td>
Enables panning actions on the y-axis in SfDiagram (vertical panning).</td></tr>
<tr>
<td>
Undoable</td><td>
Enables Redo or Undo behavior.</td></tr>
<tr>
<td>
Virtualize</td><td>
Enables Virtualizing behavior.</td></tr>
<tr>
<td>
Relationship</td><td>
Enables properties based on Node and Connector realactionships on dragging at run time.</td></tr>
<tr>
<td>
Events</td><td>
Enables all events of the control.</td></tr>
<tr>
<td>
Bridging</td><td>
Enables line bridging.</td></tr>
<tr>
<td>
Routing</td><td>
Enables line routing.</td></tr>
<tr>
<td>
AutoScroll</td><td>
Enables AutoScroll behavior</td></tr>
<tr>
<td>
PanRails</td><td>
Enables panning actions on the x-axis (horizontal panning) and y-axis (vertical panning) in SfDiagram.</td></tr>
<tr>
<td>
Selectable</td><td>
Enables Selecting behavior.</td></tr>
<tr>
<td>
Draggable</td><td>
Enables Dragging behavior.</td></tr>
<tr>
<td>
Connectable</td><td>
Enables Connecting behavior.</td></tr>
<tr>
<td>
Drop</td><td>
Enables Drop behavior.</td></tr>
<tr>
<td>
Resizable</td><td>
Enables Resizing behavior.</td></tr>
<tr>
<td>
Rotatable</td><td>
Enable Rotating behavior.</td></tr>
<tr>
<td>
ContextMenu</td><td>
Enables ContextMenu.</td></tr>
<tr>
<td>
Commands</td><td>
Enable Commands.</td></tr>
<tr>
<td>
DrawingTool</td><td>
Enagbles DrawingTool.</td></tr>
<tr>
<td>
PageEditing</td><td>
Enables PageEditing.</td></tr>
<tr>
<td>
Default</td><td>
Enables all behaviors of the control.</td></tr>
</table>


The default value for GraphConstraints property is Default.

Example 

The following example illustrates how to disable page editing

{% highlight C# %}

diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.PageEditing;

{% endhighlight %}

NodeConstraints

NodeConstraints allow to enable or disable the following behaviors of Node

* Selection

* Deletion

* Drag

* Resize

* Rotate

* Connect

* sDrag label

NodeConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Node of the SfDiagram control.

<table>
<tr>
<td>
Constraints</td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Disables all behaviors of the control.</td></tr>
<tr>
<td>
Selectable</td><td>
Enables a Node to be selected.</td></tr>
<tr>
<td>
Draggable</td><td>
Enables the Node to be gragged.</td></tr>
<tr>
<td>
Resizable</td><td>
Enables a Node to be resized.</td></tr>
<tr>
<td>
Rotatable</td><td>
Enables a Node to be rotated.</td></tr>
<tr>
<td>
InConnect</td><td>
Enables connecting to the incoming Connector.</td></tr>
<tr>
<td>
OutConnect</td><td>
Enables connecting the outgoing Connector.</td></tr>
<tr>
<td>
SnapToHorizontalLines</td><td>
Enables Nodes to snap to horizontal gridlines.</td></tr>
<tr>
<td>
SnapToVerticalLines</td><td>
Enables Nodes to snap to vertical gridlines.</td></tr>
<tr>
<td>
SnapAngle</td><td>
Enables snap while rotating.</td></tr>
<tr>
<td>
SnapToLines</td><td>
Enables Nodes to snap gridlines.</td></tr>
<tr>
<td>
Connectable</td><td>
Enables a Node to connect to the Connector.</td></tr>
<tr>
<td>
AllowPan</td><td>
Enables panning on the Node.</td></tr>
<tr>
<td>
InheritSnapping</td><td>
Enables to inherit the value of SnapToLines and SnapAngle from the SfDiagram by SnapConstraints in SnapSettings.</td></tr>
<tr>
<td>
InheritSnapToObject</td><td>
Enables to inherit the value to SnapToObject from the SfDiagram by SnapConstraints in SnapSettings.</td></tr>
<tr>
<td>
InheritPortVisibility</td><td>
Enables to inherit the value for PortVisibility from the SfDiagram.</td></tr>
<tr>
<td>
Inherit</td><td>
Enables to inherit all the Snapping, SnapToObject, and PortVisibility from the SfDiagram.</td></tr>
<tr>
<td>
AspectRatio</td><td>
Enables Node to be Resized in all the direction.</td></tr>
<tr>
<td>
Default</td><td>
Enables all behaviors of the control.</td></tr>
<tr>
<td>
ResizeNorthEast</td><td>
Enables or disables resizing Nodes in the north east.</td></tr>
<tr>
<td>
ResizeEast</td><td>
Enables or disables resizing Nodes in the east.</td></tr>
<tr>
<td>
ResizeSouthEast</td><td>
Enables or disables resizing Nodes in the south east.</td></tr>
<tr>
<td>
ResizeSouth</td><td>
Enables or disables resizing Nodes in the south.</td></tr>
<tr>
<td>
ResizeSouthWest</td><td>
Enables or disables resizing Nodes in the south west.</td></tr>
<tr>
<td>
ResizeWest</td><td>
Enables or disables resizing Nodes in the west.</td></tr>
<tr>
<td>
ResizeNorthWest</td><td>
Enables or disables resizing Nodes in the north west.</td></tr>
<tr>
<td>
ResizeNorth</td><td>
Enables or disables resizing Nodes in the north.</td></tr>
<tr>
<td>
Menu</td><td>
Enables or disables the Menu.</td></tr>
<tr>
<td>
InheritMenu</td><td>
Enables to inherit the Menu.</td></tr>
<tr>
<td>
Drag Annotation</td><td>
Enables or disables Node Annotation to be dragged.</td></tr>
</table>


The default value for NodeContraints property is Default.

Example

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

ConnectorConstraints

ConnectorConstraints allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection

* Deletion

* Drag

* Segment editing

* Bridging

* Label dragging

<table>
<tr>
<td>
Constraint</td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Disables a behavior of control.</td></tr>
<tr>
<td>
Selectable</td><td>
Enables to Connectors to be selected.</td></tr>
<tr>
<td>
SourceDraggable</td><td>
Enables the source end to be dragged.</td></tr>
<tr>
<td>
TargetDraggable</td><td>
Enables the target end of a Connector to be dragged.</td></tr>
<tr>
<td>
EndDraggable</td><td>
Enables both the source and target ends of a Connector to be dragged.</td></tr>
<tr>
<td>
Draggable</td><td>
Enables to Connectors to be dragged.</td></tr>
<tr>
<td>
EndThumbs</td><td>
Enables end points on line Connectors for editing, such as source points and target points.</td></tr>
<tr>
<td>
SegmentThumbs</td><td>
Enables control points and end points of every segment in a line Connector for editing.</td></tr>
<tr>
<td>
Thumbs</td><td>
Enables both EndThumbs and SegmentThumbs.</td></tr>
<tr>
<td>
Bridging</td><td>
Enables line bridging.</td></tr>
<tr>
<td>
Routing</td><td>
Enables line routing.</td></tr>
<tr>
<td>
SnapToHorizontalLines</td><td>
Enables Connectors to be snapped horizontal gridlines.</td></tr>
<tr>
<td>
SnapToVerticalLines</td><td>
Enables Connectors to be snapped vertical gridlines.</td></tr>
<tr>
<td>
SnapToLines</td><td>
Enables Connectors to be snapped to gridlines.</td></tr>
<tr>
<td>
InheritBridging</td><td>
Enables to inherit the bridging behavior from Node.</td></tr>
<tr>
<td>
InhertiRouting</td><td>
Enables to inherit the Routing behavior from Node.</td></tr>
<tr>
<td>
InheritSnapping</td><td>
Enables to inherit the Snapping behavior from Node.</td></tr>
<tr>
<td>
InheritSnapToObject</td><td>
Enables to inherit the SnapToObject behavior from Node.</td></tr>
<tr>
<td>
InheritSmoothness</td><td>
Enables to inherit the smoothness behavior from Node.</td></tr>
<tr>
<td>
Menu</td><td>
Enables or disables the Menu.</td></tr>
<tr>
<td>
InheritMenu</td><td>
Enables to inherit the Menu.</td></tr>
<tr>
<td>
InheritPortVisibility</td><td>
Enables to inherit the value for PortVisibility from the SfDiagram.</td></tr>
<tr>
<td>
Inherit</td><td>
Enables to inherit the connecting behavior from Node.</td></tr>
<tr>
<td>
DragAnnotation</td><td>
Enables or Disables Annotation to be dragged.</td></tr>
<tr>
<td>
InConnect</td><td>
Enables or Disables connecting to the incoming Connector.</td></tr>
<tr>
<td>
OutConnect</td><td>
Enables or Disables connecting the outgoing Connector.</td></tr>
<tr>
<td>
Connectable</td><td>
Enables or Disables a Node to connect to the Connector.</td></tr>
<tr>
<td>
Default</td><td>
Enables all behavior of the control.</td></tr>
</table>


Example

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

PortConstraints

You can enable or disable certain behaviors of port. They are as follows.

* Connect

PortConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Port of the SfDiagram control.

<table>
<tr>
<td>
Constraints</td><td>
Description</td></tr>
<tr>
<td>
Connectable</td><td>
Enables connection with the Connector.</td></tr>
<tr>
<td>
InConnect</td><td>
Enables connection with the incoming Connector.</td></tr>
<tr>
<td>
OutConnect</td><td>
Enables connection with the outgoing Connector.</td></tr>
<tr>
<td>
InheritConnectable</td><td>
Enables to inherit the connecting behavior from Node (incoming or outgoing).</td></tr>
<tr>
<td>
InheritPortVisibility</td><td>
Enables to inherit the value for PortVisibility from the Node.</td></tr>
<tr>
<td>
Inherit</td><td>
Enables to inherit both connecting behavior and the value for PortVisibility from the Node.</td></tr>
<tr>
<td>
None</td><td>
Disables all behaviors of the control.</td></tr>
<tr>
<td>
Default</td><td>
Enables all constraints.</td></tr>
</table>


The default value for PortConstraints property is Inherit.

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

SelectorConstraints

Selector visually represents the selected elements with certain editable thumbs. The visually of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer

* Rotator

* User handles

<table>
<tr>
<td>
Constraints</td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Disables the constraints for Selector.</td></tr>
<tr>
<td>
Resizer</td><td>
Enables or Disables the Resizer.</td></tr>
<tr>
<td>
Rotator</td><td>
Enables or Disables the Rotator.</td></tr>
<tr>
<td>
TooltipPosition</td><td>
Enables or Disables the Tooltip information based on the position of the selected Node.</td></tr>
<tr>
<td>
TooltipSize</td><td>
Enables or Disables the Tooltip information based on the size of the selected Node.</td></tr>
<tr>
<td>
TooltipAngle</td><td>
Enables or Disables the Tooltip information based on the angle of the selected Node.</td></tr>
<tr>
<td>
Tooltip</td><td>
Enables or Disables the Tooltip information based on the selected Node.</td></tr>
<tr>
<td>
QuickCommands</td><td>
Enables or Disables the QuickCommands.</td></tr>
<tr>
<td>
Default</td><td>
By default, position, size, and angle information are shown in the Tooltip and Quick Commands.</td></tr>
</table>


Example

The following code illustrates how to hide rotator.

{% highlight C# %}

(diagram.SelectedItems as SelectorViewModel).SelectorConstraints = (diagram.SelectedItems as  SelectorViewModel).SelectorConstraints & ~SelectorConstraints.Rotator;

{% endhighlight %}

SnapConstraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only horizontal or vertical gridlines

* Show both horizontal or vertical gridlines

* Show to either horizontal or vertical gridlines

* Show to both horizontal or vertical gridlines

<table>
<tr>
<td>
Constraints</td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Disable gridlines and disable snapping</td></tr>
<tr>
<td>
HorizontalLines</td><td>
Display horizontal gridlines.</td></tr>
<tr>
<td>
VerticalLines</td><td>
Show vertical gridlines.</td></tr>
<tr>
<td>
ShowLines</td><td>
Show both horizontal and vertical gridlines.</td></tr>
<tr>
<td>
SnapToHorizontalLines</td><td>
Snap to horizontal gridlines.</td></tr>
<tr>
<td>
SnapToVerticalLines</td><td>
Snap to vertical gridlines.</td></tr>
<tr>
<td>
Rotation</td><td>
Enable rotation behavior.</td></tr>
<tr>
<td>
SnapToLines</td><td>
Enable both horizontal and vertical lines.</td></tr>
<tr>
<td>
All</td><td>
Show and snap to both horizontal and vertical gridlines.</td></tr>
</table>

Example

The following code illustrates how to show only horizontal gridlines

{% highlight C# %}

diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToHorizontalLines;

{% endhighlight %}

Inherit behaviors

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

Bitwise Operations

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In the section, Bitwise Operations are illustrated by using Node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

Add Operation

You can add or enable multiple values at a time	 by using Bitwise ‘|’ (OR) operator.

{% highlight C# %}

node.Constraints = NodeConstraints.Selectable | NodeConstraints.Rotatable;

{% endhighlight %}

In the above example, you can do both the selection and rotation.

Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

{% highlight C# %}

node.Constraints = node.Constraints & ~(NodeConstraints.Rotatable);

{% endhighlight %}

In the above example, Rotation is disabled but other constraints are enabled.

Check Operation

You can check any value by using Bitwise ‘&’ (AND) operator.

{% highlight C# %}

if ((node.Constraints & (NodeConstraints.Rotatable)) == (NodeConstraints.Rotatable))

{% endhighlight %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.

