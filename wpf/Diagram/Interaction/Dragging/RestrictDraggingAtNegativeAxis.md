---
layout: post
title: Support to restrict dragging at negative axis | Syncfusion.
description: How to restrict diagram control objects of Node, Connectors, Groups, and Symbols dragging at negative axis during runtime
platform: wpf
control: SfDiagram
documentation: ug
---
# Restrict objects dragging at negative axis in WPF Diagram (SfDiagram)

SfDiagram allows you to restrict diagram elements from dragging behind the negative axis. When `RestrictNegativeAxisDragDrop` is enabled, diagram elements such as Node, Connector, Connector end thumbs, Groups, Swim lane objects, and stencil symbols can be restricted from dragging when drag enters into negative zone.

![Find and position the node without overlapping](Drag_images/RestrictDragObjects.gif)

N> While dragging diagram elements and auto-scrolling is running, auto-scrolling will be stopped automatically when the element drag enters into negative region. If an object is placed in negative region and `RestrictNegativeAxisDragDrop` option is enabled, then element can be dragged from the negative to the positive region. Once, an object is dragged into positive region, then element cannot be dragged into negative region.

![Find and position the node without overlapping](Drag_images/RestrictDragToPositive.gif)

While symbol is dragging from the stencil control, it will be added into diagram page once entire symbol is placed in the positive region. 

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

## Inherit restrict dragging

Restrict diagram elements dragging at negative region behavior can be defined using both the specific object (Node/Connector) and the diagram. When the behaviors are contradictorily defined by both, the actual behavior is set by inherit options.

The following code example illustrates how to enable restrict object dragging at negative region behavior for a particular Node or specific connector.

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