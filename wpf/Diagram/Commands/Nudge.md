---
layout: post
title: Syncfusion | Explore the Nudge commands.
description: Nudge commands are used to move the selected elements such as nodes and connectors in diagram page towards up, down, left, or right by 1 pixel.
platform: wpf
control: SfDiagram
documentation: ug
---

# Nudge in the WPF Diagram(SfDiagram)

Nudge commands are used to move the selected elements towards up, down, left, or right by 1 pixel. The [IMoveParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IMoveParameter.html) is provided to customize the movement of the selected objects. The Nudge Commands as follows.

| Commands | Description |
|---|---|
| NudgeUp | The [NudgeUp](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveUp) command moves the selected object towards the top by 1 pixel. |
| NudgeDown | The [NudgeDown](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveDown) command moves the selected object towards the bottom by 1 pixel. |
| NudgeLeft | The [NudgeLeft](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveLeft) command moves the selected object towards the left by 1 pixel. |
| NudgeRight | The [NudgeRight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_MoveRight) command moves the selected object towards the right by 1 pixel. |

{% tabs %}
{% highlight C# %}

            IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

            // Nudge up the selected objects
            graphinfo.Commands.MoveUp.Execute(new MoveParameter() { MoveDelta = 5 });

{% endhighlight %}
{% endtabs %}

![Nudge gif](Commands_Images/Commands_img17.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Nudge%20Commands) 