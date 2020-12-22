---
layout: post
title: Syncfusion | Explore the SelectTool commands.
description: EditAnnotation,ToggleBold,ToggleItalic,ToggleStrikeThrough and ToggleUnderline Commands are used to edit and style annotations in diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# Edit and Format Annotation in WPF Diagram(SfDiagram)

## EditAnnotation

The [EditAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_EditAnnotation) command enables annotation editing mode of the first selected diagram element.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="EditAnnotation" Name="EditAnnotation" Command="Syncfusion:DiagramCommands.EditAnnotation"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.EditAnnotation.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleBold Command

The [ToggleBold](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleBold) command is used to toggle the bold style for the annotation of the selected element in the diagram.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="ToggleBold" Name="ToggleBold" Command="Syncfusion:DiagramCommands.ToggleBold"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleBold.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleItalic Command

The [ToggleItalic](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleItalic) command is used to toggle the italic style for the annotation of the selected element in the diagram.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="ToggleItalic" Name="ToggleItalic" Command="Syncfusion:DiagramCommands.ToggleItalic"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleItalic.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleUnderline Command

The [ToggleUnderline](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleUnderline) command is used to toggle the underline for the annotation of the selected elements in the diagram.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="ToggleUnderline" Name="ToggleUnderline" Command="Syncfusion:DiagramCommands.ToggleUnderline"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleUnderline.Execute(null);

{% endhighlight %}
{% endtabs %}

## ToggleStrikeThrough Command

The [ToggleStrikeThrough](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ToggleStrikeThrough) command is used to toggle the strikethrough style for the annotation of the selected elements in the diagram.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="ToggleStrikeThrough" Name="ToggleStrikeThrough" Command="Syncfusion:DiagramCommands.ToggleStrikeThrough"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.ToggleStrikeThrough.Execute(null);

{% endhighlight %}
{% endtabs %}

## Cancel command 

The [Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Cancel) command is used to perform either any of the below action.
* Stops the annotation editing and accept the current value.
* Clear the Keyboard focus.
* Clear the selection of the diagram elements.
* Reset the diagram tool to select tool.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Cancel" Name="Cancel" Command="Syncfusion:DiagramCommands.Cancel"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.Cancel.Execute(null);

{% endhighlight %}
{% endtabs %}


![Gif for EditAnnotation command](Commands_Images/Commands_EditStyleText.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/SelectToolCommand)


