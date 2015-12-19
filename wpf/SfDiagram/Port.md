# Port

Essential Diagram for WPF provides support to define custom ports for making connections.

![](Port_images/Port_img1.jpeg)
![](Port_images/Port_img2.jpeg)


When a Connector is connected between two Nodes, its end points are automatically docked to Node’s nearest boundary as shown in the following image.

![](Port_images/Port_img3.jpeg)


Port act as the connection points of node and allows to create connections with only specific points as shown in the following image.

![](Port_images/Port_img4.jpeg)
![](Port_images/Port_img5.jpeg)


Create Port

Add ports when initializing Nodes

To add a collection port, you need to define the port object and add it to Node’s ports collection. The offset property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports when initializing the Node.

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 400,<br/><br/>OffsetY = 100,<br/><br/>Ports = new ObservableCollection<INodePort>()<br/><br/>{<br/><br/>new NodePort()<br/><br/>{<br/><br/>Width = 10,<br/><br/>Height = 10,<br/><br/>NodeOffsetX = 0,<br/><br/>NodeOffsetY = 0.5,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
The following code illustrates how to add ports to Node.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodePort port = AddPort(0, 0.5);<br/><br/>NodePort port1 = AddPort(1, 0.5);<br/><br/>NodePort port2 = AddPort(0.5, 0);<br/><br/>NodePort port3 = AddPort(0.5, 1);<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100, <br/><br/>OffsetX = 400,<br/><br/>OffsetY = 100,<br/><br/>Ports = new ObservableCollection<NodePort>()<br/><br/>{<br/><br/>port,<br/><br/>port1,<br/><br/>port2,<br/><br/>port3<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/>private NodePort AddPort(double p1, double p2)<br/><br/>{<br/><br/>NodePort port = new NodePort()<br/><br/>{<br/><br/>Width = 10,<br/><br/>Height = 10,<br/><br/>NodeOffsetX = p1,<br/><br/>NodeOffsetY = p2,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/>port.Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility;<br/><br/>return port;<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![](Port_images/Port_img6.jpeg)


The following code illustrates how to add ports to Connector.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>ConnectorPort port = AddConnectorPort(0);<br/><br/>ConnectorPort port1 = AddConnectorPort(0.5);<br/><br/>ConnectorPort port2 = AddConnectorPort(1);<br/><br/><br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>Ports = new ObservableCollection<ConnectorPort>()<br/><br/>{<br/><br/>port,<br/><br/>port1,<br/><br/>port2<br/><br/>},<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(300, 300),               <br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/>private ConnectorPort AddConnectorPort(double p)<br/><br/>{<br/><br/>ConnectorPort connectorport = new ConnectorPort()<br/><br/>{<br/><br/>Length = p,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style,<br/><br/>Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility<br/><br/>};<br/><br/>return connectorport;<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![](Port_images/Port_img7.jpeg)


Connect with ports

Connector’s SourcePort and TargetPort properties allow to create connections between some specific points of source/target Nodes. For More information about creating connections with port, refer to **[Connections with Ports](#ConnectionswithPorts "")**. 

Appearance

You can change the shape of port by using its shape property. The appearance of ports can be customized with a set of style specific properties.

The following code illustrates how to change the appearance of port.

[XAML]

<table>
<tr>
<td>
<Style TargetType="Path" x:Key="shapestyle"><br/><br/><Setter Property="Fill" Value="DarkCyan"></Setter><br/><br/><Setter Property="Stroke" Value="Black"></Setter><br/><br/><Setter Property="StrokeThickness" Value="2"></Setter><br/><br/><Setter Property="Stretch" Value="Fill"></Setter><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
NodePort port = new NodePort()<br/><br/>{<br/><br/>Width = 15,<br/><br/>Height = 15,<br/><br/>NodeOffsetX = p1,<br/><br/>NodeOffsetY = p2,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/><br/><br/></td></tr>
</table>
![](Port_images/Port_img8.jpeg)


Constraints

The Constraints property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to **[PortConstraints](#PortConstraints "")**

