---
layout: post
title: Create custom connection points to draw connections with any specific point of Node.
description: How to draw connections with specific points of Node?
platform: wpf
control: SfDiagram
documentation: ug
---

#Port

Essential Diagram for WPF provides support to define custom ports for making connections.

![](Port_images/Port_img1.jpeg)![](Port_images/Port_img2.jpeg)

When a Connector is connected between two Nodes, its end points are automatically docked to Node’s nearest boundary as shown in the following image.

![](Port_images/Port_img3.jpeg)

Port act as the connection points of node and allows to create connections with only specific points as shown in the following image.

![](Port_images/Port_img4.jpeg)![](Port_images/Port_img5.jpeg)

##Create Port

###Add ports to Nodes

To add a collection port, you need to define the port object and add it to Node’s ports collection. The `Offset` property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports when initializing the Node.

{% highlight C# %}

ObservableCollection<Node> nodes = new ObservableCollection<Node>();
Node node = new Node()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 400,
	OffsetY = 100,
	Ports = new ObservableCollection<INodePort>()
	{
		new NodePort()
		{
			Width = 10,
			Height = 10,
			NodeOffsetX = 0,
			NodeOffsetY = 0.5,
			UnitMode = UnitMode.Fraction,
			PortVisibility = PortVisibility.Visible,
			Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility
		}
	},
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

The following code illustrates how to add ports to Node.

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
NodePort port = AddPort(0, 0.5);
NodePort port1 = AddPort(1, 0.5);
NodePort port2 = AddPort(0.5, 0);
NodePort port3 = AddPort(0.5, 1);
NodeViewModel node = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100, 
	OffsetX = 400,
	OffsetY = 100,
	Ports = new ObservableCollection<NodePort>()
	{
		port,
		port1,
		port2,
		port3
	},
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};

nodes.Add(node);
diagram.Nodes = nodes;

private NodePort AddPort(double p1, double p2)
{
	NodePort port = new NodePort()
	{
		Width = 10,
		Height = 10,
		NodeOffsetX = p1,
		NodeOffsetY = p2,
		UnitMode = UnitMode.Fraction,
		PortVisibility = PortVisibility.Visible,
		Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
		ShapeStyle = this.diagram.Resources["portshapestyle"] as Style
	};
	port.Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility;
	return port;
}

{% endhighlight %}

![](Port_images/Port_img6.jpeg)

The following code illustrates how to add ports to Connector.

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
ConnectorPort port = AddConnectorPort(0);
ConnectorPort port1 = AddConnectorPort(0.5);
ConnectorPort port2 = AddConnectorPort(1);
        
ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();
ConnectorViewModel connector = new ConnectorViewModel()
{
	Ports = new ObservableCollection<ConnectorPort>()
	{
       	port,
              port1,
              port2
       },
       SourcePoint = new Point(100, 100),
       TargetPoint = new Point(300, 300),               
};

lines.Add(connector);
diagram.Connectors = lines;

private ConnectorPort AddConnectorPort(double p)
{
	ConnectorPort connectorport = new ConnectorPort()
       {
       	Length = p,
              UnitMode = UnitMode.Fraction,
              PortVisibility = PortVisibility.Visible,
              Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
              ShapeStyle = this.diagram.Resources["portshapestyle"] as Style,
              Constraints = PortConstraints.Inherit & ~PortConstraints.InheritPortVisibility
       };
       return connectorport;
}

{% endhighlight %}

![](Port_images/Port_img7.jpeg)

##Connect with ports

Connector’s SourcePort and TargetPort properties allow to create connections between some specific points of source/target Nodes. For More information about creating connections with port, refer to [Connections with Ports](/wpf/sfdiagram/Connector#Connections-with-Ports "Connections with Ports").

##Appearance

You can change the shape of port by using its shape property. The appearance of ports can be customized with a set of style specific properties.

The following code illustrates how to change the appearance of port.

[XAML]

{% highlight xml %}

<Style TargetType="Path" x:Key="shapestyle">
  <Setter Property="Fill" Value="DarkCyan"></Setter>
  <Setter Property="Stroke" Value="Black"></Setter>
  <Setter Property="StrokeThickness" Value="2"></Setter>
  <Setter Property="Stretch" Value="Fill"></Setter>
</Style>

{% endhighlight %}

[C#]

{% highlight C# %}

NodePort port = new NodePort()
{
	Width = 15,
	Height = 15,
	NodeOffsetX = p1,
	NodeOffsetY = p2,
	UnitMode = UnitMode.Fraction,
	PortVisibility = PortVisibility.Visible,
	Shape = new EllipseGeometry() { RadiusX = 10, RadiusY = 10 },
	ShapeStyle = this.diagram.Resources["portshapestyle"] as Style
};

{% endhighlight %}

![](Port_images/Port_img8.jpeg)

##Constraints

The `Constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/wpf/sfdiagram/Constraints#PortConstraints "Port Constraints").