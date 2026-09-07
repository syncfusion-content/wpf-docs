---
layout: post
title: SetShapeStyle Commands in WPF Diagram | Syncfusion®
description: Apply custom styles to selected diagram elements in Syncfusion® WPF Diagram using the SetShapeStyle command.
platform: wpf
control: SfDiagram
documentation: ug
---

# SetShapeStyle Commands in WPF Diagram

The [SetShapeStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SetShapeStyle) command is used to set a specific style for the selected elements in the [WPF SfDiagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram).

N> The `SetShapeStyle` command is applicable only when one or more diagram elements are selected. If no elements are selected, the command will not perform any operation.

N> The `SetShapeStyle` command requires a valid `Style` object as its command parameter. Passing a `null` value is not supported and may result in an exception.

{% tabs %}

{% highlight xaml%}

<Style TargetType="Path" x:Key="SetShapeStyleParameter">
  <Setter Property="Stretch" Value="Fill"></Setter>
  <Setter Property="Fill" Value="Green"></Setter>
</Style>

<Button Height="50" Content="SetShapeStyle" Name="SetShapeStyle" Command="Syncfusion:DiagramCommands.SetShapeStyle" CommandParameter="{StaticResource SetShapeStyleParameter}"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the Diagram 
SfDiagram diagramcontrol = new SfDiagram();

Style style = new Style();
style.Setters.Add(new Setter() { Property = System.Windows.Shapes.Path.FillProperty, Value = new SolidColorBrush(Colors.Green) });
style.Setters.Add(new Setter() { Property = System.Windows.Shapes.Path.StretchProperty, Value = Stretch.Fill });

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.SetShapeStyle.Execute(style);

{% endhighlight %}
{% endtabs %}

![Gif for SetShapeStyle command](Commands_Images/Commands_SetShapeStyle.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Rotate%20Command)