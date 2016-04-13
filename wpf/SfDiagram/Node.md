---
layout: post
title: Visually represent the geometrical informations, process flow, or entities.
description: How to visually represent the geometrical information and process flows as nodes?
platform: wpf
control: SfDiagram
documentation: ug
---

#Node

Nodes are graphical objects used to visually represent the geometrical information, process flow, internal business procedure, entity, or any other kind of data.

![](Node_images/Node_img1.jpeg)

##Create Node

A Node can be created and added to the Diagram, either programmatically or interactively. Nodes are stacked on the Diagram area from bottom to top in the order they are added.

###Add Node through Nodes collection 

To create a Node, You have to define the Node object and add that to Nodes collection of the Diagram. The following code example illustrate how to add the Node to the Diagram.

{% highlight xaml %}

<diagram:SfDiagram x:Name="diagram">
    <diagram:SfDiagram.Nodes>
        <diagram:DiagramCollection>
            <diagram:NodeViewModel UnitWidth="100" UnitHeight="100" OffsetX="200" OffsetY="200">
                <diagram:NodeViewModel.Shape>
                    <RectangleGeometry Rect="0,0,10,10"/>
                </diagram:NodeViewModel.Shape>
                <diagram:NodeViewModel.ShapeStyle>
                    <Style TargetType="Path">
                        <Setter Property="Fill" Value="DarkCyan"></Setter>
                        <Setter Property="Stroke" Value="Black"/>
                        <Setter Property="StrokeThickness" Value="2"></Setter>
                        <Setter Property="Stretch" Value="Fill"></Setter>
                    </Style>
                </diagram:NodeViewModel.ShapeStyle>
            </diagram:NodeViewModel>
        </diagram:DiagramCollection>
    </diagram:SfDiagram.Nodes>
</diagram:SfDiagram>

{% endhighlight %}

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();

NodeViewModel node = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 200,
	OffsetY = 200,
	
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};
            
nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

![](Node_images/Node_img2.jpeg)

###Add Node from stencil

Nodes can be predefined and added to palette and can be dropped into the Diagram when needed. For more information about adding Nodes from Stencil, refer to [Stencil](/wpf/sfdiagram/Stencil "Stencil").

###Create Node through data source

Nodes can be generated automatically with the information provided through data source.For more information about data source, 

refer to [Data Source](/wpf/sfdiagram/DataSource "DataSource").

###Draw Nodes

Nodes can be interactively drawn by clicking and dragging the Diagram surface by using **Drawing Tool**. For more information about drawing Nodes, refer to [Draw Nodes](/wpf/sfdiagram/Tools#drawing-tools:shapes "Draw Nodes").

##Position

Position of a Node is controlled by using its OffsetX and OffsetY properties. By default, these Offset properties represent the distance between origin of the Diagram’s page and Node’s center point. You may except this Offset values to represent the distance between page origin and Node’s top left corner instead of center. Pivot property helps solve this problem. Default value of Node’s pivot point is (0.5, 0.5), that means center of Node.

The following table illustrates how pivot relates Offset values with Node boundaries.

| Pivot | Offset |
|---|---|
| (0,5, 0.5) |  OffsetX and OffsetY values are considered as the Node’s center point. |
| (0,0) | OffsetX and OffsetY values are considered as the top left corner of Node. |
| (1,1) | OffsetX and OffsetY values are considered as the bottom right corner of the Node. |

{% highlight xaml %}

<diagram:SfDiagram x:Name="diagram">
    <diagram:SfDiagram.Nodes>
        <diagram:DiagramCollection>
            <diagram:NodeViewModel UnitWidth="100" UnitHeight="100" OffsetX="200" OffsetY="200"
                                   Pivot="0,0">
                <diagram:NodeViewModel.Shape>
                    <RectangleGeometry Rect="0,0,10,10"/>
                </diagram:NodeViewModel.Shape>
                <diagram:NodeViewModel.ShapeStyle>
                    <Style TargetType="Path">
                        <Setter Property="Fill" Value="DarkCyan"></Setter>
                        <Setter Property="Stroke" Value="Black"/>
                        <Setter Property="StrokeThickness" Value="2"></Setter>
                        <Setter Property="Stretch" Value="Fill"></Setter>
                    </Style>
                </diagram:NodeViewModel.ShapeStyle>
            </diagram:NodeViewModel>
        </diagram:DiagramCollection>
    </diagram:SfDiagram.Nodes>
</diagram:SfDiagram>

{% endhighlight %}

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();

NodeViewModel node = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 200,
	OffsetY = 200,
	Pivot = new Point(0, 0)
};

nodes.Add(node);
diagram.Nodes = nodes;

{% endhighlight %}

![](Node_images/Node_img3.jpeg)

##Appearance

You can customize the appearance of a Node by changing its ShapeStyle. The following code illustrates how to customize the appearance of the shape.

{% highlight xaml %}

<Style TargetType="Path" x:Key="shapestyle">
  <Setter Property="Fill" Value="DarkCyan"></Setter>
  <Setter Property="Stroke" Value="Black"/>
  <Setter Property="StrokeDashArray" Value="4,5"></Setter>
  <Setter Property="StrokeThickness" Value="2"></Setter>
  <Setter Property="Stretch" Value="Fill"></Setter>   
</Style>

{% endhighlight %}

{% highlight C# %}

Style style = new Style(typeof(Path));
style.Setters.Add(new Setter(Path.FillProperty, Brushes.DarkCyan));
style.Setters.Add(new Setter(Path.StrokeProperty, Brushes.Black));
style.Setters.Add(new Setter(Path.StrokeThicknessProperty, 2d));
style.Setters.Add(new Setter(Path.StrokeDashArrayProperty, new DoubleCollection() { 5 }));            
style.Setters.Add(new Setter(Path.StretchProperty, Stretch.Fill));
return style;

{% endhighlight %}

![](Node_images/Node_img4.jpeg)

## View to ViewModel Binding

By default, View will be generated for each ViewModel and Properties of ViewModel (NodeViewModel) are bind to View (Node). We have changed this Default Behavior (ViewModel to View binding will not work).In order to achieve ViewModel to View binding, we have provided the Default Style for View in “BindingStyle.xaml”.
 
The following code illustrates how to achieve View to View Model binding by using “BindingStyle.xaml”. 

{% highlight xaml %}
 <!--For View to ViewModel binding-->
 <ResourceDictionary.MergedDictionaries>
    <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BindingStyle.xaml" />
 </ResourceDictionary.MergedDictionaries>

{% endhighlight %}

The following code illustrates how to customize the ViewModel by using Common style for View.

{% highlight xaml %}
<!--For View to ViewModel binding-->
<ResourceDictionary.MergedDictionaries>
    <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BindingStyle.xaml" />
</ResourceDictionary.MergedDictionaries>
            
<!--To apply Style for NodeViewModel,ConnectorViewModel-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
   <!--Common code for NodeViewModel-->
</Style>
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle}">
    <!--Common code for ConnectorViewModel-->
</Style>

{% endhighlight %}

N> The AutoBind property is deprecated. Instead of AutoBind, please use this View to ViewModel Binding approach.

##Interaction

Diagram provides support to drag, resize, or rotate the Node interactively. For more information about editing a Node at runtime, refer to [Interaction](/wpf/sfdiagram/Interaction "Interaction").

##Constraints

The `Constraints` property of Node allows you to enable/disable certain features. For more information about Node constraints, refer to [Node Constraints](/wpf/sfdiagram/Constraints#NodeConstraints "Node Constraints").