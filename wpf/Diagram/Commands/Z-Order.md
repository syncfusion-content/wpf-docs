---
layout: post
title: Syncfusion | Explore the Z-order usage with the Z-order commands.
description: Z – Order commands are used to visually arrange the selected objects such as Nodes and Connectors on the diagram page with its Z-order values.
platform: wpf
control: SfDiagram
documentation: ug
---

# Z – Order in WPF Diagram(SfDiagram)

Z – Order commands are used to visually arrange the selected objects such as Nodes and Connectors on the diagram page with its Z-order values.

## BringToFront

The [BringToFront](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_BringToFront) command is used to visually brings the selected element to the front over all other overlapped elements. 

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="BringToFront" Name="BringToFront" Command="Syncfusion:DiagramCommands.BringToFront"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Brings to front
graphinfo.Commands.BringToFront.Execute(null);

{% endhighlight %}
{% endtabs %}

## SendToBack

The [SendToBack](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SendToBack) command visually moves the selected elements behind all the other overlapped elements. 

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SendToBack" Name="SendToBack" Command="Syncfusion:DiagramCommands.SendToBack"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Send To Back
graphinfo.Commands.SendToBack.Execute(null);

{% endhighlight %}
{% endtabs %}

![Represents the send to back](Commands_images/Commands_img8.gif)

## SendBackward

The [SendBackward](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SendBackward) command visually moves the selected elements behind the underlying element.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SendBackward" Name="SendBackward" Command="Syncfusion:DiagramCommands.SendBackward"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Send To Backward
graphinfo.Commands.SendBackward.Execute(null);

{% endhighlight %}
{% endtabs %}

## BringForward

The [BringForward](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_BringForward) command visually moves the selected element over the nearest overlapping element.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="BringForward" Name="BringForward" Command="Syncfusion:DiagramCommands.BringForward"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Brings To Forward
graphinfo.Commands.BringForward.Execute(null);

{% endhighlight %}
{% endtabs %}

![Represents the bring forward](Commands_images/Commands_img9.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Z-Order%20Commands)