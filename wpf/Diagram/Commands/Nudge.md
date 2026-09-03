---
layout: post
title: Nudge Commands in WPF Diagram | Syncfusion®
description: Move selected diagram elements in Syncfusion® WPF Diagram using nudge commands with customizable movement distances and directions.
platform: wpf
control: SfDiagram
documentation: ug
---

# Nudge Commands in WPF Diagram

Nudge commands are used to move the selected elements towards up, down, left, or right by 1 pixel. The [MoveParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MoveParameter.html) class, which implements the [IMoveParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IMoveParameter.html) interface, is provided to customize the movement of the selected objects.

To customize the nudge distance, create a `MoveParameter` instance and set its [MoveDelta](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MoveParameter.html#Syncfusion_UI_Xaml_Diagram_MoveParameter_MoveDelta) property. Then, pass the parameter to the required nudge command through the command parameter or the `Execute` method.

Below are the specific nudge commands:

| Commands | Description |
|---|---|
| [MoveUp](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveUp) | The `MoveUp` command moves the selected object towards the top by 1 pixel. |
| [MoveDown](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveDown) | The `MoveDown` command moves the selected object towards the bottom by 1 pixel. |
| [MoveLeft](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveLeft) | The `MoveLeft` command moves the selected object towards the left by 1 pixel. |
| [MoveRight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveRight) | The `MoveRight` command moves the selected object towards the right by 1 pixel. |

N> Nudge commands are applicable only when one or more diagram elements are selected. If no elements are selected, the command will not perform any operation.

{% tabs %}

{% highlight xaml%}

<Syncfusion:MoveParameter MoveDelta="5" x:Key="MoveupCommandParameter"/> 

<Button Height="50" Content="MoveUp" Name="MoveUp" Command="Syncfusion:DiagramCommands.MoveUp" CommandParameter="{StaticResource MoveupCommandParameter}"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the Diagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Nudge up the selected objects
graphinfo.Commands.MoveUp.Execute(new MoveParameter() { MoveDelta = 5 });

{% endhighlight %}
{% endtabs %}

![Nudge gif](Commands_Images/Commands_img17.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Nudge%20Commands)