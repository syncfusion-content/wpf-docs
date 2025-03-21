---
layout: post
title: Nudge Commands in WPF Diagram control | Syncfusion®
description: Learn here all about Nudge Commands support in Syncfusion® WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Nudge Commands in WPF Diagram (SfDiagram)

Nudge commands are used to move the selected elements towards up, down, left, or right by 1 pixel. The [IMoveParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IMoveParameter.html) is provided to customize the movement of the selected objects.

Below are the specific nudge commands:

| Commands | Description |
|---|---|
| [MoveUp](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveUp) | The `MoveUp` command moves the selected object towards the top by 1 pixel. |
| [MoveDown](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveDown) | The `MoveDown` command moves the selected object towards the bottom by 1 pixel. |
| [MoveLeft](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveLeft) | The `MoveLeft` command moves the selected object towards the left by 1 pixel. |
| [MoveRight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveRight) | The `MoveRight` command moves the selected object towards the right by 1 pixel. |

{% tabs %}

{% highlight Xaml%}

<Syncfusion:MoveParameter MoveDelta="5" x:Key="MoveupCommandParameter"/> 

<Button Height="50" Content="MoveUp" Name="MoveUp" Command="Syncfusion:DiagramCommands.MoveUp" CommandParameter="{StaticResource MoveupCommandParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Nudge up the selected objects
graphinfo.Commands.MoveUp.Execute(new MoveParameter() { MoveDelta = 5 });

{% endhighlight %}
{% endtabs %}

![Nudge gif](Commands_Images/Commands_img17.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Nudge%20Commands)