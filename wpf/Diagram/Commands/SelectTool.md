---
layout: post
title: Syncfusion | Explore the SelectTool commands.
description: SelectTool Commands are used to enable drawing tool options such as ConnectorTool, Node (Rectangel, Ellipse) in diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectTool command in WPF Diagram(SfDiagram)

The [SelectTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectTool) command of the diagram helps to change the [DrawingTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool) and [Tool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool) properties to specified values. [SelectToolCommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SelectToolCommandParameter.html) of `SelectTool` command contains the `Tool`, `DrawingTool` and `ConnectorType` informations to enable drawing tool option in diagram.

| Property | Tool | DrawingTool | ConnectorType  |Description |
|---|---|
| Pointer Tool |--- |--- |--- |It is used to select the elements in the diagram.If parameter is not specified , it acts as pointer tool|
| Text Tool | ContinuesDraw |TextNode|---|It is used to create text nodee. |
| Connector Tool| ContinuesDraw |Connector|---| It is used to create orthogonal connector by click and drag on the diagram.If connectortype is not specified , orthogonal connector will be drawn|
| Freehand Tool | ContinuesDraw |FreeHand|---|It is used to create Free hand drawing connections.|
| Line Tool | ContinuesDraw |Connector|Line|It is used to create a straight line connector by click and drag on the diagram.|
| Rectangle Tool| ContinuesDraw |Rectangle|---|It is used to create a rectangle shaped Node by click and drag on the diagram.|
| Ellipse Tool| ContinuesDraw |Ellipse|---|It is used to create an ellipse shaped Node by click and drag on the diagram.|

For details , refer [Tools and DrawingTools](https://help.syncfusion.com/wpf/diagram/tools) 

{% tabs %}

{% highlight Xaml%}

 <Syncfusion:SelectToolCommandParameter DrawingTool="Ellipse" Tool="ContinuesDraw"  x:Key="SelectToolEllipseCommandParameter"/>
 
 <Syncfusion:SelectToolCommandParameter DrawingTool="Connector" Tool="ContinuesDraw"  x:Key="SelectToolConnectorCommandParameter"/>
 
 <Syncfusion:SelectToolCommandParameter DrawingTool="TextNode" Tool="ContinuesDraw"  x:Key="SelectToolTextCommandParameter"/>
 

<Button Height="50" Content="ConnectorTool" Name="Connector" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolConnectorCommandParameter}"></Button>

<Button Height="50" Content="EllipseTool" Name="Ellipse" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolEllipseCommandParameter}"></Button>

<Button Height="50" Content="TextTool" Name="TextNode" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolTextCommandParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.SelectTool.Execute(null);
graphinfo.Commands.SelectTool.Execute(new SelectToolCommandParameter() 
{ 
    Tool = Tool.ContinuesDraw, DrawingTool = DrawingTool.Connector, ConnectorType = ConnectorType.Line 
});

{% endhighlight %}
{% endtabs %}

![Gif for SelectTool command](Commands_Images/Commands_SelectTool.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/SelectToolCommand)