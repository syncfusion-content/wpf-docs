---
layout: post
title: SelectByType Command in WPF SfDiagram | Syncfusion®
description: Select specific diagram element types in Syncfusion® WPF SfDiagram using the SelectByType command for targeted operations.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectByType Command in WPF SfDiagram

The [SelectByType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectByType) command is used to select the specified type (such as NodeViewModel, BpmnNodeViewModel, etc.) of elements in the diagram.

To execute the `SelectByType` command, pass a .NET `Type` object that represents the diagram element type to be selected. For example, use `typeof(NodeViewModel)` in C# or `{x:Type Syncfusion:NodeViewModel}` in XAML to select all elements of the specified type.

N> If the diagram does not contain any elements of the specified type, the `SelectByType` command will not perform any selection and the current selection state remains unchanged.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="SelectByType" Name="SelectByType" Command="Syncfusion:DiagramCommands.SelectByType" CommandParameter="{x:Type Syncfusion:NodeViewModel}"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.SelectByType.Execute(typeof(NodeViewModel));

{% endhighlight %}
{% endtabs %}

![Gif for SelectByType command](Commands_Images/Commands_SelectByType.gif)


[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Rotate%20Command)