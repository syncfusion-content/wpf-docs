---
layout: post
title: Syncfusion diagram supports to connect two points, nodes or ports.
description: How to draw a line to connect points, nodes, or ports?
platform: wpf
control: SfDiagram
documentation: ug
---

# Connector

Connectors are objects used to create link between two points or nodes to indicate the flow of operation or relationships between them.

![point to point connection](Connector_images/Connector_img1.PNG)

## Connector types

Diagram supports to create five types of connectors. They are,

*   `Line`
*   `Orthogonal`
*   `CubicBezier`
*   `QuadraticBezier`
*   `PolyLine`

`DefaultConnectorType` property allows to change the connector type. By default, diagram connector type is `Orthogonal`.

{% tabs %}
{% highlight xaml %}
<!--Style for the Connector-->
<Style TargetType="syncfusion:Connector">
    <Setter Property="ConnectorGeometryStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="#6BA5D7"/>
                <Setter Property="StrokeThickness" Value="1"/>
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="TargetDecoratorStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Fill" Value="#6BA5D7"/>
                <Setter Property="StrokeThickness" Value="1"/>
            </Style>
        </Setter.Value>
    </Setter>
</Style>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--create the simple connector with source point and target point values-->
            <syncfusion:ConnectorViewModel x:Name="simpleConnector" SourcePoint="100,100" TargetPoint="200,200" />
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

//Define the Connector Type as line
diagram.DefaultConnectorType = ConnectorType.Line;

//creating simple connector through collction using source and target points.
ConnectorViewModel simpleConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(100,100),
    TargetPoint = new Point(200,200),
};

//Adding the connector into Collection
(diagram.Connectors as ConnectorCollection).Add(simpleConnector);

{% endhighlight %}
{% endtabs %}

![Line connector](Connector_images/ConnectorTypes.PNg)

### How to draw poly line

Poly Line is a continuous line composed of one or more line segments. When you click on the diagram page a line will be started drawing, then new segments will be keep on added for every click on page. Line drawing will be stopped when double click on the page. This poly line will be drawing using `Tool` , `DrawingTool` and `DefaultConnectorType` properties.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line" Tool="ContinuesDraw" DrawingTool="Connector" />

{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

//Define the Connector type as poly line
diagram.DefaultConnectorType = ConnectorType.PolyLine;

//Define tool as continious draw and drawing tool as connector
diagram.Tool = Tool.ContinuesDraw;
diagram.DrawingTool = DrawingTool.Connector;

{% endhighlight %}
{% endtabs %}

![Line connector](Connector_images/PloyLineDrawing.gif)

### Free-hand drawing

Diagram have support for free-hand drawing which makes you to draw any thing on tha diagram page independently. Free-hand drawing will be enabled by using `DrawingTool` property and setting its value as `FreeHand`.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" Tool="ContinuesDraw" DrawingTool="FreeHand" />

{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
diagram.Tool = Tool.ContinuesDraw;
//Define drawing tool as free hand
diagram.DrawingTool = DrawingTool.FreeHand;

{% endhighlight %}
{% endtabs %}

![Line connector](Connector_images/FreeHandDrawing.gif)

## Create Connector 

Connector can be created by defining the start and end points. The Path to be drawn can be defined with a collection of [Segments](/wpf/sfdiagram/connector#segments "Segments").

## Create connectors through connection Points

Connector can be created by defining the source and target point of the connection. The `SourcePoint` and `TargetPoint` properties which are `Point` type that allows you to set or get the start and end point of a connection.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--create the simple connector with source point and target point values-->
            <syncfusion:ConnectorViewModel x:Name="simpleConnector" SourcePoint="100,100" TargetPoint="200,200" />
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

//Define the Connector Type
diagram.DefaultConnectorType = ConnectorType.Line;

//creating simple connector through collection using source and target points.
ConnectorViewModel simpleConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(100,100),
    TargetPoint = new Point(200,200),
};

//Adding the connector into Collection
(diagram.Connectors as ConnectorCollection).Add(simpleConnector);

{% endhighlight %}
{% endtabs %}

![point to point connection](Connector_images/Connector_img6.PNG)

## Create connection between Nodes

The connector can be created between Nodes to display the relationship between them. The `SourceNode`/`SourceNodeID` and `TargetNode`/`TargetNodeID` properties allow to represent the Nodes to be connected.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Nodes Collection-->
        <syncfusion:NodeCollection>
            <!--Creating source node-->
            <syncfusion:NodeViewModel ID="sourceNode" UnitWidth="100" UnitHeight="50" OffsetX="300" OffsetY="200" Shape="{StaticResource Rectangle}"/>
            <!--Creating target node-->
            <syncfusion:NodeViewModel ID="targetNode" UnitWidth="100" UnitHeight="50" OffsetX="500" OffsetY="200" Shape="{StaticResource Rectangle}"/>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>

    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the ConnectorCollection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with source node and target node values-->
            <syncfusion:ConnectorViewModel x:Name="NodeToNodeConnection" SourceNodeID="sourceNode" TargetNodeID="targetNode"/>
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
             
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

//creating source node
NodeViewModel sourcenode = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 50,
    OffsetX = 300,
    OffsetY = 200,
    Shape = this.Resources["Rectangle"],
};

//creating target node
NodeViewModel targetenode = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 50,
    OffsetX = 500,
    OffsetY = 200,
    Shape = this.Resources["Rectangle"],
};

//Adding nodes into Collection
(diagram.Nodes as NodeCollection).Add(sourcenode);
(diagram.Nodes as NodeCollection).Add(targetenode);

//create the connector with source node and target node values
ConnectorViewModel nodeToNodeConnection = new ConnectorViewModel()
{
    SourceNode = sourcenode,
    TargetNode = targetenode,
};

//Adding connector into Collection
(diagram.Connectors as ConnectorCollection).Add(nodeToNodeConnection);

{% endhighlight %}
{% endtabs %}

![connection between nodes](Connector_images/Connector_img3.PNG)

## Connections with Ports

By default, connections are created at the intersecting point of Segments and Node bounds. The connection between any specific point of Source and Target Nodes can be achieved with Ports.

The `SourcePort`/`SourcePortID` and `TargetPort`/`TargetPortID` properties allow to create connections between some specific points of Source/Target Nodes. 

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Nodes Collection-->
        <syncfusion:NodeCollection>
            <!--Creating source node-->
            <syncfusion:NodeViewModel ID="sourceNode" UnitWidth="100" UnitHeight="50" OffsetX="300" OffsetY="200" Shape="{StaticResource Rectangle}">
                <syncfusion:NodeViewModel.Ports>
                    <!--Initialize the Ports Collection-->
                    <syncfusion:PortCollection>
                        <!--create source node port-->
                        <syncfusion:NodePortViewModel ID="SourcePort" NodeOffsetX="0" NodeOffsetY="0.5"/>
                    </syncfusion:PortCollection>
                </syncfusion:NodeViewModel.Ports>
            </syncfusion:NodeViewModel>

            <!--Creating target node-->
            <syncfusion:NodeViewModel ID="targetNode" UnitWidth="100" UnitHeight="50" OffsetX="500" OffsetY="200" Shape="{StaticResource Rectangle}">
                <syncfusion:NodeViewModel.Ports>
                    <!--Initialize the Ports Collection-->
                    <syncfusion:PortCollection>
                        <!--create source node port-->
                        <syncfusion:NodePortViewModel ID="TargetPort" NodeOffsetX="1" NodeOffsetY="0.5"/>
                    </syncfusion:PortCollection>
                </syncfusion:NodeViewModel.Ports>
            </syncfusion:NodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>

    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the ConnectorCollection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with source node and target node values-->
            <syncfusion:ConnectorViewModel x:Name="PortToPortConnection" SourcePortID="SourcePort" TargetPortID="TargetPort" SourceNodeID="sourceNode"  TargetNodeID="targetNode"/>
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

//Create source node port
NodePortViewModel sourcePort = new NodePortViewModel()
{
    NodeOffsetX = 0,
    NodeOffsetY = 0.5,
};

//Create target node port
NodePortViewModel targetPort = new NodePortViewModel()
{
    NodeOffsetX = 1,
    NodeOffsetY = 0.5,
};

//creating source node
NodeViewModel sourcenode = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 50,
    OffsetX = 300,
    OffsetY = 200,
    Shape = this.Resources["Rectangle"],
    Ports = new PortCollection()
    {
        //Add source port to source node
        sourcePort,
    }
};

//creating target node
NodeViewModel targetenode = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 50,
    OffsetX = 500,
    OffsetY = 200,
    Shape = this.Resources["Rectangle"],
    Ports = new PortCollection()
    {
        //Add target port to target node
        targetPort,
    }
};

//Adding nodes into Collection
(diagram.Nodes as NodeCollection).Add(sourcenode);
(diagram.Nodes as NodeCollection).Add(targetenode);

//create the connector from port to port
ConnectorViewModel PortToPortConnection = new ConnectorViewModel()
{
    SourceNode = sourcenode,
    //Define the source port
    SourcePort = sourcePort,
    TargetNode = targetenode,
    //Define the target port
    TargetPort = targetPort,
};

//Adding port to port connector into connector Collection
(diagram.Connectors as ConnectorCollection).Add(PortToPortConnection);

{% endhighlight %}
{% endtabs %}

![connection between ports](Connector_images/PortToPortConnection.PNG)

For more details about Ports, please refer to [Port](https://help.syncfusion.com/wpf/sfdiagram/port "Port").

## Draw Connectors

Connectors can be interactively drawn by clicking and dragging on the Diagram surface by using Drawing Tool. For more information about drawing Connectors, refer to [Drawing Tools](/wpf/sfdiagram/tools#drawing-tools:connectors "Drawing Tools").

## Connectors through data source

Connectors are automatically generated based on the relationships defined through the data source. For more information about data source, refer to [Data Source](/wpf/sfdiagram/datasource "DataSource").

## Add connectors from stencil

Connectors can be predefined and added to the stencil. You can drop those Connectors into the Diagram, when required. 

For more information about adding Connectors from stencil, refer to [Stencil](/wpf/sfdiagram/stencil "Stencil").

