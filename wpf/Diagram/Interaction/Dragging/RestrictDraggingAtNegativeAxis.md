---
layout: post
title: Support to restrict dragging at negative axis | Syncfusion.
description: How to restrict Node, Connectors, Groups, Symbols dragging at negative axis during runtime?
platform: wpf
control: SfDiagram
documentation: ug
---
## Restrict objects dragging at negative axis in WPF Diagram (SfDiagram)

SfDiagram provides support to restrict objects dragging behind the negative axis. It can be achieved by enabling 'RestrictNegativeAxisDragDrop' enum of [GraphConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GraphConstraints.html) property. Diagram elements of Node, Connector, Connector end thumbs, Groups, Swim lane objects, stencil symbols can be restricted to dragging when drag enter into negative region when 'RestrictNegativeAxisDragDrop' is enabled.

![Find and position the node without overlapping](Drag_images/RestrictDragObjects.gif)

While dragging diagram elements and auto-scrolling is running, auto-scrolling will be stopped atomatically when element drag enter into negative region.

If object is placed at negative region and 'RestrictNegativeAxisDragDrop' enabled, then element can be drag from negative to positve region. Once object dragged into positive region, then element can't drag into negative region. 

![Find and position the node without overlapping](Drag_images/RestrictDragToPositive.gif)

While symbol is dragging from stencil control, it will be added into diagram page once entire symbl is placed at positive region. 

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,RestrictNegativeAxisDragDrop">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enables the SnapToObject value as All
diagram.Constraints = GraphConstraints.Default | GraphConstraints.RestrictNegativeAxisDragDrop;
{% endhighlight %}
{% endtabs %}

## Inherit Restrict dragging

Restrict object dragging at negative region behavior can be defined through both the specific object (Node/Connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to enable restrict object dragging at negative region behavior for Particular or particular connector.

{% tabs %}
{% highlight C# %}
//Here node is instance of a NodeViewModel
//Remove inherit constraint.
node.Constraints &= ~NodeConstraints.InheritRestrictNegativeAxisDragDrop;
//Enable RestrictNegativeAxisDragDrop behaviour for one node alone
node.Constraints |= NodeConstraints.RestrictNegativeAxisDragDrop;

//Here connector is instance of a ConnectorViewModel
//Remove inherit constraint.
connector.Constraints &= ~NodeConstraints.InheritRestrictNegativeAxisDragDrop;
//Enable RestrictNegativeAxisDragDrop behaviour for one connector alone.
connector.Constraints |= NodeConstraints.RestrictNegativeAxisDragDrop;
{% endhighlight %}
{% endtabs %}