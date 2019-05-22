---
layout: post
title: Diagram supports to connect two points, nodes or ports.
description: How to draw a line to connect points, nodes, or ports?
platform: wpf
control: SfDiagram
documentation: ug
---

# Connector

Connectors are objects used to create link between two Points, Nodes or ports to represent the relationships between them.

![connection between ports](Connector_images/Connector_img1.PNG)

## Define Connector

Connector can be created by defining the start and end points. The Path to be drawn can be defined with a collection of segments. The `SourcePoint` and `TargetPoint` properties of Connector allow you to define the end points of a Connector.

{% tabs %}
{% highlight xaml %}
<!--Style for the Connector-->
<Style TargetType="syncfusion:Connector">
  <Setter Property="ConnectorGeometryStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Stroke" Value="CornflowerBlue"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
  </Setter>
  <Setter Property="TargetDecoratorStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Fill" Value="CornflowerBlue"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
  </Setter>
</Style>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
  <syncfusion:SfDiagram.Connectors>
  <!--Initialize the ConnectorCollection-->
    <syncfusion:ConnectorCollection>
    <!--Initialize the Connector-->
      <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200">
      </syncfusion:ConnectorViewModel>
    </syncfusion:ConnectorCollection>
  </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}
//Define the ConnectorType
diagram.DefaultConnectorType = ConnectorType.Line;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    //Define the Source and TargetPoint
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![point to point connection](Connector_images/Connector_img2.PNG)

### Connectors from stencil

Connectors can be predefined and added to the stencil. You can drop those Connectors into the Diagram, when required. 

For more information about adding Connectors from stencil, refer to [Stencil](/wpf/sfdiagram/stencil "Stencil").

### Connectors through data source

Connectors are automatically generated based on the relationships defined through the data source. For more information about data source, refer to [Data Source](/wpf/sfdiagram/datasource "DataSource").

### Draw Connectors

Connectors can be interactively drawn by clicking and dragging on the Diagram surface by using Drawing Tool. For more information about drawing Connectors, refer to [Draw Connectors](/wpf/sfdiagram/tools#drawing-tools:connectors "Draw Connectors").

## Connect Nodes

The `SourceNode` and `TargetNode` properties allow to define the Nodes to be connected.

{% tabs %}
{% highlight C# %}

//Define the NodeCollection
diagram.Nodes = new NodeCollection();
//Defining the Node
NodeViewModel node1 = AddNode(100,"Node1");
NodeViewModel node2 = AddNode(250,"Node2");
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node1);
(diagram.Nodes as NodeCollection).Add(node2);
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNode=node1,
    TargetNode=node2,
    ConnectorGeometryStyle = this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);


//Creating NodeViewmodel
public NodeViewModel AddNode(double offsetX, string text)
{
    NodeViewModel node = new NodeViewModel();
    node.UnitHeight = 60;
    node.UnitWidth = 100;
    node.OffsetX = offsetX;
    node.OffsetY = 100;
    node.Shape = new RectangleGeometry { Rect = new Rect(0, 0, 10, 10) };   
    return node;
}

{% endhighlight %}
{% endtabs %}

The `SourceNodeID` and `TargetNodeID` properties also allows to define the nodes to be connected, for sample please refer to [ConnectNodes](http://www.syncfusion.com/downloads/support/directtrac/205629/ze/NodeID-1392072082).

![connection between nodes](Connector_images/Connector_img3.PNG)

N> By default, connections are created at the intersecting point of Segments and Node bounds. The connection between any specific point of Source and Target Nodes can be achieved with Ports.

## Connections with Ports

The `SourcePort`/`SourcePortID` and `TargetPort`/`TargetPortID` properties allow to create connections between some specific points of Source/Target Nodes. 

For Connections with Ports, please refer to [Port](https://help.syncfusion.com/wpf/sfdiagram/port "Port").

## Segments

The path of the Connector is defined with a collection of `Segments`.

![types of connector segment](Connector_images/Connector_img31.PNG)

### Straight

Straight segment allows to create a straight line. To create a straight line, you should specify the segment as `StraightSegment` and add a straight segment to collection.

{% tabs %}
{% highlight C# %}
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new StraightSegment()      
    }
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Straight segment](Connector_images/Connector_img6.PNG)

### Orthogonal

Orthogonal segments are used to create segments that are perpendicular to each other. Set the segment as `OrthogonalSegment` to create the default orthogonal segment.

{% tabs %}
{% highlight C# %}
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new OrthogonalSegment()      
    }
};
//Adding Connector to CollectionS
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Orthogonal segments](Connector_images/Connector_img8.PNG)

### CubicCurveSegment

Cubic curve segments are used to create curve segments and the curves are configurable with the control points.To create a Curve line, you should specify the segment as `CubicCurveSegment` and add a CubicCurveSegment  to collection.

{% tabs %}
{% highlight C# %}

//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new CubicCurveSegment()      
    }
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Cubic curve segments](Connector_images/Connector_img12.PNG)

#### Avoid overlapping

Orthogonal segments are automatically re-routed, in order to avoid overlapping with the source and target Nodes.

![basic routing](Connector_images/Connector_img10.PNG)

![source and target overlapping](Connector_images/Connector_img11.PNG)

N> Overlapping with Source and Target nodes are only avoided. Other nodes are not considered as obstacles.

## Decorator

Start and end points of a Connector can be decorated with some customizable shapes like arrows, circles, diamond or path. You can decorate the connection end points with the `SourceDecorator` and `TargetDecorator` properties of Connector. 

The `SourceDecoratorStyle` and `TargetDecoratorStyle` properties allows to define the shape of the decorators.

For Sample, please refer to [Decorator](http://www.syncfusion.com/downloads/support/directtrac/153031/ze/DecoratorConnector1321823789 "Decorator")

![source and target of the connector](Connector_images/Connector_img15.PNG)

The `SourceDecoratorPivot` and `TargetDecoratorPivot` properties allows to Customize the position of the decorators in the connector.

## SegmentDecorators
 
 `SegmentDecorator` property allows to customize the shape within the Connector. `SegmentDecoratorStyle` property allows to customize the Style of SegmentDecorator.
 
 {% tabs %}
 {% highlight c# %}
 
 //Define the collection of SegmentDecorator
SegmentDecorators = new ObservableCollection<ISegmentDecorator>()
{
    //Define the SegmentDecorator
    new SegmentDecorator()
    {
        //Define the Shape of SegmentDecorator
        Shape = "M0,0 L10,5 L0,10",
        Length =0.4
    }
}

 {% endhighlight %}
 {% endtabs %}
 
 For Sample, please refer to [SegmentDecorator](http://www.syncfusion.com/downloads/support/directtrac/205629/ze/SegmentDecorator575139946). 
 
 ![segment decorator of the connector](Connector_images/SegmentDecorator.PNG)

## Corner radius

Corner radius allows to create Connectors with rounded corners. The radius of the rounded corner is set with `CornerRadius` property.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Connectors>
    <syncfusion:ConnectorCollection>
      <!--Initialize the Connector-->
      <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200" CornerRadius="10">
      </syncfusion:ConnectorViewModel>
    </syncfusion:ConnectorCollection>
  </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    //Define the CornerRadius
    CornerRadius = 10,
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![arc based corners of the connector](Connector_images/Connector_img21.PNG)

## Padding

Padding is used to leave space between the Connector’s end point and the object to where it is connected. The `SourcePadding` and `TargetPadding` properties of Connector define the space to be left between the connection end points and the source and target Nodes of Connector.

{% tabs %}
{% highlight C# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNode=node1,
    TargetNode=node2,
    //Space between SourceNode and SourceObject
    SourcePadding=5,
    //Space between TargetNode and TargetObject
    TargetPadding = 5,
    ConnectorGeometryStyle = this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![space between the Connectors end point and the object](Connector_images/Connector_img16.PNG)

## Bridging

Line Bridging creates a bridge for lines to smartly cross over other lines, at points of interaction. When two lines Connectors meet each other, the line with higher z-order (upper one) draws an arc over the underlying Connector. Bridging can be enabled/disabled either with the `Constraints` property of Connector or with `GraphConstraints`.

The Direction of Bridge can be customized with property `BridgeDirection`.

![bridge for lines to smartly cross over other lines at points of interaction](Connector_images/Bridging1.PNG)

{% tabs %}
{% highlight xaml %}
<Grid>
  <!--Initialize the SfDiagram with Constraints and BridgeDirection-->
  <syncfusion:SfDiagram x:Name="diagram" BridgeDirection="Bottom" Constraints="Bridging">
    <syncfusion:SfDiagram.Connectors>
      <!--Initialize the ConnectorCollection-->
      <syncfusion:ConnectorCollection>
        <!--Initialize the Connector-->
        <syncfusion:ConnectorViewModel SourcePoint="88,183" TargetPoint="250,300">
        </syncfusion:ConnectorViewModel>
        <syncfusion:ConnectorViewModel SourcePoint="150,156" TargetPoint="150,300">
        </syncfusion:ConnectorViewModel>
      </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
  </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

{% highlight C# %}

//Define the BridgeDirection
diagram.BridgeDirection = BridgeDirection.Bottom;
//Define Constraints
diagram.Constraints = diagram.Constraints | GraphConstraints.Bridging;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(88, 183),
    TargetPoint = new Point(250, 300)
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(150, 156),
    TargetPoint = new Point(150, 300),
};
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![bridge for lines to smartly cross over other lines](Connector_images/bridging.png)

N> Bezier segments do not support Bridging.

#### BridgeSpace

The `BridgeSpace` property allows to customize the size of bridge in a connector.

{% tabs %}
{% highlight c# %}

//Define the BridgeDirection
diagram.BridgeDirection = BridgeDirection.Bottom;
//Define Constraints
diagram.Constraints = diagram.Constraints | GraphConstraints.Bridging;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    //Define the Bridge space of the connector
    BridgeSpace=30,
    SourcePoint = new Point(88, 183),
    TargetPoint = new Point(250, 300),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(150, 156),
    TargetPoint = new Point(150, 300),
};
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![customize the size of bridge in a connector](Connector_images/bridgespace.png)

## Appearance

StrokeThickness, Stroke and style of the Connector and Decorators can be customized with a set of defined properties.

{% tabs %}
{% highlight xaml %}

<!--Style for ConnectorGeometryStyle-->
<Style TargetType="Path" x:Key="ConnectorStyle">
  <Setter Property="Stroke" Value="CornflowerBlue"/>
  <Setter Property="StrokeThickness" Value="2"/>
  <Setter Property="StrokeDashArray" Value="2"/>
  <Setter Property="Opacity" Value="0.8"/>
</Style>

{% endhighlight %}

{% highlight c# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    ConnectorGeometryStyle=this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![appearance customization](Connector_images/Connector_img22.PNG)

## Interaction

#### Draw Connector

* On drawing a connector, `ObjectDrawn` event will notify the DragState and Item. To explore about arguments, please refer to [ObjectDrawn](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ObjectDrawnEventArgs.html) . 

### Connection Editing

* Each segment and end points of a selected Connector is editable with some specific handles/thumbs.

### End point handles

Source and target points of the selected connectors are represented with two handles. Clicking and dragging those handles help you to adjust the source and target points.

![straight segment with end thumbs for editing](Connector_images/StraightEditing.PNG)

* If any changes made in the source thumb of the connector ,`ConnectorSourceChangedEvent` will notify the DragState, Connector Item with its old and new values.To explore about arguments ,please refer to [ChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ConnectorChangedEventArgs.html) .

* If any changes made in the target thumb of the connector ,`ConnectorTargetChangedEvent` will notify the DragState and CauseValue Connector Item with its old and new values.
* Unknown- On dragging the target thumb of available connector, will notify the Cause as `UnKnown`.
* Drawing- On drawing a connector in an Element will notify the Cause as `Drawing`.

To explore about arguments, please refer to [ChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ConnectorChangedEventArgs.html) . 

* If any changes made in the segment of the connector,`ConnectorEditingEvent` will notify the DragState, Item and ThumbType.To explore about arguments, please refer to [ConnectorEditingEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ConnectorEditingEventArgs.html) .

### Straight segment editing

* End point of each straight segment is represented by a thumb that enables to edit the segment.
* Any number of new segments can be inserted into a straight line by clicking that when shift and ctrl keys are pressed. (Ctrl+Shift+Click).
* Straight segments can be removed by clicking the segment end point, when ctrl and shift keys are pressed. (Ctrl+Shift+Click).

### Orthogonal thumbs

* Orthogonal thumbs allow to adjust the length of adjacent segments by clicking and dragging it.
* When necessary, some segments are added or removed automatically, when dragging the segment. This is to maintain proper routing of orthogonality between segments.

![segment editing at runtime using segment thumbs](Connector_images//SegmentEditing.png)

### Bezier thumbs

* Bezier segments are annotated with two thumbs to represent the control points. Control points of the curve can be configured by clicking and dragging the control thumbs.

![control points editing at runtime using segment thumbs](Connector_images/Bezier3.gif)


## Customization and Validation on Connector Ends

This support used to decide on which element Connector is going dock with diagramming object at runtime.

### ConnectionParameter
This is used to Gets or sets the arguments to the ConnectionParameter. Here we are listed the arguments as below:


| Type | Name | Type | Description |
|---|---|---|---|
| Property | Connector | object | Returns the Connector which is edited at runtime. |
| Property | SourceNode | object | Defines the specific Node as Source of Connector. |
| Property | TargetNode | object | Defines the specific Node as Target of Connector. |
| Property | SourcePort | IPort | Defines the specific Port as Source of Connector. |
| Property | TargetPort | IPort | Defines the specific Port as Target of Connector. |
| Property | SourcePoint | Point | Defines the specific Point as Source of Connector. |
| Property | TargetPoint | Point | Defines the specific Point as Source of Connector. |
| Property | ConnectorEnd | ConnectorEnd | Returns the Connector end which is edited at runtime.

public enum ConnectorEnd
    {
        Source,
        Target,
    } |
| Property | SourceConnector | object | Defines the specific Connector as Source of Connector. |
| Property | TargetConnector | object | Defines the specific Connector as Target of Connector. |


The following code illustrates how to override ValidateConnection

{% tabs %}
{% highlight C# %}

/// <summary>
/// Create custom class for diagram
/// </summary>
public class CustomDiagram : SfDiagram
{
     /// <summary>
    /// Override the validate connection
    /// </summary>
    /// <param name="args">Gets args value</param>
    protected override void ValidateConnection(ConnectionParameter args)
    {
        // set the target node and target port
        if (args.TargetPort == null && args.TargetNode != null)
        {
            if (args.TargetNode is NodeViewModel)
            {
                NodeViewModel node = args.TargetNode as NodeViewModel;
                if (node.Ports != null && (node.Ports as ObservableCollection<IPort>).Count() > 0)
                {
                    args.TargetPort = (node.Ports as ObservableCollection<IPort>)[0];
                }
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Validate whether port already have connection and count of connection](Interaction_images/Interaction_img16.jpg)

## Hit Padding

Connection can be made from/to Nodes, Connectors, Port or on empty area in a diagram. Making connection with Connector and Ports are usually difficult as thickness are usually small. To make it easy to connect, it should be possible to connect when mouse comes near its vicinity area. `HitPadding` property allow to customize the vicinity area while connecting.

{% tabs %}
{% highlight xaml %}

<diagram:SfDiagram.Connectors>
  <diagram:DiagramCollection>
    <diagram:Connector SourcePoint="100,100" TargetPoint="200,200" HitPadding="25">
      <diagram:Connector.ConnectorGeometryStyle>
        <Style TargetType="Path">
          <Setter Property="Stroke" Value="Black"></Setter>
          <Setter Property="Fill" Value="Black"/>
        </Style>
      </diagram:Connector.ConnectorGeometryStyle>
      <diagram:Connector.TargetDecoratorStyle>
        <Style TargetType="Path">
          <Setter Property="Stroke" Value="Black"></Setter>
          <Setter Property="Fill" Value="Black"/>
        </Style>
      </diagram:Connector.TargetDecoratorStyle>
    </diagram:Connector>
  </diagram:DiagramCollection>
</diagram:SfDiagram.Connectors>

{% endhighlight %}

{% highlight C# %}

diagram.DefaultConnectorType = ConnectorType.Line;

ObservableCollection<Connector> lines = new ObservableCollection<Connector>();
Connector connector = new Connector()
{
	SourcePoint = new Point(100, 100),
	TargetPoint = new Point(200, 200),
	HitPadding = 25,
};

lines.Add(connector);
diagram.Connectors = lines;

{% endhighlight %}
{% endtabs %}

![vicinity area to make connection](Connector_images/Connector_img23.jpg)

## Automatic Port creation

We have provided support to create a Port at the intersection point on Node or Connector at runtime. This can be achieved by using the combination of `SetTool` and `ObjectDrawn`Event.

### Enable Drawing in SetTool

This SetTool method will be invoked when Mouse/Pointer is over on Diagramming Element. In this method, We can make decision to start drawing of the Connector.

Please refer to the code example as below

{% tabs %}
{% highlight C# %}

//Override the SetTool method
protected override void SetTool(SetToolArgs args)
{
    if (args.Source is INode || args.Source is IConnector)
    {
    	args.Action = ActiveTool.Draw;
    }
    else
    {
    	base.SetTool(args);
    }
}

{% endhighlight %}
{% endtabs %}

### Set Port for intersection

The `ObjectDrawn` event will be invoked while drawing the objects. We have provided two properties in the argument of this event to set Source and Target Port of the Connector.

Please refer to the code example as below

{% tabs %}
{% highlight C# %}

//Hook the ObjectDrawn Event
(diagram.Info as IGraphInfo).ObjectDrawn += MainWindow_ObjectDrawn;

+private void MainWindow_ObjectDrawn(object sender, ObjectDrawnEventArgs args)
{
    //SourcePort should be set on Started state
    if (args.State == DragState.Started)
    {
    	if (args.Item is IConnector)
        {
        	IConnector connector = args.Item as IConnector;
        	if (connector.SourceNode != null)
        	{
            	if ((connector.SourceNode as NodeViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.SourceNode as NodeViewModel).Ports = new ObservableCollection<IPort>();

				//Set the TargetPort as NodePort to the Node
                args.SourcePort = new NodePortViewModel();
			}
            if (connector.SourceConnector != null)
            {
            	if ((connector.SourceConnector as ConnectorViewModel).Ports == null)
            		//Initialize the Port collection
                	(connector.SourceConnector as ConnectorViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as ConnectorPort to the Connector
                args.SourcePort = new ConnectorPortViewModel();
         	}
		}
	}

	//TargetPort should be set on Started state
    if (args.State == DragState.Completed)
    {
    	if (args.Item is IConnector)
        {
        	IConnector connector = args.Item as IConnector;
            if (connector.TargetNode != null)
            {
            	if ((connector.TargetNode as NodeViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.TargetNode as NodeViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as NodePort to the Node
                args.TargetPort = new NodePortViewModel();
			}
            if (connector.TargetConnector != null)
            {
          		if ((connector.TargetConnector as ConnectorViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.TargetConnector as ConnectorViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as ConnectorPort to the Connector
                args.TargetPort = new ConnectorPortViewModel();
        	}
		}
	}
}

{% endhighlight %}
{% endtabs %}

 ConnectionIndicator animation for Node:

![ConnectionIndicator animation for Node](Interaction_images/Interaction_img13.jpeg)

 ConnectionIndicator animation for Connector:

![ConnectionIndicator animation for Connector](Interaction_images/Interaction_img14.jpeg)

ConnectorPort to NodePort Connection:

![ConnectorPort to NodePort Connection](Interaction_images/Interaction_img15.jpeg)


## Constraints

The `Constraints` property of Connector allows to enable/disable certain features of Connectors. For more information about	constraints, refer to [Connector Constraints](/wpf/sfdiagram/constraints#connector-constraints "Connector Constraints").

