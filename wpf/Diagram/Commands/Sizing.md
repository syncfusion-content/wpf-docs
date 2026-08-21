---
layout: post
title: Sizing Commands in WPF SfDiagram | Syncfusion®
description: Resize selected diagram elements in Syncfusion® WPF SfDiagram by matching the width, height, or size of a reference object.
platform: wpf
control: SfDiagram
documentation: ug
---

# Sizing Commands in WPF SfDiagram

Sizing commands are used to resize all selected objects based on width, height, or size of the reference object (FirstSelectedItem).

N> Sizing commands use the `FirstSelectedItem` as the reference object. The size of this object is preserved, and all other selected objects are resized to match its width, height, or overall size, depending on the command being executed. Therefore, the sizing result depends on which object is selected first.

N> Sizing commands require at least two selected objects. The first selected object is used as the reference object, and the remaining selected objects are resized based on it. If only one object is selected or no objects are selected, the sizing command will not produce any change.

## SameSize command

The [`SameSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameSize) command is used to resize all the selected objects based on the size of the first item in the selection list.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="SameSize" Name="SameSize" Command="Syncfusion:DiagramCommands.SameSize"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Scales the selected items to the size of first selected object
graphinfo.Commands.SameSize.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameHeight command

The [`SameHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameHeight) command is used to resize all the selected objects based on the height of the first item in the selection list.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="SameHeight" Name="SameHeight" Command="Syncfusion:DiagramCommands.SameHeight"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Vertically scales the selected items to the height of first selected object
graphinfo.Commands.SameHeight.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameWidth command

The [`SameWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameWidth) command is used to resize all the selected objects based on the width of the first item in the selection list.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="SameWidth" Name="SameWidth" Command="Syncfusion:DiagramCommands.SameWidth"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Horizontally scales the selected items to the width of first selected object
graphinfo.Commands.SameWidth.Execute(null);

{% endhighlight %}
{% endtabs %}

![Sizing commands](Commands_Images/Commands_img5.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Sizing%20Commands)