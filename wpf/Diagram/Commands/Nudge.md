---
layout: post
title: Syncfusion | Explore the Nudge commands.
description: Nudge commands are used to move the selected elements such as nodes and connectors in diagram page towards up, down, left or right by 1 pixel.
platform: wpf
control: SfDiagram
documentation: ug
---

# Nudge

Nudge commands are used to move the selected elements towards up, down, left or right by 1 pixel. [IMoveParameter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.MoveParameter_members.html) is provided to customize the movement of the selected objects. The Nudge Commands as follows.

| Commands | Description |
|---|---|
| NudgeUp | The NudgeUp command moves the selected object towards the top by 1 pixel. |
| NudgeDown | The NudgeDown command moves the selected object towards the bottom by 1 pixel. |
| NudgeLeft | The NudgeLeft command moves the selected object towards the left by 1 pixel. |
| NudgeRight | The NudgeRight command moves the selected object towards the right by 1 pixel. |

{% tabs %}
{% highlight C# %}

            IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

            // Nudge up the selected objects
            graphinfo.Commands.MoveUp.Execute(new MoveParameter() { MoveDelta = 5 });

{% endhighlight %}
{% endtabs %}

![Nudge gif](Commands_Images/Commands_img17.gif)

Please find the [Nudge Sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Nudge_Commands-101739046) to depict these commands.