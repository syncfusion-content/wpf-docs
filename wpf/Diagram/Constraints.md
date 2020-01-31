---
layout: post
title: Enable/Disable the optional features | Syncfusion.
description: How to enable or disable the optional features, behaviours of diagram and how to enable single or multiple feature at a time?
platform: wpf
control: SfDiagram
documentation: ug
---

# Constraints

`Constraints` are used to enable/disable certain behaviors of the diagram, Node and Connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (&, |, ~, <<, etc.). 
To know more about bitwise operators, refer to [Bitwise Operations](#bitwise-operations).

## Graph Constraints

[GraphConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.GraphConstraints.html) allow to enable or disable the following behaviors.

* Page Editing
* Line Bridging
* Zoom and Pan
* Undo Redo
* Routing

The following code example illustrates how to disable page editing.

{% tabs %}
{% highlight C# %}

diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.PageEditing;

{% endhighlight %}
{% endtabs %}

## Node Constraints

[NodeConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.NodeConstraints.html) allow to enable or disable the following behaviors of Node.

* Selection
* Deletion
* Drag
* Resize
* Rotate
* Connect

The following code example illustrates how to disable rotation.

{% tabs %}
{% highlight C# %}

//Create NodeViewModel collection
diagram.nodes = new ObservableCollection<NodeViewModel>();

//Create NodeViewModel (Shape and ShapeStyle Applied from "Data-Binding")
NodeViewModel node = new NodeViewModel()
{
  Constraints = NodeConstraints.Default & ~NodeConstraints.Rotatable,
  UnitWidth = 50,
  UnitHeight = 50,
  OffsetX = 100,
  OffsetY = 100,  
};
//Add NodeViewModel to Nodes Collection
(diagram.Nodes as ObservableCollection<NodeViewModel>).Add(node);

{% endhighlight %}
{% endtabs %}

## Connector Constraints

[ConnectorConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ConnectorConstraints.html) allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection
* Drag
* Segment editing
* Bridging
* Delete

The following code example illustrates how to disable selection.

{% tabs %}
{% highlight C# %}

diagram.connectors = new ObservableCollection<ConnectorViewModel>();

//Create ConnectorViewModel (Style Applied from "Data-Binding")
ConnectorViewModel connector1 = new ConnectorViewModel()
{
	Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.Selectable
};

(diagram.Connectors as ObservableCollection<ConnectorViewModel>).Add(connector1);

{% endhighlight %}
{% endtabs %} 

## Port Constraints

[PortConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PortConstraints.html) allow to enable or disable certain behaviors of port. They are as follows.

* Connect 
* Drag

The following code example illustrates how to disable creating connections with a port.

{% tabs %}
{% highlight C# %}

//Create NodePortViewModel (Shape and ShapeStyle Applied from "Data-Binding")
NodePortViewModel port=	new NodePortViewModel()
{
  UnitWidth= 10,
	UnitHeight= 10,
	Constraints = PortConstraints.Default & 
    ~PortConstraints.Connectable
};

{% endhighlight %}
{% endtabs %}

## Annotation Constraints

[AnnotationConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.AnnotationConstraints.html) allow to enable or disable the following behaviors of Annotation.

* Selection
* Drag
* Resize
* Rotate

The following code example illustrates how to enable annotation dragging.

{% tabs %}
{% highlight C# %}

//Create a AnnotationEditorViewModel (Style Applied from "Data-Binding")
AnnotationEditorViewModel anno = new AnnotationEditorViewModel()
{
    Content="Annotation",
    //Assign Constraint to Select and Drag
    Constraints=AnnotationConstraints.Selectable|AnnotationConstraints.Draggable,
};

{% endhighlight %}
{% endtabs %} 

## Selector Constraints

Selector visually represents the selected elements with certain editable thumbs. The visual representation of the thumbs can be controlled with [SelectorConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SelectorConstraints.html). The part of selector is categorized as follows.

* Resizer
* Rotator
* Quick Commands

The following code example illustrates how to hide rotator.

{% tabs %}
{% highlight C# %}

(diagram.SelectedItems as SelectorViewModel).SelectorConstraints = (diagram.SelectedItems as  SelectorViewModel).SelectorConstraints & ~SelectorConstraints.Rotator;

{% endhighlight %}
{% endtabs %}

## Snap Constraints

[SnapConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SnapConstraints.html) control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only Horizontal or Vertical Gridlines
* Show both Horizontal or Vertical Gridlines
* Show to either Horizontal or Vertical Gridlines
* Show to both Horizontal or vertical gridlines

The following code example illustrates how to show only Horizontal Gridlines

{% tabs %}
{% highlight C# %}

diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToHorizontalLines;

{% endhighlight %}
{% endtabs %}

### Inherit behaviors

Some of the behaviors can be defined through both the specific object (Node/Connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram.

{% tabs %}
{% highlight C# %}

diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;

ObservableCollection<ConnectorViewModel> connectors = new ObservableCollection<ConnectorViewModel>();

ConnectorViewModel connector1 = new ConnectorViewModel()
{
	SourcePoint=new Point(100,100),
	TargetPoint=new Point(200,200),
	Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging
};

connectors.Add(connector1);
diagram.Connectors = connectors;

{% endhighlight %}
{% endtabs %}

## Bitwise Operations

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In the section, Bitwise Operations are illustrated by using Node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

### Add Operation

You can add or enable multiple values at a time	by using Bitwise `|` (OR) operator.

{% tabs %}
{% highlight C# %}

node.Constraints = NodeConstraints.Selectable | NodeConstraints.Rotatable;

{% endhighlight %}
{% endtabs %}

In the above example, you can do both the selection and rotation.

### Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

{% tabs %}
{% highlight C# %}

node.Constraints = node.Constraints & ~(NodeConstraints.Rotatable);

{% endhighlight %}
{% endtabs %}

In the above example, Rotation is disabled but other constraints are enabled.

### Check Operation

You can check any value by using Bitwise ‘&’ (AND) operator.

{% tabs %}
{% highlight C# %}

if ((node.Constraints & (NodeConstraints.Rotatable)) == (NodeConstraints.Rotatable))

{% endhighlight %}
{% endtabs %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When `NodeConstraints` have rotate constraints, the expression returns a rotate constraint.