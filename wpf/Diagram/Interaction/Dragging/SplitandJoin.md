---
layout: post
title: Split and join in WPF Diagram control | Syncfusion
description: Learn here all about how split and joining of connectors works in Syncfusion WPF Diagram (SfDiagram) control.
platform: wpf
control: SfDiagram
documentation: ug
---

# Split and Join in WPF Diagram (SfDiagram)

Diagram provides support to split and join the connectors using [EnableConnectorSplitting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.EnableConnectorSplitting.html) . Default value of `EnableConnectorSplitting` is false. 

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