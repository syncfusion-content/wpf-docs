---
layout: post
title: Visually represent the geometrical informations, process flow, or entities.
description: How to visually represent the geometrical information and process flows as nodes?
platform: wpf
control: SfDiagram
documentation: ug
---

# Node

Nodes are graphical objects used to visually represent the geometrical information, process flow, internal business procedure or any other kind of data and it represents the functions of a complete system in regards to how it interacts with external entities

![](Node_images/Node_img1.jpeg)

## Shapes

We have provided some basic built-in shapes as ResourceDictionary.For more information, refer to  [Shapes](/wpf/sfdiagram/Shapes). 

## Create Node

A Node can be created and added to the Diagram, either programmatically or interactively. Nodes are stacked on the Diagram area from bottom to top in the order they are added.

### Add Node through Nodes collection 

To create a Node, You have to define the Node object and add that to Nodes collection of the Diagram.
For more, refer to  [Add Nodes](/wpf/sfdiagram/Getting-Started#simple Application:Add Nodes "Add Nodes"). 

### Add Node from stencil

Nodes can be predefined and added to palette and can be dropped into the Diagram when needed. For more information about adding Nodes from Stencil, refer to [Stencil](/wpf/sfdiagram/Stencil "Stencil").

### Create Node through data source

Nodes can be generated automatically with the information provided through data source.For more information about data source, 

refer to [Data Source](/wpf/sfdiagram/DataSource "DataSource").

### Draw Nodes

Nodes can be interactively drawn by clicking and dragging the Diagram surface by using **Drawing Tool**. For more information about drawing Nodes, refer to [Draw Nodes](/wpf/sfdiagram/Tools#drawing-tools:shapes "Draw Nodes").

## Position

Position of a Node is controlled by using its OffsetX and OffsetY properties. By default, these Offset properties represent the distance between origin of the Diagram’s page and Node’s center point. You may except this Offset values to represent the distance between page origin and Node’s top left corner instead of center. Pivot property helps solve this problem. Default value of Node’s pivot point is (0.5, 0.5), that means center of Node.

The following table illustrates how pivot relates Offset values with Node boundaries.

| Pivot | Offset |
|---|---|
| (0,5, 0.5) |  OffsetX and OffsetY values are considered as the Node’s center point. |
| (0,0) | OffsetX and OffsetY values are considered as the top left corner of Node. |
| (1,1) | OffsetX and OffsetY values are considered as the bottom right corner of the Node. |

{% tabs %}
{% highlight xaml %}
<!--Style for Node-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
    <Setter Property="Shape" Value="{StaticResource Rectangle}"/>
    <Setter Property="ShapeStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Fill" Value="DarkCyan"/>
                <Setter Property="Stroke" Value="Black"/>
                <Setter Property="StrokeThickness" Value="2"/>
                <Setter Property="Stretch" Value="Fill"/>
            </Style>
        </Setter.Value>
    </Setter>
</Style>
{% endhighlight %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram  x:Name="diagram">
    <!--Initialize NodeCollection-->
    <syncfusion:SfDiagram.Nodes>
        <syncfusion:NodeCollection>
            <!--Initialize Node-->
            <syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" OffsetX="200" OffsetY="200"
                                      Pivot="0,0">
            </syncfusion:NodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Creates the Node collection
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
//Create Node
NodeViewModel node = new NodeViewModel()
{
    //Sets the size
	UnitWidth = 100,UnitHeight = 100,   
    //Sets the position
	OffsetX = 200,OffsetY = 200,
    //Sets pivot point
	Pivot = new Point(0, 0)
};
//Adds the Node to the SfDiagram 
nodes.Add(node);
diagram.Nodes = nodes;
{% endhighlight %}
{% endtabs %}

![](Node_images/Node_img3.jpeg)

## Appearance

You can customize the appearance of a Node by changing its ShapeStyle. The following code illustrates how to customize the appearance of the shape.

{% tabs %}
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
{% endtabs %}

![](Node_images/Node_img4.jpeg)

## Data Binding

In order to achieve Properties of ViewModel are bind to View, we have provided the default style for View in “BindingStyle.xaml”. For more information, refer to [Data Binding](/wpf/sfdiagram/Data-Binding).

N> The AutoBind property is deprecated. Instead of AutoBind, please use this View to ViewModel Binding approach.

## Interaction

Diagram provides support to drag, resize, or rotate the Node interactively. For more information about editing a Node at runtime, refer to [Interaction](/wpf/sfdiagram/Interaction "Interaction").

## Hit Padding

Connection can be made from/to Nodes, Connectors, Port or on empty area in a diagram. Making connection with Connector and Ports are usually difficult as thickness are usually small. To make it easy to connect, it should be possible to connect when mouse comes near its vicinity area.

The following code illustrates how to customize the HitPadding 

{% tabs %}
{% highlight xaml %}

<syncfusion:NodeViewModel x:Name="ViewModel"  UnitWidth="100" HitPadding="25"
                                              UnitHeight="100" OffsetX="200" OffsetY="300">
</syncfusion:NodeViewModel>

{% endhighlight %}
{% highlight C# %}
//Creates the Node collection
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
//Create Node
NodeViewModel node = new NodeViewModel()
{
    //Sets the size
	UnitWidth = 100,UnitHeight = 100,   
    //Sets the position
	OffsetX = 200,OffsetY = 300,
    //Sets pivot point
	Pivot = new Point(0, 0),
    //defines the vicinity area of the Node
    HitPadding = 25
};
//Adds the Node to the SfDiagram 
nodes.Add(node);
diagram.Nodes = nodes;
{% endhighlight %}
{% endtabs %}

![](Node_images/Node_img5.jpg)

## Constraints

The `Constraints` property of Node allows you to enable/disable certain features. For more information about Node constraints, refer to [Node Constraints](/wpf/sfdiagram/Constraints#nodeconstraints "Node Constraints").