# Tools

Drawing Tools

Drawing tool allow you to draw any kind of node/connector during runtime by clicking and dragging on the Diagram page.

Shapes

To draw a shape, You have to activate the drawing tool by using the Tool property and you need to set the event for GetDrawType. The following code illustrates how to draw a rectangle at run time.

[XAML]

<table>
<tr>
<td>
<Style TargetType="Path" x:Key="shapestyle"><br/><br/><Setter Property="Fill" Value="#fcbc7c"></Setter><br/><br/><Setter Property="Stroke" Value="#f89b4c"/><br/><br/><Setter Property="Stretch" Value="Fill"></Setter><br/><br/></Style><br/><br/><Style TargetType="{x:Type diagram:Node}"><br/><br/><Setter Property="Shape"><br/><br/><Setter.Value><br/><br/><RectangleGeometry Rect="10,10,10,10"/><br/><br/></Setter.Value><br/><br/></Setter><br/><br/><Setter Property="ShapeStyle" Value="{StaticResource shapestyle}"></Setter><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;<br/><br/>diagram.DrawingTool = DrawingTool.Node;<br/><br/>diagram.Tool = Tool.ContinuesDraw;<br/><br/>private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)<br/><br/>{<br/><br/>args.DrawItem = new TextBlock()<br/><br/>{<br/><br/>Text = "Rectangle",<br/><br/>HorizontalAlignment = HorizontalAlignment.Center,<br/><br/>VerticalAlignment = VerticalAlignment.Center<br/><br/>};<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![](Tools_images/Tools_img1.jpeg)


The following code example illustrates how to draw a path.

[XAML]

<table>
<tr>
<td>
<Style TargetType="Path" x:Key="shapestyle"><br/><br/><Setter Property="Fill" Value="#fbe172"></Setter><br/><br/><Setter Property="Stroke" Value="Black"/><br/><br/><Setter Property="Stretch" Value="Fill"></Setter><br/><br/></Style><br/><br/><Style TargetType="{x:Type diagram:Node}"><br/><br/><Setter Property="Shape" Value="M13.560 67.524 L 21.941 41.731 L 0.000 25.790 L<br/><br/>27.120 25.790 L 35.501 0.000 L 43.882 25.790 L 71.000 <br/><br/>25.790 L 49.061 41.731 L 57.441 67.524 L 35.501 <br/><br/>51.583 z"></Setter><br/><br/><Setter Property="ShapeStyle" Value="{StaticResource shapestyle}"></Setter><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;<br/><br/>diagram.DrawingTool = DrawingTool.Node;<br/><br/>diagram.Tool = Tool.ContinuesDraw;<br/><br/>private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)<br/><br/>{<br/><br/>args.DrawItem = new TextBlock()<br/><br/>{<br/><br/>Text="Path",<br/><br/>HorizontalAlignment = HorizontalAlignment.Center,<br/><br/>VerticalAlignment = VerticalAlignment.Center<br/><br/>};<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![](Tools_images/Tools_img2.jpeg)


Connectors

To draw Connectors, you have to set the Connector to DrawingTool property. The drawing tool can be activated by using the Tool property as shown. The following code example illustrates how to draw a straight line Connector.

[XAML]

<table>
<tr>
<td>
<Style x:Key="decoratorstyle" TargetType="Path"><br/><br/><Setter Property="Stroke" Value="Black" /><br/><br/><Setter Property="Fill" Value="Black" /><br/><br/><Setter Property="StrokeThickness" Value="1" /><br/><br/></Style><br/><br/><Style TargetType="Path" x:Key="connectorstyle"><br/><br/><Setter Property="Stroke" Value="Black"></Setter><br/><br/><Setter Property="StrokeThickness" Value="2"></Setter><br/><br/></Style><br/><br/><Style TargetType="{x:Type diagram:Connector}"><br/><br/><Setter Property="TargetDecoratorStyle" Value="{StaticResource decoratorstyle1}"/><br/><br/><Setter Property="ConnectorGeometryStyle" Value="{StaticResource connectorstyle}"/><br/><br/></Style><br/><br/><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
diagram.DrawingTool = DrawingTool.Connector;<br/><br/>diagram.Tool = Tool.DrawOnce;<br/><br/><br/><br/></td></tr>
</table>
![](Tools_images/Tools_img3.jpeg)


Text

Diagram allows you to create a text Node as soon as you click on the Diagram page. The following code illustrates how to draw a text.

<table>
<tr>
<td>
(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;<br/><br/>diagram.DrawingTool = DrawingTool.Node;<br/><br/>diagram.Tool = Tool.ContinuesDraw;<br/><br/>private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)<br/><br/>{<br/><br/>args.DrawItem = new TextBlock()<br/><br/>{<br/><br/>Text="text",<br/><br/>HorizontalAlignment = HorizontalAlignment.Center,<br/><br/>VerticalAlignment = VerticalAlignment.Center<br/><br/>};<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
Tool Selection

There are some functionalities that can be achieved by clicking and dragging on the Diagram surface. They are as follows.

* Draw selection rectangle – MultipleSelect tool
* Pan the Diagram – Zoom pan
* Draw Nodes/Connectors – ContinuousDraw / DrawOnce

As all the three behaviors are completely different, You can achieve only one behavior at a time based on the tool that you choose. When more than one of those are applied, a tool is activated based on the precedence given in the following table.

<table>
<tr>
<td>
Precedence<br/><br/></td><td>
Tools<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
1.<br/><br/></td><td>
ContinuesDraw<br/><br/></td><td>
Allows you to draw the Nodes or Connectors continuously. Once it is activated, you cannot perform any other interaction in the Diagram.<br/><br/></td></tr>
<tr>
<td>
2.<br/><br/></td><td>
DrawOnce<br/><br/></td><td>
Allows you to draw single Node or Connector. Once you complete the DrawOnce action, SingleSelect and MultipleSelect tools are automatically enabled.<br/><br/></td></tr>
<tr>
<td>
3.<br/><br/></td><td>
ZoomPan<br/><br/></td><td>
Allows you to pan the Diagram. When you enable both the SingleSelect and ZoomPan tools, you can perform the basic interaction as the cursor hovers Node/Connector. Panning is enebled when cursor hovers the Diagram.<br/><br/></td></tr>
<tr>
<td>
4.<br/><br/></td><td>
MultipleSelect<br/><br/></td><td>
Allows you to select multiple Nodes and Connectors. When you enable both the MultipleSelect and ZoomPan tools, cursor hovers the Diagram. When panning is enabled, you cannot select multiple Nodes.<br/><br/></td></tr>
<tr>
<td>
5.<br/><br/></td><td>
SingleSelect<br/><br/></td><td>
Allows you to select individual or Connectors.<br/><br/></td></tr>
<tr>
<td>
6.<br/><br/></td><td>
None<br/><br/></td><td>
Disables all tools.<br/><br/></td></tr>
</table>
You can set the desired tool to the Tool property of the Diagram. The following code illustrates how to enable single/multiple tools.

<table>
<tr>
<td>
{{'__//__'| markdownify }}{{'__To__ '| markdownify }}{{'__Enable__ '| markdownify }}{{'__Single__ '| markdownify }}{{'__Tool__'| markdownify }}{{'____'| markdownify }}<br/><br/>diagram.Tool = Tool.SingleSelect;<br/><br/>{{'__//__'| markdownify }}{{'__To__ '| markdownify }}{{'__Enable__ '| markdownify }}{{'__multiple__ '| markdownify }}{{'__tools__'| markdownify }}{{'____'| markdownify }}<br/><br/>diagram.Tool = Tool.SingleSelect | Tool.ZoomPan; <br/><br/><br/><br/></td></tr>
</table>
