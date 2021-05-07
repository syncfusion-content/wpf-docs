---
layout: post
title: Spacing Commands in WPF Diagram control | Syncfusion
description: Learn here all about Spacing Commands support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Spacing Commands in WPF Diagram (SfDiagram)

Spacing commands are used to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

## SpaceAcross command

The [SpaceAcross](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SpaceAcross) command is used to place selected objects on the page at equal intervals from each other horizontally.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SpaceAcross" Name="SpaceAcross" Command="Syncfusion:DiagramCommands.SpaceAcross"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes horizontally
graphinfo.Commands.SpaceAcross.Execute(null);

{% endhighlight %}
{% endtabs %}

![SPace Across](Commands_images/Commands_img3.gif)

## SpaceDown command

The [SpaceDown](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SpaceDown) command is used to place selected objects on the page at equal intervals from each other vertically.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SpaceDown" Name="SpaceDown" Command="Syncfusion:DiagramCommands.SpaceDown"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes vertically
graphinfo.Commands.SpaceDown.Execute(null);

{% endhighlight %}
{% endtabs %}

![SPace Down](Commands_images/Commands_img4.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Spacing%20Commands)
