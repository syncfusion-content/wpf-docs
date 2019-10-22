---
layout: post
title: Connector Selection, Dragging and Routing | Syncfusion
description: How to select and drag the connector and How routing is happened when connector is intersecting with Node?
platform: wpf
control: SfDiagram
documentation: ug
---

# Connector Selection, Dragging and Routing

Connectors can be selected and dragged over the diagram page. 

## How to select and edit the connector

The connector can be selected by tapping it. When connector is selected, circles will be added on the starting and ending of the connector, which is represented by `Thumbs`. Clicking and dragging those handles helps you to adjust the source and target points.

![Straight segment](Connector_images/Thumb.gif)

## How to drag the connector

Also, the entire connector can be dragged over the page by using the `Constraints` property and setting its value as Draggable.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with draggable constraint-->
            <syncfusion:ConnectorViewModel x:Name="simpleConnector" SourcePoint="100,100" TargetPoint="200,200" Constraints="Default,Draggable" />
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
    //Define the constraint as draggable
    Constraints = ConnectorConstraints.Default | ConnectorConstraints.Draggable,
};

//Adding the connector into Collection
(diagram.Connectors as ConnectorCollection).Add(simpleConnector);

{% endhighlight %}
{% endtabs %}

![Straight segment](Connector_images/Draggable.gif)

## How to route the connectors

Connector's geometry might be hidden or pass over the diagram element, if the element is placed in contact with the connector. This will makes less clarity about connector path flow. This can be avoided using Routing process.

Routing is the process of updating connector's geometry to avoid obstacles in their path. This behaviour can be enabled in diagram by using `GraphConstraints.Routing`.

{% tabs %}
{% highlight xaml %}

<!--Initialize the SfDiagram with routig constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Routing"/>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the routing constraint
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Routing;

{% endhighlight %}
{% endtabs %}

![Routing](Connector_images/Routing.gif)

N> Routing is applicable only for orthogonal connectors.

Diagram supports two types of routing algorithm.. They are

* Classic : Additional segments will be added based on the position and dimension of the obstacles in their path. This type of routing gives less priority to geometry length and number of bends.

* Advanced : This routing type evaluates all possible geometrical paths for a connector aiming to find one that has a minimal bends and length.

Routing algorithm can be specified by using `RoutingType` property of `LineRoutingSettings`class.

{% tabs %}
{% highlight xaml %}

<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Routing">
  <!--Initialize the routing type-->
  <syncfusion:SfDiagram.LineRoutingSettings>
    <syncfusion:LineRoutingSettings RoutingType="Classic"/>
  </syncfusion:SfDiagram.LineRoutingSettings>
</syncfusion:SfDiagram>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the routing type
diagram.LineRoutingSettings.RoutingType = RoutingTypes.Classic;

{% endhighlight %}
{% endtabs %}

By default, all nodes are treated as an obstacle for a connector i.e. connections will go around the node boundary. And using `NodeConstraints.RoutingObstacle` individual node's can be controlled whether to act as an obstacle or not.

{% tabs %}
{% highlight C# %}

NodeViewModel node = new NodeViewModel()
  {
    UnitHeight = 50,
    UnitWidth = 50, 
    OffsetX = 200,
    OffsetY = 300,
    Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
    //Disable the routing obstacle property
    Constraints = NodeConstraints.Default & ~(NodeConstraints.RoutingObstacle),
  };

{% endhighlight %}
{% endtabs %}

![Routing](Connector_images/RoutingObstacle.png)

Also, routing option can be disabled for each connector using `ConnectorConstraints.Routing` and `ConnectorConstraints.InheritRouting` properties of connector. 

{% tabs %}
{% highlight C# %}

ConnectorViewModel connector = new ConnectorViewModel()
  {
    SourcePoint = new Point(200, 200),
    TargetPoint = new Point(400, 400),
    //Disable the routing
    Constraints = ConnectorConstraints.Default & ~(ConnectorConstraints.Routing | ConnectorConstraints.InheritRouting),
  };

{% endhighlight %}
{% endtabs %}
