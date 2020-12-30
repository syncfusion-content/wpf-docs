---
layout: post
title: Syncfusion | Explore the SelectByType command.
description: SelectByType Command is used to select the specified type of elements(NodeViewModel,BpmnNodeViewModel) in diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectByType command in WPF Diagram(SfDiagram)

The [SelectByType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SelectByType) command is used to select the specified type (NodeViewModel,BpmnNodeViewModel,...) of elements in the diagram.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SelectByType" Name="SelectByType" Command="Syncfusion:DiagramCommands.SelectByType" CommandParameter="{x:Type Syncfusion:NodeViewModel}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.SelectByType.Execute(typeof(NodeViewModel));

{% endhighlight %}
{% endtabs %}

![Gif for SelectByType command](Commands_Images/Commands_SelectByType.gif)


[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Commands%20Sample)