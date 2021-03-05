---
layout: post
title: Automatic port creation | Syncfusion
description: How to create port at runtime by clicking and drag over the node or connector without initializing the port collection?
platform: wpf
control: SfDiagram
documentation: ug
---

# Automatic port creation

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

![AutomaticPortCreation](Port_images/AutomaticPortCreation.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Port/AutomaticPortCreation)

## Port Dragging

 Diagram provides the support to drag the port interactively within the limit.

* For `NodePort` and `DockPort`, port can be dragged within the node bounds.
* For `ConnectorPort`, port can be dragged anywhere on the connector.
 
 ![Port dragging](Port_images/Interaction.gif)

## See Also

* [How to decide whether to drag or draw a port at runtime?](https://www.syncfusion.com/kb/9622/how-to-decide-whether-to-drag-or-draw-a-connection-on-port-at-runtime)

* [How to create port at runtime though SetTool?](https://www.syncfusion.com/kb/11446/how-to-create-port-at-runtime-through-set-tool-in-wpf-diagram-sfdiagram)