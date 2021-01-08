---
layout: post
title: Syncfusion | Explore the Group and UnGroup commands.
description: The Grouping commands are used to group or ungroup the selected diagramming objects (node or connector) in the diagram page.
platform: wpf
control: SfDiagram
documentation: ug
---

# Grouping commands in WPF Diagram(SfDiagram)

The Grouping commands are used to group or ungroup the selected diagramming objects such as node and connector in the diagram.

## Group command

The [Group](help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IDiagramCommands~Group.html) command is used to group the selected diagramming objects in the diagram page. The Group command can be executed by the keyboard shortcut CTRL + G.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Cancel" Name="Cancel" Command="Syncfusion:DiagramCommands.Group"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Groups the selected elements.
graphinfo.Commands.Group.Execute(null);

{% endhighlight %}
{% endtabs %}

## UnGroup command

The [UnGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_UnGroup) command is used to ungroup the selected group diagramming objects in the diagram page. UnGroup command can be executed by the keyboard shortcut CTRL + G.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Cancel" Name="Cancel" Command="Syncfusion:DiagramCommands.UnGroup"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//UnGroups the selected group elements.
graphinfo.Commands.UnGroup.Execute(null);

{% endhighlight %}
{% endtabs %}

![Group/UnGroup gif](Commands_Images/Commands_img12.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Grouping%20Commands)