---
layout: post
title: SelectTool Command in WPF Diagram control | Syncfusion
description: Learn here all about SelectTool Command support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectTool Command in WPF Diagram (SfDiagram)

The [SelectTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectTool) command of the diagram helps to change the [DrawingTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool) and [Tool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool) properties to a specified value. The [SelectToolCommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SelectToolCommandParameter.html) of `SelectTool` command is used to represent a specific tool.

| Property | Description |
|---|---|
| Tool | It is used to customize the tools of the diagram.|
| DrawingTool | It is used to specify the drawing tool, which is valid only if the `Tool` is set as either `ContinuesDraw` or `DrawOnce`. |
| ConnectorType | It is used to specify the type (such as Orthogonal, Straight and Cubic-Curve etc.) of the connector to be drawn. |

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
