---
layout: post
title: Undo Redo Commands in WPF SfDiagram | Syncfusion®
description: Reverse or restore diagram changes in Syncfusion® WPF SfDiagram using undo and redo commands for editing operations.
platform: wpf
control: SfDiagram
documentation: ug
---

# Undo Redo Commands in WPF SfDiagram

The [Undo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Undo) command reverses the last editing action performed. For example, some of the basic operations performed on diagram objects such as translation, rotation, resizing, grouping, ungrouping, changing z-order, addition, deletion, and so on, can be reversed. The [Redo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Redo) command restores the last editing action if no other actions have occurred since the last undo.

`Undo` and `Redo` actions are disabled by default, to enable this you can use the `Constraints` property of the SfDiagram.  Please refer to the [GraphConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GraphConstraints.html).

N> Undo and Redo commands are available only when the `GraphConstraints.Undoable` constraint is enabled on the `SfDiagram`. Ensure that this constraint is set before executing the Undo or Redo commands.

{% tabs %}
{% highlight Xaml%}

<Syncfusion:SfDiagram x:Name="diagramcontrol" Constraints="Default,Undoable"/>

<Button Height="50" Content="Undo" Name="Undo" Command="Syncfusion:DiagramCommands.Undo"></Button>

<Button Height="50" Content="Redo" Name="Redo" Command="Syncfusion:DiagramCommands.Redo"></Button>

{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

// To enable the Undo and Redo action
diagramcontrol.Constraints |= GraphConstraints.Undoable;

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// To perform the Undo action in Diagram
graphinfo.Commands.Undo.Execute(null);

// To Perform the Redo action in Diagram
graphinfo.Commands.Redo.Execute(null);

{% endhighlight %}
{% endtabs %}

N> The Undo command reverses the most recent tracked action in the diagram. If there are no actions available in the undo stack, the command will not perform any operation.

N> The Redo command restores the most recently undone action. If there are no actions available in the redo stack, the command will not perform any operation.

![Undo Redo gif](Commands_Images/Commands_img16.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Undo%20Redo)

## See Also
[How to enable Undo/Redo feature in WPF SfDiagram?](https://support.syncfusion.com/kb/article/11090/how-to-enable-undo-redo-feature-in-wpf-diagram-sfdiagram)
