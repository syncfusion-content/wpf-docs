---
layout: post
title: Restrict Dragging at Negative Axis in WPF SfDiagram | Syncfusion®
description: Restrict nodes, connectors, groups, and symbols from dragging into negative coordinates in Syncfusion® WPF SfDiagram.
platform: wpf
control: SfDiagram
documentation: ug
---
# Restrict Dragging at Negative Axis in WPF SfDiagram

[WPF SfDiagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram) allows you to restrict diagram elements from being dragged into the negative axis region. When `RestrictNegativeAxisDragDrop` is enabled, diagram elements such as Node, Connector, Connector end thumbs, Groups, Swim lane objects, and stencil symbols can be restricted from dragging when the drag operation enters the negative region.

N> The negative region refers to any location whose coordinate value is less than zero on either axis. When `RestrictNegativeAxisDragDrop` is enabled, diagram elements cannot be dragged to positions where the X-coordinate is less than 0 or the Y-coordinate is less than 0.

![Find and position the node without overlapping](Drag_images/RestrictDragObjects.gif)

N> While dragging diagram elements and auto-scrolling is running, auto-scrolling will be stopped automatically when the element drag enters into negative region. If an object is placed in negative region and `RestrictNegativeAxisDragDrop` option is enabled, the element can be dragged from the negative to the positive region. Once an object is dragged into positive region, then element cannot be dragged into negative region.

![Find and position the node without overlapping](Drag_images/RestrictDragToPositive.gif)

While a symbol is being dragged from the stencil control, it will be added into diagram page once entire symbol is placed in the positive region. 

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,RestrictNegativeAxisDragDrop">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();

//Enables the SnapToObject value as All
diagram.Constraints = GraphConstraints.Default | GraphConstraints.RestrictNegativeAxisDragDrop;
{% endhighlight %}
{% endtabs %}

## Inherit restrict dragging

Restrict diagram elements dragging at negative region behavior can be defined using both the specific object (Node/Connector) and the diagram. When the behaviors are contradictorily defined by both, the actual behavior is set by inherit options.

### Inheritance Behavior

By default, nodes and connectors inherit the value of `RestrictNegativeAxisDragDrop` from the parent diagram through the `InheritRestrictNegativeAxisDragDrop` constraint.

When `InheritRestrictNegativeAxisDragDrop` is enabled, the diagram-level setting determines whether the object can be dragged into the negative region.

To define a different behavior for a specific node or connector, remove the `InheritRestrictNegativeAxisDragDrop` constraint and explicitly enable or disable `RestrictNegativeAxisDragDrop` on that object. In such cases, the object-level setting takes precedence over the diagram-level setting.

The following code example illustrates how to enable restrict object dragging at negative region behavior for a particular Node or specific connector.

{% tabs %}
{% highlight c# %}
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