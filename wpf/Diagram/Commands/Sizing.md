---
layout: post
title: Syncfusion | Explore the sizing functionalities Sizing commands.
description: Sizing commands are used to resize all selected object based on width, height, and size of the reference object (FirstSelectedItem). 
platform: wpf
control: SfDiagram
documentation: ug
---

# Sizing commands in WPF Diagram(SfDiagram)

Sizing commands are used to resize all selected object based on width, height, and size of the reference object (FirstSelectedItem).

## SameSize command

The [SameSize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameSize) command is used to resize all the selected object based on the size of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Scales the selected items to the size of first selected object
graphinfo.Commands.SameSize.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameHeight command

The [SameHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameHeight) command is used to resize all the selected object based on the height of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Vertically scales the selected items to the height of first selected object
graphinfo.Commands.SameHeight.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameWidth command

The [SameWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_SameWidth) command is used to resize all the selected object based on the width of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Horizontally scales the selected items to the width of first selected object
graphinfo.Commands.SameWidth.Execute(null);

{% endhighlight %}
{% endtabs %}

![Sizing commands](Commands_Images/Commands_img5.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Sizing%20Commands)