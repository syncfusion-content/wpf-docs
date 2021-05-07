---
layout: post
title: Clipboard Commands in WPF Diagram control | Syncfusion
description: Learn here all about Clipboard Commands support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Clipboard Commands in WPF Diagram (SfDiagram)

Clipboard commands are used to cut or copy the selected diagram objects to the clipboard and paste the valid clipboard content into the diagram page.

## Cut command

The [Cut](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Cut) command is used to cut the selected diagram objects to the clipboard. Cut command can be executed by the keyboard shortcut CTRL + X.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Cut" Name="Cut" Command="Syncfusion:DiagramCommands.Cut"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Cuts the selected elements from the diagram to the diagram’s clipboard
graphinfo.Commands.Cut.Execute(null);

{% endhighlight %}
{% endtabs %}

## Copy command

The [Copy](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Copy) command is used to copy the selected diagram objects to the clipboard. Copy command can be executed by the keyboard shortcut CTRL + C.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Copy" Name="Copy" Command="Syncfusion:DiagramCommands.Copy"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copies the selected elements from the diagram to the diagram’s clipboard.
graphinfo.Commands.Copy.Execute(null);

{% endhighlight %}
{% endtabs %}

## Paste command

The [Paste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Paste) command is used to paste the clipboard content to the diagram page. Paste command can be executed by the keyboard shortcut CTRL + V.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Paste" Name="Paste" Command="Syncfusion:DiagramCommands.Paste"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Pastes the diagram’s clipboard data (nodes or connectors) into the Diagram.
graphinfo.Commands.Paste.Execute(null);

{% endhighlight %}
{% endtabs %}

## Duplicate command

The [Duplicate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Duplicate) command is used to copy the selected diagram objects to the clipboard and paste the clipboard content to the diagram page. Duplicate command can be executed by the keyboard shortcut CTRL + D.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Duplicate" Name="Duplicate" Command="Syncfusion:DiagramCommands.Duplicate"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copy the diagram objects and Paste the clipboard's data (nodes or connectors) into the Diagram.
graphinfo.Commands.Duplicate.Execute(null);

{% endhighlight %}
{% endtabs %}

![Clipboard gif](Commands_Images/Commands_img11.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Clipboard%20commands)
