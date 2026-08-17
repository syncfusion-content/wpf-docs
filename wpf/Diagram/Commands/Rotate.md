---
layout: post
title: Rotate Command in WPF SfDiagram | Syncfusion®
description: Rotate diagram elements in Syncfusion® WPF SfDiagram using rotate commands with configurable angles and rotation directions.
platform: wpf
control: SfDiagram
documentation: ug
---

# Rotate Command in WPF SfDiagram

The [Rotate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Rotate) command is used to rotate elements in the diagram. 

The [RotateParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.RotateParameter.html) is used to represent [RotationDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.RotationDirection.html) and [Angle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.RotateParameter.html#Syncfusion_UI_Xaml_Diagram_RotateParameter_Angle) to rotate the element in diagram.


## RotateParameter

### RotationDirection

The `RotationDirection` property is used to specify the direction of rotation. The default value of the `RotationDirection` property is `Clockwise`.

### Angle

The `Angle` property is used to specify the rotation angle in degrees. The default value of the `Angle` property is `90`.

{% tabs %}

{% highlight Xaml%}

<Syncfusion:RotateParameter RotationDirection="Clockwise" Angle="45"  x:Key="RotateCommandParameter"/>

<Button Height="50" Content="Rotate" Name="RotateCommand" Command="Syncfusion:DiagramCommands.Rotate" CommandParameter="{StaticResource RotateCommandParameter }"></Button>

{% endhighlight %}

{% highlight C# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

graphinfo.Commands.Rotate.Execute(new RotateParameter() 
{ 
    RotationDirection=RotationDirection.Clockwise,
    Angle=45
});

{% endhighlight %}
{% endtabs %}

![Gif for Rotate command](Commands_Images/Commands_Rotate.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Rotate%20Command)