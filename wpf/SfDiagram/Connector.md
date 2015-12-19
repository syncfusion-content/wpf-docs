# Connector

Connectors are objects used to create link between two Points, Nodes or ports to represent the relationships between them.

![](Connector_images/Connector_img1.jpeg)


Create Connector

Connector can be created by defining the start and end points. The Path to be drawn can be defined with a collection of segments.

Add Connectors through Connectors collection

The SourcePoint and TargetPoint properties of Connector allow you to define the end points of a Connector. The following code example illustrates how to add a Connector through Connector collection.

[XAML]

<table>
<tr>
<td>
<diagram:SfDiagram.Connectors><br/><br/><diagram:DiagramCollection><br/><br/><diagram:Connector SourcePoint="100,100" TargetPoint="200,200"><br/><br/><diagram:Connector.ConnectorGeometryStyle><br/><br/><Style TargetType="Path"><br/><br/><Setter Property="Stroke" Value="Black"></Setter><br/><br/><Setter Property="Fill" Value="Black"/><br/><br/></Style><br/><br/></diagram:Connector.ConnectorGeometryStyle><br/><br/><diagram:Connector.TargetDecoratorStyle><br/><br/><Style TargetType="Path"><br/><br/><Setter Property="Stroke" Value="Black"></Setter><br/><br/><Setter Property="Fill" Value="Black"/><br/><br/></Style><br/><br/></diagram:Connector.TargetDecoratorStyle><br/><br/></diagram:Connector><br/><br/></diagram:DiagramCollection><br/><br/></diagram:SfDiagram.Connectors><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
diagram.DefaultConnectorType = ConnectorType.Line;<br/><br/>ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img2.jpeg)


Connectors from stencil

Connectors can be predefined and added to the stencil. You can drop those Connectors into the Diagram, when required. 

For more information about adding Connectors from stencil, refer to **[Stencil](#_Stencil "")**.

Connectors through data source

Connectors are automatically generated based on the relationships defined through the data source. For more information about data source, refer to [Data Binding](#_DataSource "").

Draw Connectors

Connectors can be interactively drawn by clicking and dragging on the Diagram surface by using Drawing Tool. For more information about drawing Connectors, refer to **[Draw Connectors](#_Tools "")**.

Connect Nodes

The SourceNode and TargetNode properties allow to define the Nodes to be connected. The following code example illustrates how to connect two Nodes.

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Task 1",<br/><br/>ViewTemplate  =this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node node1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 400,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Task 2",<br/><br/>ViewTemplate = this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>nodes.Add(node1);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourceNode = node,<br/><br/>TargetNode = node1,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img3.jpeg)


Connections with Ports

The SourcePort and TargetPort properties allow to create connections between some specific points of Source/Target Nodes. The following code examples illustrates how to use NodePort and ConnectorPort.

**Using** **NodePort******

The following code example illustrates how to create ConnectorPort.

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>NodePort port1 = new NodePort()<br/><br/>{<br/><br/>Width = 10,<br/><br/>Height = 10,<br/><br/>NodeOffsetX = 1,<br/><br/>NodeOffsetY = 0.65,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Constraints = PortConstraints.Default & ~PortConstraints.InheritPortVisibility,<br/><br/>Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/>NodePort port2 = new NodePort()<br/><br/>{<br/><br/>Width = 10,<br/><br/>Height = 10,<br/><br/>NodeOffsetX = 1,<br/><br/>NodeOffsetY = 0.35,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Constraints = PortConstraints.Default & ~PortConstraints.InheritPortVisibility,<br/><br/>Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/>Node task1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 350,<br/><br/>OffsetY = 300,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node task2 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 250,<br/><br/>Ports = new ObservableCollection<INodePort>()<br/><br/>{<br/><br/>port1,<br/><br/>port2<br/><br/>},<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 2",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node task3 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 350,<br/><br/>OffsetY = 200, <br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 3",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(task1);<br/><br/>nodes.Add(task2);<br/><br/>nodes.Add(task3);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourcePort = port2,<br/><br/>SourceNode = task2,<br/><br/>TargetNode = task3,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>ConnectorViewModel connector1 = new ConnectorViewModel()<br/><br/>{<br/><br/>TargetPort = port1,<br/><br/>SourceNode = task1,<br/><br/>TargetNode = task2,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>lines.Add(connector1);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img4.jpeg)


______Using__ __NodePort______

**Using** **ConnectorPort******

The following code example illustrates how to create ConnectorPort.

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>ConnectorPort port = new ConnectorPort()<br/><br/>{<br/><br/>Height = 10,<br/><br/>Width = 10,<br/><br/>Length = 0.5,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility,<br/><br/>Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/>Node task1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node task2 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 300,<br/><br/>OffsetY = 100,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 2",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node task3 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 3",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(task1);<br/><br/>nodes.Add(task2);<br/><br/>nodes.Add(task3);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourceNode = task1,<br/><br/>TargetNode = task2,<br/><br/>Ports=new ObservableCollection<ConnectorPort>()<br/><br/>{<br/><br/>port<br/><br/>},<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>ConnectorViewModel connector1 = new ConnectorViewModel()<br/><br/>{  <br/><br/>SourceConnector=connector,<br/><br/>TargetNode = task3,<br/><br/>SourcePort = port,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/><br/><br/>lines.Add(connector);<br/><br/>lines.Add(connector1);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img5.jpeg)


__Using__ __ConnectorPort______

Segments

The path of the Connector is defined with a collection of segments.

Straight

Straight segment allows to create a straight line. To create a straight line, you should specify the segment as StraightSegment and add a straight segment to collection. The following code example illustrates how to create a default straight segment.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>{{'____'| markdownify }}{{'__//__'| markdownify }}{{'__Add__ '| markdownify }}{{'__the__ '| markdownify }}{{'__Straight__ '| markdownify }}{{'__Segment__ '| markdownify }}{{'__to__ '| markdownify }}{{'__Segments__'| markdownify }}{{'____'| markdownify }}<br/><br/>Segments = new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>new StraightSegment()<br/><br/>{<br/><br/>}<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img6.jpeg)


The Point property of straight segment allows you to define the end point of it. The following code example illustrates how to define the end point of a straight segment.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 300),<br/><br/>{{'____'| markdownify }}{{'__//__'| markdownify }}{{'__Add__ '| markdownify }}{{'__the__ '| markdownify }}{{'__Straight__ '| markdownify }}{{'__Segment__ '| markdownify }}{{'__to__ '| markdownify }}{{'__Segments__'| markdownify }}{{'____'| markdownify }}<br/><br/>Segments = new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>new StraightSegment()<br/><br/>{<br/><br/>Point=new Point(100,200)<br/><br/>}<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img7.jpeg)


Orthogonal

Orthogonal segments are used to create segments that are perpendicular to each other.

Set the segment as OrthogonalSegment to create the default orthogonal segment. The following code example illustrates how to create a default orthogonal segment.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>{{'____'| markdownify }}{{'__//__'| markdownify }}{{'__Add__ '| markdownify }}{{'__the__ '| markdownify }}{{'__Orthoganal__ '| markdownify }}{{'__Segment__ '| markdownify }}{{'__to__ '| markdownify }}{{'__Segments__'| markdownify }}{{'____'| markdownify }}<br/><br/>Segments = new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>new OrthogonalSegment()<br/><br/>{<br/><br/>}<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img8.jpeg)


<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>{{'____'| markdownify }}{{'__//__'| markdownify }}{{'__Add__ '| markdownify }}{{'__the__ '| markdownify }}{{'__Orthoganal__ '| markdownify }}{{'__Segment__ '| markdownify }}{{'__to__ '| markdownify }}{{'__Segments__'| markdownify }}{{'____'| markdownify }}<br/><br/>Segments = new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>new OrthogonalSegment()<br/><br/>{<br/><br/>Length = 50,<br/><br/>Direction = OrthogonalDirection.Bottom<br/><br/>} <br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img9.jpeg)


Avoid overlapping

Orthogonal segments are automatically re-routed, in order to avoid overlapping with the source and target Nodes. The following images illustrates how orthogonal segments are re-routed.

![](Connector_images/Connector_img10.jpeg)


![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Connector_images/Connector_img11.png](Connector_images/Connector_img11.jpeg)


CubicCurveSegment

Cubic curve segments are used to create curve segments and the curves are configurable with the control points.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>Segments = new ObservableCollection<CubicCurveSegment>()<br/><br/>{<br/><br/>new CubicCurveSegment()<br/><br/>{<br/><br/>}<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img12.jpeg)


The Point1 and Point2 of cubic curve segment enable you to set the control points. The following code example 

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 200),<br/><br/>TargetPoint = new Point(250, 200),<br/><br/>Segments = new ObservableCollection<CubicCurveSegment>()<br/><br/>{<br/><br/>new CubicCurveSegment()<br/><br/>{<br/><br/>Point1 = new Point(125,75),<br/><br/>Point2 = new Point(225,75)<br/><br/>},<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img13.jpeg)


Complex segments

Multiple segments can be defined one after another. To create a connector with multiple segments, define and add the segments to ConnectorSegments collection. The following code example illustrates how to create a connector with multiple segments.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 200),<br/><br/>TargetPoint = new Point(250, 300),<br/><br/>Segments = new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>//Segment of length 100px to the bottom<br/><br/>new OrthogonalSegment()<br/><br/>{<br/><br/>Length = 150,<br/><br/>Direction = OrthogonalDirection.Bottom<br/><br/>},<br/><br/>//Defines the segment of 150px length to the right<br/><br/>new OrthogonalSegment()<br/><br/>{<br/><br/>Length = 150,<br/><br/>Direction = OrthogonalDirection.Right<br/><br/>}<br/><br/>}<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img14.jpeg)


Decorator

Start and end points of a Connector can be decorated with some customizable shapes like arrows, circles, diamond or path. You can decorate the connection end points with the SourceDecorator and TargetDecorator properties of Connector. 

The SourceDecoratorStyle and TargetDecoratorStyle properties allows to define the shape of the decorators. The following code example illustrates how to create decorators of various shapes.

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/><br/><br/>// Ellipse shape decorator<br/><br/>SourceDecorator = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>SourceDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>// Arrow shape decorator<br/><br/>TargetDecorator = new PathGeometry()<br/><br/>{<br/><br/>Figures = new PathFigureCollection()<br/><br/>{<br/><br/>new PathFigure()<br/><br/>{<br/><br/>StartPoint = new Point(0, 0),<br/><br/>Segments = new PathSegmentCollection()<br/><br/>{<br/><br/>new PolyLineSegment()<br/><br/>{<br/><br/>Points = new PointCollection()<br/><br/>{<br/><br/>new Point(10, 5),<br/><br/>new Point(0, 10),<br/><br/>new Point(0,0)<br/><br/>}<br/><br/>}<br/><br/>}<br/><br/>}<br/><br/>}<br/><br/>},<br/><br/><br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle"] as Style<br/><br/>};<br/><br/>Connector connector1 = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(300, 100),<br/><br/>TargetPoint = new Point(400, 200),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>// Diamond shape decorator<br/><br/>SourceDecorator = "M16,0L32,15.999985 16,32.000001 0,15.999985z",<br/><br/>SourceDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>// Open arrow shape decorator<br/><br/>TargetDecorator = "M2.7330054,0L16.31903,16.055999 1.6030035,31.999999 0,30.518999  <br/><br/>13.407025,15.994999 1.0660024,1.4089985z",<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle"] as Style<br/><br/>};<br/><br/>Connector connector2 = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(500, 100),<br/><br/>TargetPoint = new Point(600, 200),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>// arrow shape decorator<br/><br/>TargetDecorator = "M 376.892,225.284L 371.279,211.95L 376.892,198.617L 350.225,211.95L <br/><br/>376.892,225.284 Z",<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle"] as Style<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>lines.Add(connector1);<br/><br/>lines.Add(connector2);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Connector_images/Connector_img16.png](Connector_images/Connector_img15.jpeg)




Padding

Padding is used to leave space between the Connector’s end point and the object to where it is connected.

The SourcePadding and TargetPadding properties of Connector define the space to be left between the connection end points and the source and target Nodes of Connector. The following code example illustrates how to leave space between the connection end points and source, target Nodes.

<table>
<tr>
<td>
ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourceNode = node,<br/><br/>TargetNode = node1,<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(250, 150),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>{{'__//__'| markdownify }}{{'__Space__ '| markdownify }}{{'__between__ '| markdownify }}{{'__source__ '| markdownify }}{{'__point__ '| markdownify }}{{'__and__ '| markdownify }}{{'__source__ '| markdownify }}{{'__object__'| markdownify }}{{'____'| markdownify }}<br/><br/>SourcePadding = 5,<br/><br/>{{'__//__'| markdownify }}{{'__Space__ '| markdownify }}{{'__between__ '| markdownify }}{{'__target__ '| markdownify }}{{'__point__ '| markdownify }}{{'__and__ '| markdownify }}{{'__target__ '| markdownify }}{{'__object__'| markdownify }}{{'____'| markdownify }}<br/><br/>TargetPadding = 10<br/><br/>};<br/><br/><br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img16.jpeg)


The ConnectorPadding property of Node defines the space to be left between the Node bounds and its edges. The following code example illustrates how to leave the space between a Node and its connections.

[XAML]

<table>
<tr>
<td>
<DataTemplate x:Key="viewtemplate"><br/><br/><TextBlock Text="{Binding Path=Content}" Foreground="White"/><br/><br/></DataTemplate><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>ConnectorPadding = 5,<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node node1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 400,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 2",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>nodes.Add(node1);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourceNode = node,<br/><br/>TargetNode = node1,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img17.jpeg)


The ConnectorPadding property of port defines the space between the ports and its in/out edges. The following code example illustrates how to leave the space between ports its connections.

<table>
<tr>
<td>
NodePort port = new NodePort()<br/><br/>{<br/><br/>ConnectorPadding = 10,<br/><br/>Width = 10,<br/><br/>Height = 10,<br/><br/>NodeOffsetX = 0,<br/><br/>NodeOffsetY = 0.5,<br/><br/>UnitMode = UnitMode.Fraction,<br/><br/>PortVisibility = PortVisibility.Visible,<br/><br/>Constraints = PortConstraints.Default & ~PortConstraints.InheritPortVisibility,<br/><br/>Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },<br/><br/>ShapeStyle = this.diagram.Resources["portshapestyle"] as Style<br/><br/>};<br/><br/>ObservableCollection<Node> nodes = new ObservableCollection<Node>();<br/><br/>Node node = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>Node node1 = new Node()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 400,<br/><br/>OffsetY = 200,<br/><br/>Ports = new ObservableCollection<INodePort>()<br/><br/>{<br/><br/>port<br/><br/>},<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 2",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>nodes.Add(node1);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>TargetPort = port,<br/><br/>SourceNode = node,<br/><br/>TargetNode = node1,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img18.jpeg)


Bridging

Line Bridging creates a bridge for lines to smartly cross over other lines, at points of interaction. When two lines Connectors meet each other, the line with higher z-order (upper one) draws an arc over the underlying Connector. Bridging can be enabled/disabled either with the constraints property of Connector or with Diagram constraints. The following code example illustrates how to enable line bridging.

<table>
<tr>
<td>
ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(250, 300),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.InheritBridging | <br/><br/>ConnectorConstraints.Bridging<br/><br/>};<br/><br/>ConnectorViewModel connector1 = new ConnectorViewModel()<br/><br/>{<br/><br/>SourcePoint = new Point(250, 50),<br/><br/>TargetPoint = new Point(150, 300),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.InheritBridging | <br/><br/>ConnectorConstraints.Bridging<br/><br/>};<br/><br/>diagram.BridgeDirection = BridgeDirection.Bottom;<br/><br/>diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;<br/><br/>lines.Add(connector);<br/><br/>lines.Add(connector1);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img19.jpeg)


![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Connector_images/Connector_img20.png](Connector_images/Connector_img20.jpeg)


The direction of the bridge can be customized with the property BridgeDirection defines the intersecting segment where the bridge has to be inserted. By default, the bridge direction points to the top.

The following code example illustrates how to draw the bridge at the bottom direction.

[XAML]

<table>
<tr>
<td>
<diagram:SfDiagram x:Name="diagram" BridgeDirection="Bottom"><br/><br/><diagram:ConnectorViewModel SourcePoint="100,100" TargetPoint="250,150" <br/><br/>Constraints="Bridging"><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
diagram.BridgeDirection = BridgeDirection.Bottom;<br/><br/>diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;<br/><br/><br/><br/></td></tr>
</table>
Corner radius

Corner radius allows to create Connectors with rounded corners. The radius of the rounded corner is set with CornerRadius property.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node1 = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>ContentTemplate = this.diagram.Resources["contenttemplate"] as DataTemplate,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>NodeViewModel node2 = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 60,<br/><br/>OffsetX = 350,<br/><br/>OffsetY = 300,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Task 1",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node1);<br/><br/>nodes.Add(node2);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourceNode = node1,<br/><br/>TargetNode = node2,<br/><br/>CornerRadius = 10,<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>connectors.Add(connector);<br/><br/>diagram.Connectors = connectors;<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img21.jpeg)


Appearance

StrokeThickness, Stroke and style of the LineConnector and Decorators can be customized with a set of defined properties.

Segment Appearance

The following code example illustrates how to customize the segment appearance.

[XAML]

<table>
<tr>
<td>
<Style TargetType="Path" x:Key="connectorstyle"><br/><br/><Setter Property="Stroke" Value="Green"></Setter><br/><br/><Setter Property="StrokeThickness" Value="2"/><br/><br/><Setter Property="StrokeDashArray" Value="2"/><br/><br/><Setter Property="Opacity" Value="0.8"/><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
ObservableCollection<Connector> lines = new ObservableCollection<Connector>();<br/><br/>Connector connector = new Connector()<br/><br/>{<br/><br/>SourcePoint = new Point(100, 100),<br/><br/>TargetPoint = new Point(200, 200),<br/><br/>ConnectorGeometryStyle = this.diagram.Resources["connectorstyle"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;<br/><br/><br/><br/></td></tr>
</table>
Decorator Appearance

The following code example illustrates how to customize the appearance of the decorator.

[XAML]

<table>
<tr>
<td>
<Style x:Key="decoratorstyle1" TargetType="Path"><br/><br/><Setter Property="Fill" Value="Red" /><br/><br/><Setter Property="Stroke" Value="Green" /><br/><br/><Setter Property="StrokeThickness" Value="2" /><br/><br/><Setter Property="Width" Value="10" /><br/><br/><Setter Property="Height" Value="10" /><br/><br/><Setter Property="Stretch" Value="Fill" /><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/><br/><br/></td></tr>
</table>
![](Connector_images/Connector_img22.jpeg)


Interaction

Diagram allows to edit the Connectors at runtime. To edit the Connector segments at runtime, refer to **[Connection Editing](#ConnectionEditing "")**.

Constraints

The Constraints property of Connector allows to enable/disable certain features of Connectors. For more information aboutconstraints, refer to **[Connector Constraints](#ConnectorConstraints "")**.

