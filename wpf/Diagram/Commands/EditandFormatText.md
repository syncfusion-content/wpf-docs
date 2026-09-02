---
layout: post
title: Edit and Format Text Commands in WPF SfDiagram | Syncfusion®
description: Edit annotations and format text in Syncfusion® WPF SfDiagram using commands for bold, italic, underline, strikethrough, and editing.
platform: wpf
control: SfDiagram
documentation: ug
---

# Edit and Format Text Commands in WPF SfDiagram

N> The `EditAnnotation`, `ToggleBold`, `ToggleItalic`, `ToggleUnderline`, and `ToggleStrikeThrough` commands are applicable only when a diagram element with an annotation is selected. If no annotated element is selected, the command will not perform any operation.

## EditAnnotation

The [EditAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_EditAnnotation) command is used to enable editing mode for the annotation of the selected element. In the case of multiple selection, editing will be enabled for the first selected element.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="EditAnnotation" Name="EditAnnotation" Command="Syncfusion:DiagramCommands.EditAnnotation"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.EditAnnotation.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleBold Command

The [ToggleBold](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleBold) command is used to toggle the bold style for the annotation of the selected element in the diagram.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="ToggleBold" Name="ToggleBold" Command="Syncfusion:DiagramCommands.ToggleBold"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleBold.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleItalic Command

The [ToggleItalic](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleItalic) command is used to toggle the italic style for the annotation of the selected element in the diagram.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="ToggleItalic" Name="ToggleItalic" Command="Syncfusion:DiagramCommands.ToggleItalic"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleItalic.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleUnderline Command

The [ToggleUnderline](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleUnderline) command is used to toggle the underline for the annotation of the selected elements in the diagram.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="ToggleUnderline" Name="ToggleUnderline" Command="Syncfusion:DiagramCommands.ToggleUnderline"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleUnderline.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleStrikeThrough Command

The [ToggleStrikeThrough](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleStrikeThrough) command is used to toggle the strikethrough style for the annotation of the selected elements in the diagram.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="ToggleStrikeThrough" Name="ToggleStrikeThrough" Command="Syncfusion:DiagramCommands.ToggleStrikeThrough"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleStrikeThrough.Execute(null);

{% endhighlight %}
{% endtabs %}

## Cancel command 

The [Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Cancel) command is used to perform either one of the below action with higher priority.
* Stops the annotation editing and accepts the current value.
* Clears the selection of or keyboard focus on the diagram elements.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="Cancel" Name="Cancel" Command="Syncfusion:DiagramCommands.Cancel"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.Cancel.Execute(null);

{% endhighlight %}
{% endtabs %}


![Gif for EditAnnotation command](Commands_Images/Commands_EditStyleText.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Commands%20Sample)