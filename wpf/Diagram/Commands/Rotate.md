---
layout: post
title: Syncfusion | Explore the Rotate command.
description: Rotate Command is used to rotate the selected element in specified angle in diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# Rotate command in WPF Diagram(SfDiagram)

Rotate Command invokes to rotate the elements in diagram.This command will receive `RotateParameter` as command which contains `RotationDirection` and `Angle` informations set the direction and angle to rotate the element in diagram.

{% tabs %}

{% highlight Xaml%}

<Syncfusion:RotateParameter RotationDirection="Clockwise" Angle="45"  x:Key="RotateCommandParameter"/>

<Button Height="50" Content="Rotate" Name="RotateCommand" Command="Syncfusion:DiagramCommands.Rotate" CommandParameter="{StaticResource RotateCommandParameter }"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
graphinfo.Commands.Rotate.Execute(new RotateParameter() 
{ 
    RotationDirection=RotationDirection.Clockwise,Angle=45
});

{% endhighlight %}
{% endtabs %}

![Gif for Rotate command](Commands_Images/Commands_Rotate.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Rotate%20Command)