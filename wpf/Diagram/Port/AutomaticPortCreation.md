---
layout: post
title: AutomaticPortCreation in WPF Diagram control | Syncfusion
description: Learn here all about AutomaticPortCreation support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# AutomaticPortCreation in WPF Diagram (SfDiagram)

Diagram provides an option to create a port dynamically by clicking and dragging the mouse over any node or connector. This behavior is disabled by default and can be enabled by using `GraphConstraints.AutomaticPortCreation`. To draw connector, you need to set the `Tool` and `DrawingTool` properties of diagram.

{% tabs %}
{% highlight xaml %}

<!--Enables AutomaticPortCreation of SfDiagram to create port at runtime while making connections.-->
<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible" 
                      Tool="ContinuesDraw" DrawingTool="Connector" 
                      Constraints="Default,AutomaticPortCreation"/>

{% endhighlight %}

{% highlight C# %}

//We need to enable tool and drawingtool to draw connector by clicking and dragging the mouse over the node.
diagram.Tool = Tool.ContinuesDraw;
diagram.DrawingTool = DrawingTool.Connector;
//Enables AutomaticPortCreation of SfDiagram to create port at runtime while making connections.
diagram.Constraints |= GraphConstraints.AutomaticPortCreation;

{% endhighlight %}
{% endtabs %}

![WPF Diagram Automatic Port Creation](Port_images/wpf-diagram-automatic-port-creation.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Port/AutomaticPortCreation)

## Port Dragging

 Diagram provides the support to drag the port interactively within the limit.

* For [`NodePort`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodePort.html) and [`DockPort`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DockPort.html), port can be dragged within the node bounds.
* For [`ConnectorPort`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorPort.html), port can be dragged anywhere on the connector.
 
 ![WPF Diagram Port Dragging](Port_images/wpf-port-dragging.gif)

## See Also

[How to decide whether to drag or draw a port at runtime?](https://www.syncfusion.com/kb/9622/how-to-decide-whether-to-drag-or-draw-a-connection-on-port-at-runtime)

[How to create port at runtime though SetTool?](https://www.syncfusion.com/kb/11446/how-to-create-port-at-runtime-through-set-tool-in-wpf-diagram-sfdiagram)