---
layout: post
title: Grouping Commands in WPF Diagram control | Syncfusion
description: Learn here all about Grouping Commands support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Grouping Commands in WPF Diagram (SfDiagram)

The Grouping commands are used to group or ungroup the selected diagramming objects such as node and connector in the diagram.

## Group command

The [`Group`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramCommands.html#Syncfusion_UI_Xaml_Diagram_DiagramCommands_Group) command is used to group the selected diagramming objects in the diagram page. The Group command can be executed by the keyboard shortcut CTRL + G.

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

The [`UnGroup`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_UnGroup) command is used to ungroup the selected group diagramming objects in the diagram page. UnGroup command can be executed by the keyboard shortcut CTRL + SHIFT + U.

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
