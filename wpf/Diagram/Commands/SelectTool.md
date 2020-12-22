---
layout: post
title: Syncfusion | Explore the SelectTool commands.
description: SelectTool Commands are used to enable drawing tool options such as ConnectorTool, Node (Rectangel, Ellipse) in diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectTool command in WPF Diagram(SfDiagram)

[SelectTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectTool) command of the [DrawingTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool) helps to change the `SelectTool` and [Tool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool) properties to specified values. [SelectToolCommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SelectToolCommandParameter.html) of `SelectTool` command contains the `Tool`, `DrawingTool` and `ConnectorType` informations to enable drawing tool option in diagram.

| Tool | Description |
|---|---|
| PointerTool | Allows us to select the elements in the diagram.|
| TextTool | Allows you to create text nodee. |
| ConnectorTool |Allows you to create orthogonal connector by click and drag on the diagram.|
| FreedomTool |Allows you to create Free hand drawing connections.|
| LineTool |Allows you to create a straight line connector by click and drag on the diagram.|
| RectangleTool | Allows you to create a rectangle shaped Node by click and drag on the diagram.|
| EllipseTool | Allows you to create an ellipse shaped Node by click and drag on the diagram.|

{% tabs %}

{% highlight Xaml%}

 <Syncfusion:SelectToolCommandParameter DrawingTool="Ellipse" Tool="ContinuesDraw"  x:Key="SelectToolEllipseCommandParameter"/>
 <Syncfusion:SelectToolCommandParameter DrawingTool="Rectangle" Tool="ContinuesDraw"  x:Key="SelectToolRectangleCommandParameter"/>
 <Syncfusion:SelectToolCommandParameter DrawingTool="Connector" Tool="ContinuesDraw"  x:Key="SelectToolConnectorCommandParameter"/>
 <Syncfusion:SelectToolCommandParameter DrawingTool="FreeHand" Tool="ContinuesDraw"  x:Key="SelectToolFreehandCommandParameter"/>
 <Syncfusion:SelectToolCommandParameter DrawingTool="TextNode" Tool="ContinuesDraw"  x:Key="SelectToolTextCommandParameter"/>
 <Syncfusion:SelectToolCommandParameter DrawingTool="Connector" Tool="ContinuesDraw" ConnectorType="Line"  x:Key="SelectToolLineCommandParameter"/>

<Button Height="50" Content="ConnectorTool" Name="Connector" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolConnectorCommandParameter}"></Button>
<Button Height="50" Content="EllipseTool" Name="Ellipse" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolEllipseCommandParameter}"></Button>
<Button Height="50" Content="FreedomTool" Name="Freehand" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolFreehandCommandParameter}"></Button>
<Button Height="50" Content="PointerTool" Name="Select" Command="Syncfusion:DiagramCommands.SelectTool"></Button>
<Button Height="50" Content="TextTool" Name="TextNode" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolTextCommandParameter}"></Button>
<Button Height="50" Content="LineTool" Name="Line" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolLineCommandParameter}"></Button>
<Button Height="50" Content="RectangleTool" Name="Rectangle" Command="Syncfusion:DiagramCommands.SelectTool" CommandParameter="{StaticResource SelectToolRectangleCommandParameter}"></Button>

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