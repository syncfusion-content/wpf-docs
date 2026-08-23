---
layout: post
title: Clipboard Commands in WPF SfDiagram | Syncfusion®
description: Use clipboard commands in Syncfusion® WPF SfDiagram to cut, copy, paste, and duplicate selected diagram elements efficiently.
platform: wpf
control: SfDiagram
documentation: ug
---

# Clipboard Commands in WPF SfDiagram

Clipboard commands are used to cut or copy the selected diagram objects to the clipboard and paste the valid clipboard content onto the [WPF Diagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram) page.

## Cut command

The [`Cut`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Cut) command is used to cut the selected diagram objects to the clipboard. Cut command can be executed using the keyboard shortcut CTRL + X.

N> The Cut command is applicable only when one or more diagram elements are selected. If no elements are selected, the command will not perform any operation.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="Cut" Name="Cut" Command="Syncfusion:DiagramCommands.Cut"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Cuts the selected elements from the diagram to the diagram’s clipboard
graphinfo.Commands.Cut.Execute(null);

{% endhighlight %}
{% endtabs %}

## Copy command

The [`Copy`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Copy) command is used to copy the selected diagram objects to the clipboard. Copy command can be executed using the keyboard shortcut CTRL + C.

N> The Copy command is applicable only when one or more diagram elements are selected. If no elements are selected, the command will not perform any operation.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="Copy" Name="Copy" Command="Syncfusion:DiagramCommands.Copy"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copies the selected elements from the diagram to the diagram’s clipboard.
graphinfo.Commands.Copy.Execute(null);

{% endhighlight %}
{% endtabs %}

## Paste command

The [`Paste`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Paste) command is used to paste the clipboard content to the diagram page. Paste command can be executed using the keyboard shortcut CTRL + V.

N> The Paste command is applicable only when the clipboard contains supported diagram content. If the clipboard is empty or contains unsupported content, the command will not perform any operation.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="Paste" Name="Paste" Command="Syncfusion:DiagramCommands.Paste"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Pastes the diagram’s clipboard data (nodes or connectors) into the Diagram.
graphinfo.Commands.Paste.Execute(null);

{% endhighlight %}
{% endtabs %}

## Duplicate command

The [`Duplicate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Duplicate) command is used to copy the selected diagram objects to the clipboard and paste the clipboard content to the diagram page. Duplicate command can be executed using the keyboard shortcut CTRL + D.

N> When the Duplicate command is executed, a copy of the selected diagram elements is created and placed with a slight offset from the original elements to make the duplicated elements immediately visible.

N> The Duplicate command creates copies of the selected diagram elements within the diagram. This operation does not modify or replace the existing contents of the clipboard.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="Duplicate" Name="Duplicate" Command="Syncfusion:DiagramCommands.Duplicate"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copy the diagram objects and Paste the clipboard's data (nodes or connectors) into the Diagram.
graphinfo.Commands.Duplicate.Execute(null);

{% endhighlight %}
{% endtabs %}

![Clipboard gif](Commands_Images/Commands_img11.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Clipboard%20commands)

## See Also
[How to Display Different QuickCommands Based on Nodes in WPF Diagram?](https://support.syncfusion.com/kb/article/17969/how-to-display-different-quickcommands-based-on-nodes-in-wpf-diagram)

[How to disable or override clipboard support](https://support.syncfusion.com/kb/article/9010/how-to-disable-or-override-clipboard-support)