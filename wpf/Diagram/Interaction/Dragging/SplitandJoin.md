---
layout: post
title: Split and join in WPF Diagram control | Syncfusion
description: Learn here all about how split and joining of connectors works in Syncfusion WPF Diagram (SfDiagram) control.
platform: wpf
control: SfDiagram
documentation: ug
---

# Enable connector splitting in WPF Diagram (SfDiagram)

The connectors are used to create a link between two points, ports, or nodes to represent the relationship between them. You can able to split the connector between two nodes when dropping new node onto the existing connector and create the connection between new node and existing nodes by setting `EnableConnectorSplitting` as `true`. Default value of `EnableConnectorSplitting` is `false`.

{% tabs %}
{% highlight Xaml %}

<Syncfusion:SfDiagram x:Name="Diagram" EnableConnectorSplitting="True">

{% endhighlight %}

{% highlight C# %}

SfDiagram Diagram = new SfDiagram();

Diagram.EnableConnectorSplitting = true;

{% endhighlight %}
{% endtabs %}

![SplitandJoin](Drag_images/ConnectorSplitting.gif)