---
layout: post
title: Syncfusion | Explore the zooming functionalities with zoom command.
description: Zoom command is used to do zoom-in, zoom-out and zoom to certain zoom operations on the Diagram view. It can be done by zoom command parameters.
platform: wpf
control: SfDiagram
documentation: ug
---

# Zoom command in WPF Diagram(SfDiagram)

Zoom commands are used to do zoom-in and zoom-out operations on the Diagram view. This command is also used to do scroll and pan operations with its parameter. 

To execute zoom commands, parameter of type IZoomParameter [IZoomPositionParameter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter_members.html) have to be passed.

## Zoom position parameter

`ZoomPositionParameter` is used to represent the position parameters to for executing zoom command. Please find its properties and their description below.

| Property name | Description |
| --- | --- |
| FocusPoint | It is used to set the point of foucus while zooming. Usually used to specify a particular point in the diagram view. |
| PanDelta | It is used to set the finite increament in the pan value. |
| ScrollDelta | It is used to set the finite increament in the scroll value. |
| ZoomCommand | It is used to set the opertaion to be performed. |
| ZoomFactor | It is used to set the percentage of scale value for each ZoomIn or ZoomOut functionalities. |
| ZoomTo | It is used to set the zoom to a particular value. |

For ZoomIn operation

{% tabs %}
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

For ZoomTo speciffic value

{% tabs %}
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

Reset command is used to reset horizontal Offset, vertical Offset, and zoom level of the Diagram. If we want to customize the Reset command we can use [IReset](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ResetParameter_members.html) as parameter.

### ResetParameter

Reset parameter is used to define the behavior of Reset Command. 

| Reset Enum Values | Description |
| --- | --- |
| None | It is used to disables all the behaviors of Reset Command. |
| Pan | It is used to specifies to reset the panned diagram. |
| Zoom | It is used to specifies to reset the zoomed diagram. |
| ZoomPan | It is used to Specifies to reset the zoomed and panned diagram. |


{% tabs %}
{% highlight C# %}

            IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

            // Reset the Zoom level of the Diagram
            graphinfo.Commands.Reset.Execute(new ResetParameter() { Reset = Reset.ZoomPan });

{% endhighlight %}
{% endtabs %}

Please find the [Zoom and Reset Command Sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Zoom%20Command) to depict these commands.