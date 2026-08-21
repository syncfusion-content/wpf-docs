---
layout: post
title: Tooltip in WPF SfDiagram | Syncfusion®
description: Display informative tooltips in Syncfusion® WPF SfDiagram to show position, size, and rotation details during element interactions.
platform: wpf
control: SfDiagram
documentation: ug
---

# Tooltip in WPF SfDiagram

In Graphical User Interface (GUI), the tooltip is a message that is displayed when the mouse hovers over an element. In [WPF Diagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram), The tooltip is used to provide information about the position, size, and rotation angle while dragging, resizing, and rotating the diagram elements.

N> By default, tooltips are enabled and displayed during dragging, resizing, and rotating interactions. The tooltip is shown in a static position unless the `SelectorHandleDisplayMode` property is set to `Compact`.

## Static Tooltip

By default, the diagram displays the tooltip at a static position during an interaction. While dragging and resizing, the size and position information will be displayed at the top of the node and during rotation, it will be displayed at the top of the rotation thumb.

![Static Tooltip](Interaction_images/DefaultTooltip.gif)

## Dynamic Tooltip

Diagram control displays the tooltip at a dynamic position when the [`SelectorHandleDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SelectorHandleDisplayMode.html) is set to `Compact`. When resizing a diagram element, the tooltip is positioned closer to the resizer thumbs, and when dragging, the tooltip is positioned automatically in the nearest available viewport area around that diagram element. The following image illustrates how the dynamic tooltip works.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDiagram x:Name="diagram" SelectorHandleDisplayMode="Compact" >

</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight c# %}

SfDiagram Diagram = new SfDiagram();

Diagram.SelectorHandleDisplayMode = SelectorHandleDisplayMode.Compact;

{% endhighlight %}
{% endtabs %}

![Dynamic Tooltip](Interaction_images/DynamicTooltip.gif)