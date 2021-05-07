---
layout: post
title: SetShapeStyle Commands in WPF Diagram control | Syncfusion
description: Learn here all about SetShapeStyle Commands support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# SetShapeStyle Commands in WPF Diagram (SfDiagram)

The [SetShapeStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SetShapeStyle) command is used to set a specific style for the selected elements in the diagram.

{% tabs %}

{% highlight Xaml%}

<Style TargetType="Path" x:Key="SetShapeStyleParameter">
  <Setter Property="Stretch" Value="Fill"></Setter>
  <Setter Property="Fill" Value="Green"></Setter>
</Style>

<Button Height="50" Content="SetShapeStyle" Name="SetShapeStyle" Command="Syncfusion:DiagramCommands.SetShapeStyle" CommandParameter="{StaticResource SetShapeStyleParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

Style style = new Style();
style.Setters.Add(new Setter() { Property = System.Windows.Shapes.Path.FillProperty, Value = new SolidColorBrush(Colors.Green) });
style.Setters.Add(new Setter() { Property = System.Windows.Shapes.Path.StretchProperty, Value = Stretch.Fill });

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.SetShapeStyle.Execute(style);

{% endhighlight %}
{% endtabs %}

![Gif for SelectByType command](Commands_Images/Commands_SetShapeStyle.gif)


[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Rotate%20Command)
