---
layout: post
title: Syncfusion | Explore the Clipboard commands.
description:  Clipboard commands allow you to cut or copy the selected Diagram objects to the Clipboard and paste the valid Clipboard content into the Diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# Clipboard commands in WPF Diagram(SfDiagram)

Clipboard commands are used to cut or copy the selected diagram objects to the clipboard and paste the valid clipboard content into the diagram page.

## Cut command

The [Cut](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IDiagramCommands~Cut.html) command is used to cut the selected diagram objects to the clipboard. Cut command can be executed by the keyboard shortcut CTRL + X.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Cuts the selected elements from the diagram to the diagram’s clipboard
graphinfo.Commands.Cut.Execute(null);

{% endhighlight %}
{% endtabs %}

## Copy command

The [Copy](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IDiagramCommands~Copy.html) command is used to copy the selected diagram objects to the clipboard. Copy command can be executed by the keyboard shortcut CTRL + C.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copies the selected elements from the diagram to the diagram’s clipboard.
graphinfo.Commands.Copy.Execute(null);

{% endhighlight %}
{% endtabs %}

## Paste command

The [Paste](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IDiagramCommands~Paste.html) command is used to paste the clipboard content to the diagram page. Paste command can be executed by the keyboard shortcut CTRL + V.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Pastes the diagram’s clipboard data (nodes or connectors) into the Diagram.
graphinfo.Commands.Paste.Execute(null);

{% endhighlight %}
{% endtabs %}

## Duplicate command

The [Duplicate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IDiagramCommands~Duplicate.html) command is used to copy the selected diagram objects to the clipboard and paste the clipboard content to the diagram page. Duplicate command can be executed by the keyboard shortcut CTRL + D.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Copy the diagram objects and Paste the clipboard's data (nodes or connectors) into the Diagram.
graphinfo.Commands.Duplicate.Execute(null);

{% endhighlight %}
{% endtabs %}

![Clipboard gif](Commands_Images/Commands_img11.gif)

Please find the [Clipboard commands sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Clipboard%20commands) to depict these commands.