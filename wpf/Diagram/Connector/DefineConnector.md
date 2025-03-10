---
layout: post
title: Connector in WPF Diagram control | Syncfusion®
description: Learn here all about Connector support in Syncfusion® WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Connector in WPF Diagram (SfDiagram)

Connectors are objects used to create link between two points or nodes to indicate the flow of operation or relationships between them.

![WPF Diagram Point to Point Connection](Connector_images/wpf-diagram-point-to-point-connection.PNG)

## Connector types

Diagram supports to create five types of connectors. They are:

*   `Line`
*   `Orthogonal`
*   `CubicBezier`
*   `QuadraticBezier`
*   `PolyLine`

The [DefaultConnectorType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DefaultConnectorType) property allows you to change the connector type. By default, the diagram connector type is `Orthogonal`.

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
            <syncfusion:ConnectorViewModel x:Name="simpleConnector" 
                                           SourcePoint="100,100" 
                                           TargetPoint="200,200" />
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

![WPF Diagram Connector Types](Connector_images/wpf-diagram-connector-types.PNg)

### How to draw polyline

Polyline is a continuous line of a segment or a continuous line composed of more line segments. When you click the diagram page, a line will be drawn, and then new segments will be kept on added for every click on page. Line drawing will be stopped when double-click the page. This polyline will be drawn using the [`Tool`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool), [`DrawingTool`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool), and `DefaultConnectorType` properties.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="PolyLine" 
                      Tool="ContinuesDraw" DrawingTool="Connector" />

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

![WPF Diagram PloyLine Drawing](Connector_images/wpf-diagram-ployline-drawing.gif)

### Free-hand drawing

Diagram has support for free-hand drawing to draw anything on the diagram page independently. Free-hand drawing will be enabled by using the `DrawingTool` property and setting its value to `FreeHand`.

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

![WPF Diagram FreeHand Drawing](Connector_images/wpf-diagram-freehand-drawing.gif)

For more information about changing drawing tool of diagram, refer to [Tools](/wpf/diagram/tools "Tools").

Find the [Drawing tools sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/DrawingTools) to depict the Tools.

## Create connector 

Connector can be created by defining the start and end points. The path to be drawn can be defined with a collection of [Segments](https://help.syncfusion.com/wpf/diagram/connector/segments/straight "Segments").

## Create connectors through connection points

The connector can be created by defining the source and target point of the connection. The [`SourcePoint`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_SourcePoint) and [`TargetPoint`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_TargetPoint) properties, which are `Point` type allows you to set or get the start and end points of a connection.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--create the simple connector with source point and target point values-->
            <syncfusion:ConnectorViewModel x:Name="simpleConnector" 
                                           SourcePoint="100,100" TargetPoint="200,200" />
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

![WPF Diagram Connectors through Connection Points](Connector_images/wpf-diagram-connectors-through-connection-points.png)

## Create connection between nodes

The connector can be created between nodes to display the relationship between them. The [`SourceNode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_SourceNode)/[`SourceNodeID`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_SourceNodeID) and [`TargetNode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_TargetNode)/[`TargetNodeID`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_TargetNodeID) properties allows you to represent the nodes to be connected.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Nodes Collection-->
        <syncfusion:NodeCollection>
            <!--Creating source node-->
            <syncfusion:NodeViewModel ID="sourceNode" 
                                      UnitWidth="100" UnitHeight="50" 
                                      OffsetX="300" OffsetY="200" 
                                      Shape="{StaticResource Rectangle}"/>
            <!--Creating target node-->
            <syncfusion:NodeViewModel ID="targetNode" 
                                      UnitWidth="100" UnitHeight="50" 
                                      OffsetX="500" OffsetY="200" 
                                      Shape="{StaticResource Rectangle}"/>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>

    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the ConnectorCollection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with source node and target node values-->
            <syncfusion:ConnectorViewModel x:Name="NodeToNodeConnection" 
                                           SourceNodeID="sourceNode" 
                                           TargetNodeID="targetNode"/>
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

![WPF Diagram Connection Between Nodes](Connector_images/wpf-diagram-connection-between-nodes.PNG)

## Connections with ports

By default, connections are created at the intersecting point of segments and node bounds. The connection between any specific point of source and target nodes can be achieved with ports.

The [`SourcePort`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_SourcePort)/[`SourcePortID`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_SourcePortID) and [`TargetPort`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_TargetPort)/[`TargetPortID`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html#Syncfusion_UI_Xaml_Diagram_ConnectorViewModel_TargetPortID) properties allows you to create connections between some specific points of Source/Target nodes. 

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Nodes Collection-->
        <syncfusion:NodeCollection>
            <!--Creating source node-->
            <syncfusion:NodeViewModel ID="sourceNode" 
                                      UnitWidth="100" UnitHeight="50" 
                                      OffsetX="300" OffsetY="200" 
                                      Shape="{StaticResource Rectangle}">
                <syncfusion:NodeViewModel.Ports>
                    <!--Initialize the Ports Collection-->
                    <syncfusion:PortCollection>
                        <!--create source node port-->
                        <syncfusion:NodePortViewModel ID="SourcePort" 
                                                      NodeOffsetX="0" 
                                                      NodeOffsetY="0.5"/>
                    </syncfusion:PortCollection>
                </syncfusion:NodeViewModel.Ports>
            </syncfusion:NodeViewModel>

            <!--Creating target node-->
            <syncfusion:NodeViewModel ID="targetNode" 
                                      UnitWidth="100" UnitHeight="50" 
                                      OffsetX="500" OffsetY="200" 
                                      Shape="{StaticResource Rectangle}">
                <syncfusion:NodeViewModel.Ports>
                    <!--Initialize the Ports Collection-->
                    <syncfusion:PortCollection>
                        <!--create source node port-->
                        <syncfusion:NodePortViewModel ID="TargetPort" 
                                                      NodeOffsetX="1"
                                                      NodeOffsetY="0.5"/>
                    </syncfusion:PortCollection>
                </syncfusion:NodeViewModel.Ports>
            </syncfusion:NodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>

    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the ConnectorCollection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with source node and target node values-->
            <syncfusion:ConnectorViewModel x:Name="PortToPortConnection" 
                                           SourcePortID="SourcePort" 
                                           TargetPortID="TargetPort" 
                                           SourceNodeID="sourceNode"  
                                           TargetNodeID="targetNode"/>
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

![WPF Diagram Connection Between Ports](Connector_images/wpf-diagram-connection-between-ports.PNG)

For more details about Ports, refer to [Port](https://help.syncfusion.com/wpf/diagram/port "Port").

Find the [Connector creation sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Connector/Create%20Connector) to depict the connector creation.

## Draw connectors

Connectors can be interactively drawn by clicking and dragging on the diagram surface by using the drawing tool. For more information about drawing connectors, refer to [Drawing Tools](/wpf/diagram/tools#drawing-tools:connectors "Drawing Tools").

## Connectors through data source

Connectors are automatically generated based on the relationships defined through the data source. For more information about data source, refer to [DataSource](/wpf/diagram/datasource "DataSource").

## Add connectors from stencil

Connectors can be predefined and added to the stencil. You can drop those connectors into the diagram, when required. 

For more information about adding connectors from stencil, refer to [Stencil](/wpf/diagram/stencil "Stencil").

## See Also

[How to apply built-in theme for node and connector?](https://support.syncfusion.com/kb/article/9995/how-to-apply-built-in-theme-for-node-and-connector-in-wpf-diagram-sfdiagram)

[How to decide whether to drag or draw a connection on port at runtime?](https://support.syncfusion.com/kb/article/8538/how-to-decide-whether-to-drag-or-draw-a-connection-on-port-at-runtime-in-the-wpf-diagram)

[How to customize the context menu?](https://support.syncfusion.com/kb/article/9270/how-to-customize-the-contextmenu-in-wpf-diagram-sfdiagram)

[How to create port at runtime though SetTool?](https://support.syncfusion.com/kb/article/9967/how-to-create-port-at-runtime-through-set-tool-in-wpf-diagram-sfdiagram)

[How to customize the connection indicator style of node and port?](https://support.syncfusion.com/kb/article/10048/how-to-customize-the-connection-indicator-style-of-node-and-port-in-wpf-diagram-sfdiagram)

[How to restrict annotation editing by double-clicking the node or connector?](https://support.syncfusion.com/kb/article/8539/how-to-restrict-annotation-editing-by-double-clicking-the-node-or-connector-in-wpf-diagram)

[How to disable the animation while creating a connection in diagram?](https://support.syncfusion.com/kb/article/8187/how-to-disable-the-animation-while-creating-a-connection-in-wpf-diagram-sfdiagram)

[How to bring the specific diagram object to the center or viewport of the Diagram?](https://support.syncfusion.com/kb/article/8390/how-to-bring-the-specific-object-to-the-center-or-viewport-of-the-diagram-in-wpf)

[How to show the copied diagram elements as preview image along with the mouse pointer?](https://support.syncfusion.com/kb/article/12037/how-to-show-the-copied-diagram-elements-as-preview-image-along-with-the-mouse-pointer-in)

[How to restrict Connector's source/target changing from native Nodes to other Nodes?](https://support.syncfusion.com/kb/article/11796/how-to-restrict-connectors-source-target-changing-from-native-nodes-to-other-nodes-in-wpf)

[How to restrict diagram objects dragging in the positive side?](https://support.syncfusion.com/kb/article/9917/how-to-restrict-diagram-objects-dragging-in-the-positive-side-in-wpf-diagram)

[How to use the property grid for diagram elements?](https://support.syncfusion.com/kb/article/9861/how-to-use-the-property-grid-in-the-wpf-diagram-sfdiagram)

[How to override the default cursors while interact on diagram objects?](https://support.syncfusion.com/kb/article/9997/how-to-override-the-default-cursors-while-interaction-in-wpf-diagram-sfdiagram)

[How to create parent and child relationship by drag and drop nodes?](https://support.syncfusion.com/kb/article/10008/how-to-create-parent-and-child-relationship-by-drag-and-drop-nodes-in-wpf-diagram-sfdiagram)

[How to get or set the positions of the segments by programmatically?](https://support.syncfusion.com/kb/article/10082/how-to-get-or-set-the-positions-of-the-segments-by-programmatically-in-wpf-diagram)

[How to toggle the visibility of connector at runtime?](https://support.syncfusion.com/kb/article/8897/how-to-toggle-the-visibility-of-connector-at-runtime-in-wpf-diagram-sfdiagram)

[How to detect or get notification when editing the thumbs of connector?](https://support.syncfusion.com/kb/article/9030/how-to-detect-or-get-notification-when-editing-the-thumbs-of-connector-in-wpf-diagram)

[How to Notify when diagramming object is duplicated with source?](https://support.syncfusion.com/kb/article/6268/how-to-notify-when-diagramming-object-is-duplicated-with-source-in-wpf-diagram-sfdiagram)

[How to programmatically Show/Hide the Annotations of node and connector?](https://support.syncfusion.com/kb/article/6281/how-to-programmatically-showhide-annotations-in-wpf-diagram-)

[How to customize the bridging style for connector?](https://support.syncfusion.com/kb/article/6120/how-to-customize-the-bridging-style-for-connector-in-wpf-diagram-sfdiagram)

[How to add port to the connector?](https://support.syncfusion.com/kb/article/5939/how-to-add-port-to-the-connector-in-wpf-diagram-sfdiagram)

[How to customize the direction of bridge?](https://support.syncfusion.com/kb/article/6010/how-to-customize-the-direction-of-bridge-in-wpf-diagram-sfdiagram)

[How to add space between connector decorator and node?](https://support.syncfusion.com/kb/article/5448/how-to-add-space-between-decorator-and-node-in-wpf-diagram-sfdiagram)

[How to disable the selection of diagram objects?](https://support.syncfusion.com/kb/article/5495/how-to-disable-the-selection-in-wpf-diagram)

[How to Obtain the Polyline Connector Completed status in WPF Diagram?](https://support.syncfusion.com/kb/article/18899/how-to-obtain-the-completed-status-of-a-polyline-connector-in-the-wpf-diagram-sfdiagram)

[How to select a connector when the mouse hovers over a node port that is connected by the connector in the WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18695/how-to-select-a-connector-when-the-mouse-hovers-over-a-node-port-that-is-connected-by-the-connector-in-the-wpf-diagram-sfdiagram)

[How to Obtain InConnectors and OutConnectors of Node in WPF Diagram?](https://support.syncfusion.com/kb/article/18250/how-to-obtain-inconnectors-and-outconnectors-of-node-in-wpf-diagram)

[How to prevent the Connector lines from overlapping the Connector's target decorator in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18404/how-to-prevent-the-connector-lines-from-overlapping-the-connectors-target-decorator-in-wpf-diagramsfdiagram)

[How to restrict the Connector's source and target decorator from being positioned in different places in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18413/how-to-restrict-the-connectors-source-and-target-decorator-from-being-positioned-in-different-places-in-wpf-diagram-sfdiagram)

[How to change the source and target ports of the connector at runtime in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18302/how-to-change-the-source-and-target-ports-of-the-connector-at-runtime-in-the-wpf-diagram-sfdiagram)

[How to Fit Selected Nodes and Connectors to the WPF Diagram Window?](https://support.syncfusion.com/kb/article/18062/how-to-fit-selected-nodes-and-connectors-to-the-wpf-diagram-window)

[How to set the rotation angle for a node based on the angle of the connector decorator's shape in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17744/how-to-set-the-rotation-angle-for-a-node-based-on-the-angle-of-the-connector-decorators-shape-in-wpf-diagram-sfdiagram)

[How to prevent the connector segment from collapsing while dragging a node in WPF Diagram (SfDiagram) ?](https://support.syncfusion.com/kb/article/17746/how-to-prevent-the-connector-segment-from-collapsing-while-dragging-a-node-in-wpf-diagram-sfdiagram-)

[How to Get the Node or Connector in the MouseMove Event in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/15646/how-to-get-the-node-or-connector-in-the-mousemove-event-in-the-wpf-diagram-sfdiagram)

[How to update the same length for connector segments in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/15538/how-to-update-the-same-length-for-connector-segments-in-the-wpf-diagram-sfdiagram)

[How to manage the visibility of node and connector objects in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/14995/how-to-manage-the-visibility-of-node-and-connector-objects-in-the-wpf-diagram-sfdiagram)

[How to change the connector style based on its SourcePort style in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18851/how-to-change-the-connector-style-based-on-its-sourceport-style-in-wpf-diagram-sfdiagram)

[How to identify the dragging state of connectors in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18846/how-to-identify-the-dragging-state-of-connectors-in-the-wpf-diagram-sfdiagram)
