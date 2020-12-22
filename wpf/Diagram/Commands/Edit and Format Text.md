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

`EditAnnotation` command enables annotation editing mode of the first selected diagram element.

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

ToggleBold Command toggle the bold style for the annotation of the selected elements in the diagram.

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

ToggleItalic Command toggle the italic style for the annotation of the selected elements in the diagram.

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

ToggleUnderline Command toggle the underline for the annotation of the selected elements in the diagram.

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

ToggleStrikeThrough Command toggle the strikethrough style for the annotation of the selected elements in the diagram.


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

`Cancel` command stops the annotation editing and accept the curent value, clear the Keyboard focus, clear the selection of the diagram elements,reset the diagram tool to select tool.

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


