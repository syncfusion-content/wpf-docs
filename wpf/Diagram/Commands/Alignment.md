---
layout: post
title: Alignment Commands in WPF Diagram control | Syncfusion
description: Learn here all about Alignment Commands support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Alignment Commands in WPF Diagram (SfDiagram)

Alignment commands are used to align the selected objects such as Nodes and Connectors on a page with respect to a reference object(first item in the selection list).

## AlignLeft command 

The [AlignLeft](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignLeft) command is used to align all the selected objects along the left corner of the reference object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignLeft" Name="AlignLeft" Command="Syncfusion:DiagramCommands.AlignLeft"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction to Left
graphinfo.Commands.AlignLeft.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignRight command

The [AlignRight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignRight) command is used to align all the selected objects along the right corner of the reference object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignRight" Name="AlignRight" Command="Syncfusion:DiagramCommands.AlignRight"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction to Right
graphinfo.Commands.AlignRight.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignCenter command

The [AlignCenter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignCenter) command is used to center all selected objects vertically. It aligns selected objects to the center with respect to the horizontal axis by changing the x-coordinate of the object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignCenter" Name="AlignCenter" Command="Syncfusion:DiagramCommands.AlignCenter"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction to Center vertically
graphinfo.Commands.AlignCenter.Execute(null);

{% endhighlight %}
{% endtabs %}

![Gif for Align commands](Commands_Images/Commands_img1.gif)

## AlignTop command 

The [AlignTop](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignTop) command is used to align all the selected objects along the top corner of the reference object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignTop" Name="AlignTop" Command="Syncfusion:DiagramCommands.AlignTop"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction to Top
graphinfo.Commands.AlignTop.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignBottom command

The [AlignBottom](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignBottom) command is used to align all the selected objects along the bottom corner of the reference object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignBottom" Name="AlignBottom" Command="Syncfusion:DiagramCommands.AlignBottom"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Bottom
graphinfo.Commands.AlignBottom.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignMiddle command

The [AlignMiddle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_AlignMiddle) command is used to center all selected objects horizontally. It aligns selected objects to the center with respect to the vertical axis by changing the y-coordinate of the object.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="AlignMiddle" Name="AlignMiddle" Command="Syncfusion:DiagramCommands.AlignMiddle"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction to Center horizontally
graphinfo.Commands.AlignCenter.Execute(null);

{% endhighlight %}
{% endtabs %}

![Gif for Align commands](Commands_Images/Commands_img2.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Alignment%20Commands)
