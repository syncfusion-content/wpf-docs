---
layout: post
title: Enable/Disable the optional features.
description: How to enable/disable the optional features?
platform: wpf
control: SfDiagram
documentation: ug
---

# Constraints

`Constraints` are used to enable/disable certain behaviors of the diagram, Node and Connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (&, |, ~, <<, etc.). 
To know more about bitwise operators, refer to [Bitwise Operations](#bitwise-operations).

## Graph Constraints

Graph constraints allow to enable or disable the following behaviors.

* Page Editing
* Line Bridging
* Zoom and Pan
* Undo Redo

**Example** 

The following example illustrates how to disable page editing.

{% highlight C# %}

diagram.Constraints = GraphConstraints.Default & ~GraphConstraints.PageEditing;

{% endhighlight %}

## Node Constraints

NodeConstraints allow to enable or disable the following behaviors of Node.

* Selection
* Deletion
* Drag
* Resize
* Rotate
* Connect
* Annotation Dragging

**Example**

The following code illustrates how to disable rotation.

{% highlight C# %}

ObservableCollection<Node> nodes = new ObservableCollection<Node>();

Node node = new Node()
{
  Constraints = NodeConstraints.Default & ~NodeConstraints.Rotatable,
  UnitWidth = 50,
  UnitHeight = 50,
  OffsetX = 100,
  OffsetY = 100,
  Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
  ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

## Connector Constraints

ConnectorConstraints allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection
* Deletion
* Drag
* Segment editing
* Bridging
* Annotation dragging

**Example**

The following code illustrates how to disable selection.

{% highlight C# %}

ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();

Connector connector1 = new Connector()
{
	Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.Selectable
};

connectors.Add(connector1);
diagram.Connectors = connectors;

{% endhighlight %}

## Port Constraints

You can enable or disable certain behaviors of port. They are as follows.

* Connect 

Example

The following code illustrates how to disable creating connections with a port.

{% highlight C# %}

Node node = new Node()
{
	Ports = new ObservableCollection<INodePort>()
	{
		new NodePort()
		{
			Constraints = PortConstraints.None
		}
	},
	UnitWidth = 50,
	UnitHeight = 50,
	OffsetX = 100,
	OffsetY = 100,
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

## Annotation Constraints
AnnotationConstraints allow to enable or disable the following behaviors of Annotation.

* Selection
* Drag
* Resize
* Rotate

**Example**
the following code illustrates how to enable annotation dragging.

{% highlight C# %}

            //Create NodeViewModel (Shape and ShapeStyle Applied from "Data-Binding"
            NodeViewModel node = new NodeViewModel()
            {
                OffsetX = 200,
                OffsetY = 200,
                UnitWidth = 100,
                UnitHeight = 50,
                //Initialize and Add annotation to NodeViewModel
                Annotations = new ObservableCollection<IAnnotation>()
                    {
                        //Create a AnnotationEditorViewModel
                        new AnnotationEditorViewModel()
                        {
                            Content = "Annotation",
                            //Assign Constraint to Select and Drag.
                            Constraints =AnnotationConstraints.Selectable |AnnotationConstraints.Draggable,                            
                        }          
                    }
            };
            //Add NodeViewModel to Nodes Collection
            (Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %} 

## Selector Constraints

Selector visually represents the selected elements with certain editable thumbs. The visually of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer
* Rotator
* Quick Commands

**Example**

The following code illustrates how to hide rotator.

{% highlight C# %}

(diagram.SelectedItems as SelectorViewModel).SelectorConstraints = (diagram.SelectedItems as  SelectorViewModel).SelectorConstraints & ~SelectorConstraints.Rotator;

{% endhighlight %}

## Snap Constraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only Horizontal or Vertical Gridlines
* Show both Horizontal or Vertical Gridlines
* Show to either Horizontal or Vertical Gridlines
* Show to both Horizontal or vertical gridlines

**Example**

The following code illustrates how to show only Horizontal Gridlines

{% highlight C# %}

diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToHorizontalLines;

{% endhighlight %}

### Inherit behaviors

Some of the behaviors can be defined through both the specific object (Node/Connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram.

{% highlight C# %}

diagram.Constraints = GraphConstraints.Default | GraphConstraints.Bridging;

ObservableCollection<Connector> connectors = new ObservableCollection<Connector>();

Connector connector1 = new Connector()
{
	SourcePoint=new Point(100,100),
	TargetPoint=new Point(200,200),
	Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging
};

connectors.Add(connector1);
diagram.Connectors = connectors;

{% endhighlight %}

## Bitwise Operations

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In the section, Bitwise Operations are illustrated by using Node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

### Add Operation

You can add or enable multiple values at a time	 by using Bitwise ‘|’ (OR) operator.

{% highlight C# %}

node.Constraints = NodeConstraints.Selectable | NodeConstraints.Rotatable;

{% endhighlight %}

In the above example, you can do both the selection and rotation.

### Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

{% highlight C# %}

node.Constraints = node.Constraints & ~(NodeConstraints.Rotatable);

{% endhighlight %}

In the above example, Rotation is disabled but other constraints are enabled.

### Check Operation

You can check any value by using Bitwise ‘&’ (AND) operator.

{% highlight C# %}

if ((node.Constraints & (NodeConstraints.Rotatable)) == (NodeConstraints.Rotatable))

{% endhighlight %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.

