---
layout: post
title: Spacing Commands in WPF SfDiagram | Syncfusion®
description: Arrange selected diagram elements in Syncfusion® WPF SfDiagram with equal horizontal and vertical spacing using spacing commands.
platform: wpf
control: SfDiagram
documentation: ug
---

# Spacing Commands in WPF SfDiagram

Spacing commands are used to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

N> Spacing commands use the first and last objects in the current selection as reference objects. These reference objects retain their positions, and the remaining selected objects are evenly distributed between them. Therefore, the resulting spacing may vary depending on the selection order.

N> At least three objects must be selected to apply spacing commands effectively. The first and last selected objects are used as reference objects, and the remaining selected objects are distributed evenly between them. If fewer than three objects are selected, the spacing command will not produce any visible change.

## SpaceAcross command

The [`SpaceAcross`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SpaceAcross) command is used to place selected objects on the page at equal horizontal intervals.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SpaceAcross" Name="SpaceAcross" Command="Syncfusion:DiagramCommands.SpaceAcross"></Button>

{% endhighlight %}

{% highlight C# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();


IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes horizontally
graphinfo.Commands.SpaceAcross.Execute(null);

{% endhighlight %}
{% endtabs %}

![Space Across](Commands_images/Commands_img3.gif)

## SpaceDown command

The [`SpaceDown`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SpaceDown) command is used to place selected objects on the page at equal vertical intervals.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SpaceDown" Name="SpaceDown" Command="Syncfusion:DiagramCommands.SpaceDown"></Button>

{% endhighlight %}

{% highlight C# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();


IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes vertically
graphinfo.Commands.SpaceDown.Execute(null);

{% endhighlight %}
{% endtabs %}

![Space Down](Commands_images/Commands_img4.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Spacing%20Commands)