---
layout: post
title: Group in WPF Diagram control | Syncfusion
description: Learn here all about Group support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Group in WPF Diagram (SfDiagram)

Group is used to cluster multiple Nodes and Connectors into a single element. It acts like a container for its children (Nodes, Groups, and Connectors). Every change made to the Group also affects the children. Child elements can be edited individually.

## Create Group

### Add Group

The following code illustrates how to create a Group Node.

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
NodeViewModel node = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 100,
	OffsetY = 100,
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = App.Current.Resources["shapestyle"] as Style
};
NodeViewModel node1 = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 200,
	OffsetY = 200,
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = App.Current.Resources["shapestyle"] as Style
};

ObservableCollection<GroupViewModel> groups = new ObservableCollection<GroupViewModel>();
GroupViewModel group = new GroupViewModel()
{
	Nodes = new ObservableCollection<NodeViewModel>()
	{
		node,
		node1
	},
};

groups.Add(group);
diagram.Groups = groups;

{% endhighlight %}

### Group from Stencil

Group Nodes can be predefined and added to stencil. You can drop those Groups into Diagram, when required. 

To explore how to add Groups from stencil, refer to [Stencil](/wpf/diagram/stencil "Stencil").

## Interaction

You can edit the Group and its children at runtime. For more information about how to interact with a Group, refer to [Interaction](/wpf/diagram/interaction "Interaction").

## See Also
 
* [How to restrict the child node dragging whereas allow group dragging?](https://www.syncfusion.com/kb/11462/how-to-restrict-the-child-node-dragging-whereas-allow-group-dragging-in-wpf)
