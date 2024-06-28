---
layout: post
title: Zoom Command in WPF Diagram control | Syncfusion
description: Learn here all about Zoom Command support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Zoom Command in WPF Diagram (SfDiagram)

The [Zoom](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Zoom) commands are used to do zoom-in and zoom-out operations on the Diagram view. This command is also used to do scroll and pan operations with its parameter. 

To execute zoom commands, parameter of type [ZoomPositionParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html) have to be passed.

## Zoom position parameter

The `ZoomPositionParameter` is used to represent the position parameters for executing the zoom command. Please find its properties and their descriptions as follows.

| Property name | Description |
| --- | --- |
| [FocusPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_FocusPoint) | It is used to set the point of focus when zooming, Usually used to specify a particular point within the diagram view. |
| [PanDelta](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_PanDelta) | It is used to set the finite increment in the pan value. |
| [ScrollDelta](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_ScrollDelta) | It is used to set the finite increment in the scroll value. |
| [ZoomCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_ZoomCommand) | It is used to set the operation to be performed. |
| [ZoomFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_ZoomFactor) | It is used to set the percentage scale value for each ZoomIn or ZoomOut operation. |
| [ZoomTo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_ZoomTo) | It is used to set the zoom level to a specific value. |

For ZoomIn operation

{% tabs %}

{% highlight Xaml%}

<Syncfusion:ZoomPositionParameter ZoomCommand="ZoomIn" ZoomFactor="0.2" x:Key="ZoomInParameter"/>

<Button Height="50" Content="ZoomIn" Name="ZoomIn" Command="Syncfusion:DiagramCommands.Zoom" CommandParameter="{StaticResource ZoomInParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// For ZoomIn function
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.ZoomIn,
    ZoomFactor = 0.2,
});

{% endhighlight %}
{% endtabs %}

For ZoomOut operation

{% tabs %}

{% highlight Xaml%}

<Syncfusion:ZoomPositionParameter ZoomCommand="ZoomOut" ZoomFactor="0.2" x:Key="ZoomOutParameter"/>

<Button Height="50" Content="ZoomOut" Name="ZoomOut" Command="Syncfusion:DiagramCommands.Zoom" CommandParameter="{StaticResource ZoomOutParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// For ZoomOut function
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.ZoomOut,
    ZoomFactor = 0.2,
});

{% endhighlight %}
{% endtabs %}

![ZoomIn and ZoomOut gif](Commands_Images/Commands_img13.gif)

For ZoomTo specific value

{% tabs %}

{% highlight Xaml%}

<Syncfusion:ZoomPositionParameter ZoomCommand="Zoom" ZoomTo="2" x:Key="ZoomToParameter"/>

<Button Height="50" Content="ZoomTo" Name="ZoomTo" Command="Syncfusion:DiagramCommands.Zoom" CommandParameter="{StaticResource ZoomToParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// For ZoomTo specific value
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.Zoom,
    ZoomTo = 2,
});

{% endhighlight %}
{% endtabs %}

![ZoomTo gif](Commands_Images/Commands_img14.gif)

For Panning

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// For horizontal scroll
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.HorizondalScroll,
    ScrollDelta = 50,
});

{% endhighlight %}
{% endtabs %}


For HorizontalScroll

{% tabs %}

{% highlight Xaml%}

<Syncfusion:ZoomPositionParameter ZoomCommand="HorizondalScroll" ScrollDelta="5" x:Key="HorizontalScrollParameter"/>

<Button Height="50" Content="HorizontalScroll" Name="HorizontalScroll" Command="Syncfusion:DiagramCommands.Zoom" CommandParameter="{StaticResource HorizontalScrollParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// For horizontal scroll
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.HorizondalScroll,
    ScrollDelta = 50,
});

{% endhighlight %}
{% endtabs %}

For VerticalScroll

{% tabs %}

{% highlight Xaml%}

<Syncfusion:ZoomPositionParameter ZoomCommand="VerticalScroll" ScrollDelta="50"  x:Key="ZoomPositionCommandParameter"/>

<Button Height="50" Content="VerticalScroll" Name="VerticalScroll" Command="Syncfusion:DiagramCommands.Zoom" CommandParameter="{StaticResource ZoomPositionCommandParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = Diagram.Info as IGraphInfo;

// For vertical scroll
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter()
{
    ZoomCommand = ZoomCommand.VerticalScroll,
    ScrollDelta = 50,
});

{% endhighlight %}
{% endtabs %}

![Scroll and pan gif](Commands_Images/Commands_img15.gif)

## Reset

The [Reset](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Reset) command is used to reset [HorizontalOffset](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.IScrollInfo.html#Syncfusion_UI_Xaml_Diagram_Controls_IScrollInfo_HorizontalOffset), [VerticalOffset](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.IScrollInfo.html#Syncfusion_UI_Xaml_Diagram_Controls_IScrollInfo_VerticalOffset), and [CurrentZoom](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.IScrollInfo.html#Syncfusion_UI_Xaml_Diagram_Controls_IScrollInfo_CurrentZoom) of the Diagram. If you want to customize the `Reset` command, you can use the parameter of type [ResetParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ResetParameter.html).

### ResetParameter

The `Reset` parameter is used to define the behavior of the Reset Command. 

| Reset Enum Values | Description |
| --- | --- |
| None | It is used to disable all behaviors of the Reset Command. |
| Pan | It specifies resetting the panned diagram. |
| Zoom | It specifies resetting the zoomed diagram. |
| ZoomPan | It specifies resetting both the zoomed and panned diagram. |


{% tabs %}

{% highlight Xaml%}

<Syncfusion:ResetParameter Reset="ZoomPan" x:Key="ResetParameterCommandParameter"/>

<Button Height="50" Content="Reset" Name="Reset" Command="Syncfusion:DiagramCommands.Reset" CommandParameter="{StaticResource ResetParameterCommandParameter}"></Button>

{% endhighlight %}

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Reset the Zoom level of the Diagram
graphinfo.Commands.Reset.Execute(new ResetParameter() { Reset = Reset.ZoomPan });

{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Zoom%20Command)
