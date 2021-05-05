---
layout: post
title: Flip Command in WPF Diagram control | Syncfusion
description: Learn here all about Flip Command support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Flip Command in WPF Diagram (SfDiagram)

The [Flip](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Flip) command is used to mirror the selected object's content and port in the diagram page in both horizontal and vertical direction. 

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Flip" Name="Flip" Command="Syncfusion:DiagramCommands.Flip"></Button>

{% endhighlight %}

{% highlight C# %}

            IGraphInfo graphinfo = Diagram.Info as IGraphInfo;
            // Apply flip to selected objects.
            graphinfo.Commands.Flip.Execute(null);

{% endhighlight %}
{% endtabs %}

## Flip parameter

The [Flip parameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FlipParameter.html) is used to customize the flip mode and flip direction. If the parameter is null, then the object will be flipped both horizontally and vertically.

### Flip mode 

The [FlipMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FlipMode.html) is used to control the behaviour of the flip object.

| FlipMode | Description |
| --- | --- |
| Content | It is used to enable or disables the flip for object's content. |
| Port | It is used to enable or disables the flip for object's port. |
| FlipMode | It is used to enable or disables the flip for both object's content and port. |
| None | It is used to disables all the flipmode behaviour. |

### Flip

The [Flip](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Flip.html) is used to specify the flip direction in flip command.

| Flip | Description |
| --- | --- |
| Flip | It is used to flip the node or port is mirrored across the both horizontal and vertical axis.|
| HorizontalFlip | It is used to flip the node or port is mirrored across the horizontal axis.|
| VerticalFlip | It is used to flip the node or port is mirrored across the vertical axis. |
| None | It is used to disables all the flip behaviour. |

![Represents the flip](Commands_images/Commands_img7.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Flip%20Command)
