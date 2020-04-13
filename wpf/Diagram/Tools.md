---
layout: post
title: Syncfusion Diagram allows to draw, select or pan with click and drag.
description: How to draw shapes or pan Diagram by clicking and dragging over the Diagram surface how to enable or disbale the single and multiple tools to diagram?
platform: wpf
control: SfDiagram
documentation: ug
---

# Tools

## Drawing Tools

Drawing tool allow you to draw any kind of node/connector during runtime by clicking and dragging on the Diagram page.

### Shapes

To draw a shape, You have to activate the drawing tool by using the Tool property and you need to set the event for GetDrawType.

{% tabs %}
{% highlight xaml %}

<Style TargetType="Path" x:Key="shapestyle">
  <Setter Property="Fill" Value="#fbe172"/>
  <Setter Property="Stroke" Value="Black"/>
  <Setter Property="Stretch" Value="Fill"/>
</Style>

<Style TargetType="{x:Type diagram:Node}">
  <Setter Property="Shape" Value="M13.560 67.524 L 21.941 41.731 L 0.000 25.790 L
                                  27.120 25.790 L 35.501 0.000 L 43.882 25.790 L 71.000 
                                  25.790 L 49.061 41.731 L 57.441 67.524 L 35.501 
                                  51.583 z"/>
  <Setter Property="ShapeStyle" Value="{StaticResource shapestyle}"/>
</Style>

{% endhighlight %}

{% highlight C# %}

//GetDrawType event is used to specify which item have to be drawn by the user.

(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;
diagram.DrawingTool = DrawingTool.Node;
diagram.Tool = Tool.ContinuesDraw;

private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)
{
	args.DrawItem = new TextBlock()
	{
		Text="Path",
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center
	};
}

{% endhighlight %}
{% endtabs %}

![draw star shape](Tools_images/Tools_img2.jpeg)

* `GetDrawType` event will invoke when start drawing and get DrawItem (i.e which item you will draw) from the user.To explore about arguments, please refer to the [DrawTypeEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DrawTypeEventArgs.html) .

### Text

Diagram allows you to create a text Node as soon as you click on the Diagram page. The following code illustrates how to draw a text.

{% tabs %}
{% highlight C# %}

(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;
diagram.DrawingTool = DrawingTool.Node;
diagram.Tool = Tool.ContinuesDraw;

private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)
{
	args.DrawItem = new TextBlock()
	{
		Text="text",
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center
	};
}

{% endhighlight %}
{% endtabs %}

### Connectors

To draw Connectors, you have to set the Connector to DrawingTool property. The drawing tool can be activated by using the Tool property as shown. The following code example illustrates how to draw a straight line Connector.

{% tabs %}
{% highlight xaml %}

<Style x:Key="decoratorstyle" TargetType="Path">
  <Setter Property="Stroke" Value="Black" />
  <Setter Property="Fill" Value="Black" />
  <Setter Property="StrokeThickness" Value="1" />
</Style>

<Style TargetType="Path" x:Key="connectorstyle">
  <Setter Property="Stroke" Value="Black"></Setter>
  <Setter Property="StrokeThickness" Value="2"></Setter>
</Style>

<Style TargetType="{x:Type diagram:Connector}">
  <Setter Property="TargetDecoratorStyle" Value="{StaticResource decoratorstyle1}"/>
  <Setter Property="ConnectorGeometryStyle" Value="{StaticResource connectorstyle}"/>
</Style>

{% endhighlight %}

{% highlight C# %}

diagram.DrawingTool = DrawingTool.Connector;
diagram.Tool = Tool.DrawOnce;

{% endhighlight %}
{% endtabs %}

![draw straight line connector](Tools_images/Tools_img3.jpg)

Diagram allows you to establish connection with Node/Port as soon as you click on the Node/Port.

* `ObjectDrawn` event will invoke with drawing state.To explore about arguments,  please refer to the [ObjectDrawnEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ObjectDrawnEventArgs.html) .

### FreeHand drawing

Draw Bezier connections using freehand drawing. [DrawingTool](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DrawingTool.html) property is used to choose the FreeHand drawing.

{% tabs %}
{% highlight C# %}

// Enable the FreeHand drawing
diagram.DrawingTool = DrawingTool.FreeHand;

// Enable the Tool
//diagram.Tool = Tool.DrawOnce;

{% endhighlight %}
{% endtabs %}

![free hand drawing](Interaction_images/FreeHand_img1.gif)

FreeFormEvent will notify the current drawing Connector and drawing State in [FreeFormDrawingEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.FreeFormDrawingEventArgs_members.html). 

## Tool Selection

There are some functionalities that can be achieved by clicking and dragging on the Diagram surface. They are as follows.

* Draw selection rectangle – MultipleSelect tool
* Pan the Diagram – Zoom pan
* Draw Nodes/Connectors – ContinuousDraw / DrawOnce

As all the three behaviors are completely different, You can achieve only one behavior at a time based on the tool that you choose. When more than one of those are applied, a tool is activated based on the precedence given in the following table.

| Tools | Description |
|---|---|
| ContinuesDraw | Allows you to draw the Nodes or Connectors continuously. Once it is activated, you cannot perform any other interaction in the Diagram. |
| DrawOnce | Allows you to draw single Node or Connector. Once you complete the DrawOnce action, SingleSelect and MultipleSelect tools are automatically enabled. |
| ZoomPan | Allows you to pan the Diagram. When you enable both the SingleSelect and ZoomPan tools, you can perform the basic interaction as the cursor hovers Node/Connector. Panning is enebled when cursor hovers the Diagram. |
| MultipleSelect | Allows you to select multiple Nodes and Connectors. When you enable both the MultipleSelect and ZoomPan tools, cursor hovers the Diagram. When panning is enabled, you cannot select multiple Nodes. |
| SingleSelect | Allows you to select individual or Connectors. |
| None | Disables all tools. |

You can set the desired tool to the Tool property of the Diagram. The following code illustrates how to enable single/multiple tools.

{% tabs %}
{% highlight C# %}

//To Enable Single Tool
diagram.Tool = Tool.SingleSelect;

//To Enable multiple tools
diagram.Tool = Tool.SingleSelect | Tool.ZoomPan; 
 
{% endhighlight %}
{% endtabs %}

Find the [Drawing tools sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/DrawingTools) to depict the Tools.