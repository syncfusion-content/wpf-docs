---
layout: post
title: Syncfusion | Explore the Group and UnGroup commands.
description: Grouping commands are used to group or ungroup the selected diagramming objects (node or connector) in the diagram page.
platform: wpf
control: SfDiagram
documentation: ug
---

# Grouping commands

Grouping commands are used to group/ungroup the selected diagramming objects such as node and connector in the diagram.

## Group command

Group command is used to group the selected diagramming objects in the diagram page. Group command can be executed by the keyboard shortcut CTRL + G.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Groups the selected elements.
graphinfo.Commands.Group.Execute(null);

{% endhighlight %}
{% endtabs %}

## UnGroup command

UnGroup command is used to ungroup the selected group diagramming objects in the diagram page. UnGroup command can be executed by the keyboard shortcut CTRL + G.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//UnGroups the selected group elements.
graphinfo.Commands.UnGroup.Execute(null);

{% endhighlight %}
{% endtabs %}

![Group/UnGroup gif](Commands_Images/Commands_img12.gif)

Please find the [Group/UnGroup commands sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Grouping%20Commands) to depict these commands.