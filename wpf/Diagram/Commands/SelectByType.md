---
layout: post
title: SelectByType Command in WPF Diagram control | Syncfusion
description: Learn here all about SelectByType Command support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# SelectByType Command in WPF Diagram (SfDiagram)

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
