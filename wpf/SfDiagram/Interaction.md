# Interaction

**Selection******

Selector provides a visual representation of selected elements. It behaves like a container and enables you to update the size, position, and rotation angle of the selected elements through interaction and programmatically. Single or multiple elements can be selected at a time.

**Single** **Selection******

An element can be selected by clicking that element. During single click, all previously selected items are cleared. The following image shows how the selected elements are visually represented.

![](Interaction_images/Interaction_img1.jpeg)
****************************![](Interaction_images/Interaction_img2.jpeg)
****

****![](Interaction_images/Interaction_img3.jpeg)
****************![](Interaction_images/Interaction_img4.jpeg)
****

**********Selecting** **a** **Group******

When a child element of any Group is clicked, its contained Group is selected instead of the child element. With consecutive clicks on the selected element, selection is changed from top to bottom in the hierarchy of parent Group to its children.

**Multiple** **Selection******

Multiple elements can be selected with the following ways.

1. Ctrl+Click

During single click, any existing item in the selection list be clearied, and only the item clicked recently is there in the selection list. To avoid cleaning the old selected item, Ctrl key must be on hold when clicking.

2. Selection rectangle / Rubber band selection

Clicking and dragging the Diagram area allows to create a rectangular region. The elements that are covered under the rectangular region are selected at the end.

Multiple selected elements are visually represented as shown.

![](Interaction_images/Interaction_img5.jpeg)


**Select****/****Unselect** **the** **elements** **programmatically**

The IsSelected Property is used to select/unselect the elements at runtime.

The following code example illustrates how to select/unselect an item through programmatically.

<table>
<tr>
<td>
// Selects an elements <br/><br/>node.IsSelected = true;<br/><br/>// Unselect an element<br/><br/>node.IsSelected = false;<br/><br/><br/><br/></td></tr>
</table>
**Drag******

* An object can be dragged by clicking and dragging it. When multiple elements are selected, dragging any one of the selected elements move every selected element.
* While dragging, the objects are snapped towards the nearest objects to make better alignments. For better alignments, refer to [Snapping](http://help.syncfusion.com/js/Diagram/Gridlines#snapping "Snapping").

![](Interaction_images/Interaction_img6.jpeg)


**Resize******

* Selector is surrounded by eight thumbs. When dragging these thumbs, selected items can be resized smaller or larger.
* When one corner of the selector is dragged, opposite corner is in a static position.
* While resizing, the objects are snapped towards the nearest objects to make better alignments. For better alignments, refer to [Snapping](http://help.syncfusion.com/js/Diagram/Gridlines#snapping "Snapping").

![](Interaction_images/Interaction_img7.jpeg)


**Rotate******

* A rotate handler is placed above the selector. Clicking and dragging the handler in a circular direction lead to rotate the Node.
* The Node is rotated with reference to the static pivot point.
* Pivot thumb (thumb at the middle of the Node) appears while rotating the Node to represent the static point.
* For more information about pivot, refer to [Position](http://help.syncfusion.com/js/Diagram/Node#position "Position").

![](Interaction_images/Interaction_img8.jpeg)


**Connection** **Editing**

* Each segment of a selected Connector is editable with some specific handles/thumbs.****

**End** **point** **handles******

Source and target points of the selected Connectors are represented with two handles. Clicking and dragging those handles help you to adjust the source and target points.

![](Interaction_images/Interaction_img9.jpeg)


**Straight** **segment** **editing** 

* End point of each straight segment is represented by a thumb that enables to edit the segment.
* Any number of new segments can be inserted into a straight line by clicking that when shift and ctrl keys are pressed. (Ctrl+Shift+Click).
* Straight segments can be removed by clicking the segment end point, when ctrl and shift keys are pressed. (Ctrl+Shift+Click).

**Orthogonal** **thumbs******

* Orthogonal thumbs allow to adjust the length of adjacent segments by clicking and dragging it.****

****![](Interaction_images/Interaction_img10.jpeg)
****

***** When necessary, some segments are added or removed automatically, when dragging the segment. This is to maintain proper routing of orthogonality between segments.****

****![](Interaction_images/Interaction_img11.jpeg)
****

**Bezier** **thumbs******

* Bezier segments are annotated with two thumbs to represent the control points. Control points of the curve can be configured by clicking and dragging the control thumbs.****

****![](Interaction_images/Interaction_img12.jpeg)
****

**Drag** **and** **Drop** **Nodes** **over** **other** **elements******

Diagram provides support to drop a node/connector over another node/connector. Drop event is raised to notify that an element is dropped over another one and it is disabled by default. It can enabled with the constraints property. The following code illustrates how to enable **dropping**.

<table>
<tr>
<td>
(diagram.Info as IGraphInfo).ItemDropEvent += MainWindow_ItemDropEvent;<br/><br/>ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>UnitHeight = 100,<br/><br/>UnitWidth = 100,<br/><br/>OffsetX = 400,<br/><br/>OffsetY = 400,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.Resources["shapestyle"] as Style,<br/><br/>Constraints = NodeConstraints.Default |  NodeConstraints.AllowDrop<br/><br/>};<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(500, 500),<br/><br/>TargetPoint = new Point(600, 600),<br/><br/>Constraints = ConnectorConstraints.Default | ConnectorConstraints.AllowDrop<br/><br/>};<br/><br/>ObservableCollection<Group> groups = new ObservableCollection<Group>();<br/><br/>Group group = new Group()<br/><br/>{<br/><br/>Nodes = new ObservableCollection<Node><br/><br/>{<br/><br/>Node<br/><br/>},<br/><br/>Connectors = new ObservableCollection<Connector><br/><br/>{<br/><br/>connector<br/><br/>},<br/><br/>};<br/><br/>groups.Add(group);<br/><br/>diagram.Groups = groups;<br/><br/>Node node1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 300,<br/><br/>OffsetY = 300,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.Resources["shapestyle"] as Style,<br/><br/>Constraints=NodeConstraints.Default | NodeConstraints.AllowDrop<br/><br/>};<br/><br/>nodes.Add(node1);<br/><br/>diagram.Nodes = nodes;<br/><br/>private void MainWindow_ItemDropEvent(object sender, ItemDropEventArgs args)<br/><br/>{<br/><br/>//Source - Node<br/><br/>//Target – Group<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
**Zoom** **pan******

* When a large Diagram is loaded, only certain portion of the Diagram is visible. The remaining portions are clipped. Clipped portions can be explored by scrolling the scrollbars or panning the Diagram.
* Diagram can be zoomed in or out by using Ctrl + mouse wheel.

**Keyboard******

Diagram provides support to interact with the elements with key gestures. By default, some in-built commands are bound with a relevant set of key combinations.

The following table illustrates List of Commands with key Gesture

<table>
<tr>
<td>
**Shortcut** **Key******<br/><br/></td><td>
**Command******<br/><br/></td><td>
**Description******<br/><br/></td></tr>
<tr>
<td>
Ctrl + A<br/><br/></td><td>
Select all<br/><br/></td><td>
Select all the Nodes/Connectors in diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + C<br/><br/></td><td>
Copy<br/><br/></td><td>
Copy the selected elements in the diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + X<br/><br/></td><td>
Cut<br/><br/></td><td>
Cut the selected elements in the diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + V<br/><br/></td><td>
Paste<br/><br/></td><td>
Paste the cut or copy the elements in the diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + Z<br/><br/></td><td>
Undo<br/><br/></td><td>
Undo(Reverse the last editing action performed on diagram)<br/><br/></td></tr>
<tr>
<td>
Ctrl + Y<br/><br/></td><td>
Redo<br/><br/></td><td>
Redo(Restores the last editing action when no other actions have occurred since the last undo on diagram)****<br/><br/></td></tr>
<tr>
<td>
Ctrl + D<br/><br/></td><td>
Duplicate<br/><br/></td><td>
Copies the selected element from the diagram and pastes the copied element into the diagram.<br/><br/></td></tr>
<tr>
<td>
Delete<br/><br/></td><td>
Delete<br/><br/></td><td>
Delete the selected elements in the diagram<br/><br/></td></tr>
<tr>
<td>
LeftArrow<br/><br/></td><td>
MoveLeft<br/><br/></td><td>
MoveLeft (move the selected elements towards left by one pixel)<br/><br/></td></tr>
<tr>
<td>
RightArrow<br/><br/></td><td>
MoveRight<br/><br/></td><td>
MoveRight (move the selected elements towards right by one pixel)<br/><br/></td></tr>
<tr>
<td>
UpArrow<br/><br/></td><td>
MoveUp<br/><br/></td><td>
MoveUp (move the selected elements towards up by one pixel)<br/><br/></td></tr>
<tr>
<td>
DownArrow<br/><br/></td><td>
MoveDown<br/><br/></td><td>
MoveDown (move the selected elements towards up by one pixel)<br/><br/></td></tr>
<tr>
<td>
Ctrl + MouseScroll<br/><br/></td><td>
Zoom<br/><br/></td><td>
Zoom(Zoom in/Zoom out the diagram)<br/><br/></td></tr>
<tr>
<td>
Ctrl + G<br/><br/></td><td>
Group<br/><br/></td><td>
Grouping the element in the diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + G<br/><br/></td><td>
UnGroup<br/><br/></td><td>
UnGrouping the element in the diagram<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + [<br/><br/></td><td>
SendToBack<br/><br/></td><td>
Moves the selected element behind all the other overlapped elements.<br/><br/></td></tr>
<tr>
<td>
Ctrl + [<br/><br/></td><td>
SendBackward<br/><br/></td><td>
Moves the selected element behind the underlying element.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + ]<br/><br/></td><td>
BringFront<br/><br/></td><td>
Brings the selected element to front over all the other overlapped elements.<br/><br/></td></tr>
<tr>
<td>
Ctrl + ]<br/><br/></td><td>
BringForward****<br/><br/></td><td>
Moves the selected element over the nearest overlapping element****<br/><br/></td></tr>
</table>
