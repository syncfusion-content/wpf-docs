---
layout: post
title: Connector Splitting in WPF SfDiagram | Syncfusion®
description: Split existing connectors in Syncfusion® WPF SfDiagram by dropping nodes onto connector paths and automatically creating new connections.
platform: wpf
control: SfDiagram
documentation: ug
---

# Connector Splitting in WPF SfDiagram

The Connectors are used to create links between two points, ports, or nodes to represent the relationship between them. You can split the connector between two nodes when dropping a new node onto an existing connector and create a connection between the new node and existing nodes by setting `EnableConnectorSplitting` as `true`. The default value of `EnableConnectorSplitting` is `false`.

{% tabs %}
{% highlight Xaml %}

<Syncfusion:SfDiagram x:Name="Diagram" EnableConnectorSplitting="True"/>

{% endhighlight %}

{% highlight C# %}

SfDiagram Diagram = new SfDiagram();

Diagram.EnableConnectorSplitting = true;

{% endhighlight %}
{% endtabs %}

![SplitandJoin](Drag_images/ConnectorSplitting.gif)