---
layout: post
title: Syncfusion | Explore the Undo and Redo commands.
description:  Undo reverse the last operation done in diagram with undo command and redo restores the last operation done in diagram with redo command.
platform: wpf
control: SfDiagram
documentation: ug
---

# Undo and Redo in WPF Diagram(SfDiagram)

The [Undo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Undo) command reverses the last editing action performed. For example, some of the basic operations performed on diagram objects such as translation, rotation, resizing, grouping, ungrouping, changing z-order, addition, deletion, and so on, can be reversed. The [Redo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Redo) command restores the last editing action if no other actions have occurred since the last undo.

Undo and Redo actions are disabled by default, to enable this you can use the `Constraints` property of the SfDiagram.  Please refer to the [GraphConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GraphConstraints.html)

{% tabs %}
{% highlight C# %}

// To enable the Undo and Redo action
diagram.Constraints |= GraphConstraints.Undoable;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// To perform the Undo action in Diagram
graphinfo.Commands.Undo.Execute(null);

// To Perform the Redo action in Diagram
graphinfo.Commands.Redo.Execute(null);

{% endhighlight %}
{% endtabs %}

![Undo Redo gif](Commands_Images/Commands_img16.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Undo%20Redo)