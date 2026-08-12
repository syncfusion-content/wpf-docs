---
layout: post
title: SelectTool Command in WPF SfDiagram | Syncfusion®
description: Switch tools and drawing modes in Syncfusion® WPF SfDiagram using the SelectTool command to create nodes, connectors, and text elements.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectTool Command in WPF SfDiagram

The [SelectTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectTool) command of the diagram helps to change the [DrawingTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool) and [Tool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool) properties to a specified value. The [SelectToolCommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SelectToolCommandParameter.html) of `SelectTool` command is used to represent a specific tool.

| Property | Description |
|---|---|
| Tool | It is used to specify the active tool for the diagram.|
| DrawingTool | It is used to specify the drawing tool, which is valid only if the `Tool` is set as either `ContinuesDraw` or `DrawOnce`. |
| ConnectorType | It is used to specify the type (such as Orthogonal, Straight and Cubic-Curve etc.) of the connector to be drawn. |

### Tool

The `Tool` property is used to specify the active tool behavior of the diagram. The supported values are:

- `None` - Disables all tool behaviors.
- `SingleSelect` - Enables single-object selection.
- `MultipleSelect` - Enables multiple selection.
- `ZoomPan` - Enables zooming and panning.
- `DrawOnce` - Enables drawing a node or connector only once.
- `ContinuesDraw` - Enables drawing nodes or connectors continuously.

The default value of the `Tool` property is `MultipleSelect`.

### DrawingTool

The `DrawingTool` property is used to specify the type of object to be drawn. The supported values are:

- `None`
- `Connector`
- `Node`
- `FreeHand`
- `Rectangle`
- `Ellipse`
- `TextNode`

The default value of the `DrawingTool` property is `None`.

### ConnectorType

The `ConnectorType` property is used to specify the type of connector to be drawn. The supported values are:

- `Line`
- `Orthogonal`
- `QuadraticBezier`
- `CubicBezier`
- `PolyLine`

The default value of the `ConnectorType` property is `Orthogonal`.

N> To use the `DrawingTool` property, set the `Tool` property to either `ContinuesDraw` or `DrawOnce` in the `SelectToolCommandParameter`. After the tool mode is configured, specify the required drawing tool, such as `Ellipse`, `Connector`, or `TextNode`, through the `DrawingTool` property.

N> The `ConnectorType` property is applicable only when the `DrawingTool` property is set to `Connector`. If `DrawingTool` is set to any other value, the `ConnectorType` property has no effect.

For details , refer [Tools and DrawingTools](https://help.syncfusion.com/wpf/diagram/tools) 

{% tabs %}

{% highlight Xaml%}

 <!-- To draw an ellipse node-->
 <Syncfusion:SelectToolCommandParameter DrawingTool="Ellipse" Tool="ContinuesDraw"  x:Key="SelectToolEllipseCommandParameter"/>
 
 <!-- To draw a straight line connector-->
 <Syncfusion:SelectToolCommandParameter DrawingTool="Connector" ConnectorType="Line" Tool="ContinuesDraw"  x:Key="SelectToolConnectorCommandParameter"/>
 
 <!-- To draw a text node-->
 <Syncfusion:SelectToolCommandParameter DrawingTool="TextNode" Tool="ContinuesDraw"  x:Key="SelectToolTextCommandParameter"/>
 
<Button Height="50" Content="ConnectorTool" Name="Connector" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolConnectorCommandParameter}"></Button>

<Button Height="50" Content="EllipseTool" Name="Ellipse" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolEllipseCommandParameter}"></Button>

<Button Height="50" Content="TextTool" Name="TextNode" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolTextCommandParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// To draw a straight line connector            
graphinfo.Commands.SelectTool.Execute(new SelectToolCommandParameter() 
{ 
    Tool = Tool.ContinuesDraw, DrawingTool = DrawingTool.Connector, ConnectorType = ConnectorType.Line 
});

// To draw an ellipse node
graphinfo.Commands.SelectTool.Execute(new SelectToolCommandParameter() 
{ 
    Tool = Tool.ContinuesDraw, DrawingTool = DrawingTool.Ellipse
});

// To draw a text node
graphinfo.Commands.SelectTool.Execute(new SelectToolCommandParameter() 
{ 
    Tool = Tool.ContinuesDraw, DrawingTool = DrawingTool.TextNode 
});

{% endhighlight %}
{% endtabs %}

![Gif for SelectTool command](Commands_Images/Commands_SelectTool.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Commands%20Sample)