# Group

Group is used to cluster multiple Nodes and Connectors into a single element. It acts like a container for its children (Nodes, Groups, and Gonnectors). Every change made to the Group also affects the children. Child elements can be edited individually.

Create Group

Add Group

The following code illustrates how to create a Group Node.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>NodeViewModel node1 = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>ObservableCollection<GroupViewModel> groups = new ObservableCollection<GroupViewModel>();<br/><br/>GroupViewModel group = new GroupViewModel()<br/><br/>{<br/><br/>Nodes = new ObservableCollection<NodeViewModel>()<br/><br/>{<br/><br/>node,<br/><br/>node1<br/><br/>},<br/><br/>};<br/><br/>groups.Add(group);<br/><br/>diagram.Groups = groups;<br/><br/><br/><br/></td></tr>
</table>
Group from Stencil

Group Nodes can be predefined and added to stencil. You can drop those Groups into Diagram, when required. 

To explore how to add Groups from stencil, refer to **[Stencil](#_Stencil "")**

Interaction

You can edit the Group and its children at runtime. For more information about how to interact with a Group, refer to **[Interaction](#_Interaction "")**.

