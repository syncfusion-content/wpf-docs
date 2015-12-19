# Constraints

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
Constraints<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disables all behaviors of the control.<br/><br/></td></tr>
<tr>
<td>
Zoomable<br/><br/></td><td>
Enables zooming behavior.<br/><br/></td></tr>
<tr>
<td>
PannableX<br/><br/></td><td>
Enables panning in the horizontal direction.<br/><br/></td></tr>
<tr>
<td>
PannableY<br/><br/></td><td>
Enables panning in the vertical direction.<br/><br/></td></tr>
<tr>
<td>
Pannable<br/><br/></td><td>
Enables panning behavior.<br/><br/></td></tr>
<tr>
<td>
PanRailsX<br/><br/></td><td>
Enables panning behavior on the x-axis in SfDiagram (horizontal panning).<br/><br/></td></tr>
<tr>
<td>
PanRailsY<br/><br/></td><td>
Enables panning actions on the y-axis in SfDiagram (vertical panning).<br/><br/></td></tr>
<tr>
<td>
Undoable<br/><br/></td><td>
Enables Redo or Undo behavior.<br/><br/></td></tr>
<tr>
<td>
Virtualize<br/><br/></td><td>
Enables Virtualizing behavior.<br/><br/></td></tr>
<tr>
<td>
Relationship<br/><br/></td><td>
Enables properties based on Node and Connector realactionships on dragging at run time.<br/><br/></td></tr>
<tr>
<td>
Events<br/><br/></td><td>
Enables all events of the control.<br/><br/></td></tr>
<tr>
<td>
Bridging<br/><br/></td><td>
Enables line bridging.<br/><br/></td></tr>
<tr>
<td>
Routing<br/><br/></td><td>
Enables line routing.<br/><br/></td></tr>
<tr>
<td>
AutoScroll<br/><br/></td><td>
Enables AutoScroll behavior<br/><br/></td></tr>
<tr>
<td>
PanRails<br/><br/></td><td>
Enables panning actions on the x-axis (horizontal panning) and y-axis (vertical panning) in SfDiagram.<br/><br/></td></tr>
<tr>
<td>
Selectable<br/><br/></td><td>
Enables Selecting behavior.<br/><br/></td></tr>
<tr>
<td>
Draggable<br/><br/></td><td>
Enables Dragging behavior.<br/><br/></td></tr>
<tr>
<td>
Connectable<br/><br/></td><td>
Enables Connecting behavior.<br/><br/></td></tr>
<tr>
<td>
Drop<br/><br/></td><td>
Enables Drop behavior.<br/><br/></td></tr>
<tr>
<td>
Resizable<br/><br/></td><td>
Enables Resizing behavior.<br/><br/></td></tr>
<tr>
<td>
Rotatable<br/><br/></td><td>
Enable Rotating behavior.<br/><br/></td></tr>
<tr>
<td>
ContextMenu<br/><br/></td><td>
Enables ContextMenu.<br/><br/></td></tr>
<tr>
<td>
Commands<br/><br/></td><td>
Enable Commands.<br/><br/></td></tr>
<tr>
<td>
DrawingTool<br/><br/></td><td>
Enagbles DrawingTool.<br/><br/></td></tr>
<tr>
<td>
PageEditing<br/><br/></td><td>
Enables PageEditing.<br/><br/></td></tr>
<tr>
<td>
Default<br/><br/></td><td>
Enables all behaviors of the control.<br/><br/></td></tr>
</table>
The default value for GraphConstraints property is Default.

Example 

The following example illustrates how to disable page editing

<table>
<tr>
<td>
diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.PageEditing;<br/><br/><br/><br/></td></tr>
</table>
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
Constraints<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disables all behaviors of the control.<br/><br/></td></tr>
<tr>
<td>
Selectable<br/><br/></td><td>
Enables a Node to be selected.<br/><br/></td></tr>
<tr>
<td>
Draggable<br/><br/></td><td>
Enables the Node to be gragged.<br/><br/></td></tr>
<tr>
<td>
Resizable<br/><br/></td><td>
Enables a Node to be resized.<br/><br/></td></tr>
<tr>
<td>
Rotatable<br/><br/></td><td>
Enables a Node to be rotated.<br/><br/></td></tr>
<tr>
<td>
InConnect<br/><br/></td><td>
Enables connecting to the incoming Connector.<br/><br/></td></tr>
<tr>
<td>
OutConnect<br/><br/></td><td>
Enables connecting the outgoing Connector.<br/><br/></td></tr>
<tr>
<td>
SnapToHorizontalLines<br/><br/></td><td>
Enables Nodes to snap to horizontal gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapToVerticalLines<br/><br/></td><td>
Enables Nodes to snap to vertical gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapAngle<br/><br/></td><td>
Enables snap while rotating.<br/><br/></td></tr>
<tr>
<td>
SnapToLines<br/><br/></td><td>
Enables Nodes to snap gridlines.<br/><br/></td></tr>
<tr>
<td>
Connectable<br/><br/></td><td>
Enables a Node to connect to the Connector.<br/><br/></td></tr>
<tr>
<td>
AllowPan<br/><br/></td><td>
Enables panning on the Node.<br/><br/></td></tr>
<tr>
<td>
InheritSnapping<br/><br/></td><td>
Enables to inherit the value of SnapToLines and SnapAngle from the SfDiagram by SnapConstraints in SnapSettings.<br/><br/></td></tr>
<tr>
<td>
InheritSnapToObject<br/><br/></td><td>
Enables to inherit the value to SnapToObject from the SfDiagram by SnapConstraints in SnapSettings.<br/><br/></td></tr>
<tr>
<td>
InheritPortVisibility<br/><br/></td><td>
Enables to inherit the value for PortVisibility from the SfDiagram.<br/><br/></td></tr>
<tr>
<td>
Inherit<br/><br/></td><td>
Enables to inherit all the Snapping, SnapToObject, and PortVisibility from the SfDiagram.<br/><br/></td></tr>
<tr>
<td>
AspectRatio<br/><br/></td><td>
Enables Node to be Resized in all the direction.<br/><br/></td></tr>
<tr>
<td>
Default<br/><br/></td><td>
Enables all behaviors of the control.<br/><br/></td></tr>
<tr>
<td>
ResizeNorthEast<br/><br/></td><td>
Enables or disables resizing Nodes in the north east.<br/><br/></td></tr>
<tr>
<td>
ResizeEast<br/><br/></td><td>
Enables or disables resizing Nodes in the east.<br/><br/></td></tr>
<tr>
<td>
ResizeSouthEast<br/><br/></td><td>
Enables or disables resizing Nodes in the south east.<br/><br/></td></tr>
<tr>
<td>
ResizeSouth<br/><br/></td><td>
Enables or disables resizing Nodes in the south.<br/><br/></td></tr>
<tr>
<td>
ResizeSouthWest<br/><br/></td><td>
Enables or disables resizing Nodes in the south west.<br/><br/></td></tr>
<tr>
<td>
ResizeWest<br/><br/></td><td>
Enables or disables resizing Nodes in the west.<br/><br/></td></tr>
<tr>
<td>
ResizeNorthWest<br/><br/></td><td>
Enables or disables resizing Nodes in the north west.<br/><br/></td></tr>
<tr>
<td>
ResizeNorth<br/><br/></td><td>
Enables or disables resizing Nodes in the north.<br/><br/></td></tr>
<tr>
<td>
Menu<br/><br/></td><td>
Enables or disables the Menu.<br/><br/></td></tr>
<tr>
<td>
InheritMenu<br/><br/></td><td>
Enables to inherit the Menu.<br/><br/></td></tr>
<tr>
<td>
Drag Annotation<br/><br/></td><td>
Enables or disables Node Annotation to be dragged.<br/><br/></td></tr>
</table>
The default value for NodeContraints property is Default.

Example

The following code illustrates how to disable rotation.

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>Constraints = NodeConstraints.Default & ~NodeConstraints.Rotatable,<br/><br/>UnitWidth = 50,<br/><br/>UnitHeight = 50,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
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
<br/>Constraint<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disables a behavior of control.<br/><br/></td></tr>
<tr>
<td>
Selectable<br/><br/></td><td>
Enables to Connectors to be selected.<br/><br/></td></tr>
<tr>
<td>
SourceDraggable<br/><br/></td><td>
Enables the source end to be dragged.<br/><br/></td></tr>
<tr>
<td>
TargetDraggable<br/><br/></td><td>
Enables the target end of a Connector to be dragged.<br/><br/></td></tr>
<tr>
<td>
EndDraggable<br/><br/></td><td>
Enables both the source and target ends of a Connector to be dragged.<br/><br/></td></tr>
<tr>
<td>
Draggable<br/><br/></td><td>
Enables to Connectors to be dragged.<br/><br/></td></tr>
<tr>
<td>
EndThumbs<br/><br/></td><td>
Enables end points on line Connectors for editing, such as source points and target points.<br/><br/></td></tr>
<tr>
<td>
SegmentThumbs<br/><br/></td><td>
Enables control points and end points of every segment in a line Connector for editing.<br/><br/></td></tr>
<tr>
<td>
Thumbs<br/><br/></td><td>
Enables both EndThumbs and SegmentThumbs.<br/><br/></td></tr>
<tr>
<td>
Bridging<br/><br/></td><td>
Enables line bridging.<br/><br/></td></tr>
<tr>
<td>
Routing<br/><br/></td><td>
Enables line routing.<br/><br/></td></tr>
<tr>
<td>
SnapToHorizontalLines<br/><br/></td><td>
Enables Connectors to be snapped horizontal gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapToVerticalLines<br/><br/></td><td>
Enables Connectors to be snapped vertical gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapToLines<br/><br/></td><td>
Enables Connectors to be snapped to gridlines.<br/><br/></td></tr>
<tr>
<td>
InheritBridging<br/><br/></td><td>
Enables to inherit the bridging behavior from Node.<br/><br/></td></tr>
<tr>
<td>
InhertiRouting<br/><br/></td><td>
Enables to inherit the Routing behavior from Node.<br/><br/></td></tr>
<tr>
<td>
InheritSnapping<br/><br/></td><td>
Enables to inherit the Snapping behavior from Node.<br/><br/></td></tr>
<tr>
<td>
InheritSnapToObject<br/><br/></td><td>
Enables to inherit the SnapToObject behavior from Node.<br/><br/></td></tr>
<tr>
<td>
InheritSmoothness<br/><br/></td><td>
Enables to inherit the smoothness behavior from Node.<br/><br/></td></tr>
<tr>
<td>
Menu<br/><br/></td><td>
Enables or disables the Menu.<br/><br/></td></tr>
<tr>
<td>
InheritMenu<br/><br/></td><td>
Enables to inherit the Menu.<br/><br/></td></tr>
<tr>
<td>
InheritPortVisibility<br/><br/></td><td>
Enables to inherit the value for PortVisibility from the SfDiagram.<br/><br/></td></tr>
<tr>
<td>
Inherit<br/><br/></td><td>
Enables to inherit the connecting behavior from Node.<br/><br/></td></tr>
<tr>
<td>
DragAnnotation<br/><br/></td><td>
Enables or Disables Annotation to be dragged.<br/><br/></td></tr>
<tr>
<td>
InConnect<br/><br/></td><td>
Enables or Disables connecting to the incoming Connector.<br/><br/></td></tr>
<tr>
<td>
OutConnect<br/><br/></td><td>
Enables or Disables connecting the outgoing Connector.<br/><br/></td></tr>
<tr>
<td>
Connectable<br/><br/></td><td>
Enables or Disables a Node to connect to the Connector.<br/><br/></td></tr>
<tr>
<td>
Default<br/><br/></td><td>
Enables all behavior of the control.<br/><br/></td></tr>
</table>
Example

The following code illustrates how to disable selection.

<table>
<tr>
<td>
ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();<br/><br/>Connector connector1 = new Connector()<br/><br/>{<br/><br/>Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.Selectable<br/><br/>};<br/><br/>connectors.Add(connector1);<br/><br/>diagram.Connectors = connectors;<br/><br/><br/><br/></td></tr>
</table>
PortConstraints

You can enable or disable certain behaviors of port. They are as follows.

* Connect

PortConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Port of the SfDiagram control.

<table>
<tr>
<td>
Constraints<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
Connectable<br/><br/></td><td>
Enables connection with the Connector.<br/><br/></td></tr>
<tr>
<td>
InConnect<br/><br/></td><td>
Enables connection with the incoming Connector.<br/><br/></td></tr>
<tr>
<td>
OutConnect<br/><br/></td><td>
Enables connection with the outgoing Connector.<br/><br/></td></tr>
<tr>
<td>
InheritConnectable<br/><br/></td><td>
Enables to inherit the connecting behavior from Node (incoming or outgoing).<br/><br/></td></tr>
<tr>
<td>
InheritPortVisibility<br/><br/></td><td>
Enables to inherit the value for PortVisibility from the Node.<br/><br/></td></tr>
<tr>
<td>
Inherit<br/><br/></td><td>
Enables to inherit both connecting behavior and the value for PortVisibility from the Node.<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disables all behaviors of the control.<br/><br/></td></tr>
<tr>
<td>
Default<br/><br/></td><td>
Enables all constraints.<br/><br/></td></tr>
</table>
The default value for PortConstraints property is Inherit.

Example

The following code illustrates how to disable creating connections with a port.

<table>
<tr>
<td>
Node node = new Node()<br/><br/>{<br/><br/>Ports = new ObservableCollection<INodePort>()<br/><br/>{<br/><br/>new NodePort()<br/><br/>{<br/><br/>Constraints = PortConstraints.None<br/><br/>}<br/><br/>},<br/><br/>UnitWidth = 50,<br/><br/>UnitHeight = 50,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
SelectorConstraints

Selector visually represents the selected elements with certain editable thumbs. The visually of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer
* Rotator
* User handles
<table>
<tr>
<td>
<br/>Constraints<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disables the constraints for Selector.<br/><br/></td></tr>
<tr>
<td>
Resizer<br/><br/></td><td>
Enables or Disables the Resizer.<br/><br/></td></tr>
<tr>
<td>
Rotator<br/><br/></td><td>
Enables or Disables the Rotator.<br/><br/></td></tr>
<tr>
<td>
TooltipPosition<br/><br/></td><td>
Enables or Disables the Tooltip information based on the position of the selected Node.<br/><br/></td></tr>
<tr>
<td>
TooltipSize<br/><br/></td><td>
Enables or Disables the Tooltip information based on the size of the selected Node.<br/><br/></td></tr>
<tr>
<td>
TooltipAngle<br/><br/></td><td>
Enables or Disables the Tooltip information based on the angle of the selected Node.<br/><br/></td></tr>
<tr>
<td>
Tooltip<br/><br/></td><td>
Enables or Disables the Tooltip information based on the selected Node.<br/><br/></td></tr>
<tr>
<td>
QuickCommands<br/><br/></td><td>
Enables or Disables the QuickCommands.<br/><br/></td></tr>
<tr>
<td>
Default<br/><br/></td><td>
By default, position, size, and angle information are shown in the Tooltip and Quick Commands.<br/><br/></td></tr>
</table>
Example

The following code illustrates how to hide rotator.

<table>
<tr>
<td>
(diagram.SelectedItems as SelectorViewModel).SelectorConstraints = (diagram.SelectedItems as  SelectorViewModel).SelectorConstraints & ~SelectorConstraints.Rotator;<br/><br/><br/><br/></td></tr>
</table>
SnapConstraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only horizontal or vertical gridlines
* Show both horizontal or vertical gridlines
* Show to either horizontal or vertical gridlines
* Show to both horizontal or vertical gridlines
<table>
<tr>
<td>
<br/>Constraints<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
None<br/><br/></td><td>
Disable gridlines and disable snapping<br/><br/></td></tr>
<tr>
<td>
HorizontalLines<br/><br/></td><td>
Display horizontal gridlines.<br/><br/></td></tr>
<tr>
<td>
VerticalLines<br/><br/></td><td>
Show vertical gridlines.<br/><br/></td></tr>
<tr>
<td>
ShowLines<br/><br/></td><td>
Show both horizontal and vertical gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapToHorizontalLines<br/><br/></td><td>
Snap to horizontal gridlines.<br/><br/></td></tr>
<tr>
<td>
SnapToVerticalLines<br/><br/></td><td>
Snap to vertical gridlines.<br/><br/></td></tr>
<tr>
<td>
Rotation<br/><br/></td><td>
Enable rotation behavior.<br/><br/></td></tr>
<tr>
<td>
SnapToLines<br/><br/></td><td>
Enable both horizontal and vertical lines.<br/><br/></td></tr>
<tr>
<td>
All<br/><br/></td><td>
Show and snap to both horizontal and vertical gridlines.<br/><br/></td></tr>
</table>
Example

The following code illustrates how to show only horizontal gridlines

<table>
<tr>
<td>
diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToHorizontalLines;<br/><br/><br/><br/></td></tr>
</table>
Inherit behaviors

Some of the behaviors can be defined through both the specific object (Node/Connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram.

<table>
<tr>
<td>
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;<br/><br/>ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();<br/><br/>Connector connector1 = new Connector()<br/><br/>{<br/><br/>SourcePoint=new Point(100,100),<br/><br/>TargetPoint=new Point(200,200),<br/><br/>Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging<br/><br/>};<br/><br/>connectors.Add(connector1);<br/><br/>diagram.Connectors = connectors;<br/><br/><br/><br/></td></tr>
</table>
Bitwise Operations

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In the section, Bitwise Operations are illustrated by using Node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

Add Operation

You can add or enable multiple values at a timeby using Bitwise ‘|’ (OR) operator.

<table>
<tr>
<td>
<br/>node.Constraints = NodeConstraints.Selectable | NodeConstraints.Rotatable;<br/><br/><br/><br/></td></tr>
</table>
In the above example, you can do both the selection and rotation.

Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

<table>
<tr>
<td>
node.Constraints = node.Constraints & ~(NodeConstraints.Rotatable);<br/><br/><br/><br/></td></tr>
</table>
In the above example, Rotation is disabled but other constraints are enabled.

Check Operation

You can check any value by using Bitwise ‘&’ (AND) operator.

<table>
<tr>
<td>
if ((node.Constraints & (NodeConstraints.Rotatable)) == (NodeConstraints.Rotatable))<br/><br/><br/><br/></td></tr>
</table>
In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.

