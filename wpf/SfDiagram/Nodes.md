---
layout: post
title: Nodes | SfDiagram | wpf | Syncfusion
description: nodes
platform: wpf
control: SfDiagram
documentation: ug
---

# Nodes

Nodes are graphical objects used to represent data in the SfDiagram.

## Creating a Node

A node can be created and added to the Diagram by using the following methods:

* Through Stencil
* Through Code

### Adding Nodes through Stencil

Drag the desired Symbol from the Stencil to the drawing area and release the pointer. The desired node is now added to the Diagram.

![](Nodes_images/Nodes_img1.png)



### Adding Nodes through Code

The NodeViewModel is implemented with the INode interface. The NodeViewModel does not have any default Shape.

{% highlight c# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();

NodeViewModel node = new NodeViewModel()

{

// Unique Guid for NodeViewModel

ID=Guid.NewGuid()               

};

nodes.Add(node);

diagramcontrol.Nodes = nodes;

{% endhighlight %}

## Setting the Node Shape and Shape Style

Shape is a type of geometry that can be customized by using ShapeStyle property. A node shape visually lies between the content and background of the node.

{% tabs %}

{% highlight xaml %}

<Style TargetType="Path" x:Key="shapestyle">

    <Setter Property="Fill" Value="DeepSkyBlue"></Setter>

    <Setter Property="StrokeThickness" Value="1"></Setter>

    <Setter Property="Stretch" Value="Fill"></Setter>

</Style>

{% endhighlight %}

{% highlight c# %}  

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();

NodeViewModel node = new NodeViewModel()

{

     UnitWidth = 75,

     UnitHeight = 50,

     //Unique Guid for NodeViewModel

     ID = Guid.NewGuid(),

     //Shape for NodeViewModel

     Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },

     //ShapeStyle

     ShapeStyle = this.Resources["shapestyle"] as Style

};

nodes.Add(node);

diagramcontrol.Nodes = nodes;

{% endhighlight %}

{% endtabs %}

![](Nodes_images/Nodes_img2.png)

## Node Content

A node is used to visually represent UI elements by using the Content property. You can host any content inside a node through the content template of the node that provides support for all the types of content.

N> Nodes can include both Content and Shape at the same time. In such a case, the Content is placed over the Shape.

{% highlight xaml %}

<!--<NodeViewModel>-->

<SynDiagram:NodeViewModel Width="110" Height="50" OffsetX="100" OffsetY="100">

<!--<Content-RatingControl>-->

<SynDiagram:NodeViewModel.Content>

<rating:SfRating ItemsCount="5" Margin="0,10,0,0">

<rating:SfRating.Resources>

<Style TargetType="rating:SfRatingItem">

<Setter Property="Width" Value="20"></Setter>

<Setter Property="Height" Value="23"></Setter>

<Setter Property="RatedFill" Value="Green"></Setter>

</Style>

</rating:SfRating.Resources>

</rating:SfRating>

</SynDiagram:NodeViewModel.Content>



<!--<Shape-Ellipse>-->

<SynDiagram:NodeViewModel.Shape>

<EllipseGeometry RadiusX="10" RadiusY="10">                                

</EllipseGeometry>

</SynDiagram:NodeViewModel.Shape>



<!--<Shape-Style>-->

<SynDiagram:NodeViewModel.ShapeStyle>

<Style TargetType="Path">

<Setter Property="Fill" Value="DeepSkyBlue"></Setter>

<Setter Property="Stretch" Value="Fill"></Setter>

</Style>

</SynDiagram:NodeViewModel.ShapeStyle>

</SynDiagram:NodeViewModel>

{% endhighlight %}

![](Nodes_images/Nodes_img4.png)

### By using Business Objects as Node Content

Business objects can also be used as node content. In such cases, the content template determines the representation of the business objects.
The following example illustrates how to add business objects to Node Content:

1. Create an Employee class.

   ~~~ csharp

		public class Employee

		{    

			public string Name

			{

				get;

				set;

			}

			public int ID

			{

				get;

				set;

			}

		}    

   ~~~

2. Create the Content Template.

   ~~~ xaml

		<DataTemplate x:Key="contenttemplate">

		<Border BorderBrush="Black" BorderThickness="2" Background="DeepSkyBlue">

		<StackPanel Orientation="Vertical">

		<TextBlock Text="{Binding Name}" Foreground="White" FontSize="12">

		</TextBlock>

		<TextBlock Text="{Binding ID}" Foreground="White" FontSize="12">

		</TextBlock>

		</StackPanel>

		</Border>

		</DataTemplate>

   ~~~

3. Add the Node Content and Content Template to the INode interface.

   ~~~ csharp

		ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();

		NodeViewModel node = new NodeViewModel()

		{

			UnitWidth = 100,

			UnitHeight = 50,

			OffsetX = 200,

			OffsetY = 200,

			// Unique Guid for NodeViewModel

			ID = Guid.NewGuid(),

		  Content = new Employee() { Name = "Kevin", ID = 3567 },    ContentTemplate = this.Resources["contenttemplate"] as DataTemplate

		};

		nodes.Add(node);

		diagramcontrol.Nodes = nodes;

   ~~~
   
   ![](Nodes_images/Nodes_img5.png)

## Node Constraints

NodeConstraints property is used to enable or disable certain behaviors of Nodes. This property is applicable only to the Node of the SfDiagram control.

_Constraints Table_

<table>
<tr>
<th>
Constraints</th><th>
Description</th></tr>
<tr>
<td>
None</td><td>
Disables all behaviors of the control.</td></tr>
<tr>
<td>
Selectable</td><td>
Enables a node to be selected.</td></tr>
<tr>
<td>
Draggable</td><td>
Enables the node to be dragged.</td></tr>
<tr>
<td>
Resizable</td><td>
Enables a node to be resized.</td></tr>
<tr>
<td>
Rotatable</td><td>
Enables a node to be rotated.</td></tr>
<tr>
<td>
InConnect</td><td>
Enables connecting to the incoming connector.</td></tr>
<tr>
<td>
OutConnect</td><td>
Enables connecting the outgoing connector.</td></tr>
<tr>
<td>
SnapToHorizontalLines</td><td>
Enables nodes to snap to horizontal gridlines.</td></tr>
<tr>
<td>
SnapToVerticalLines</td><td>
Enables nodes to snap to vertical gridlines.</td></tr>
<tr>
<td>
SnapAngle</td><td>
Enables snap while rotating.</td></tr>
<tr>
<td>
SnapToLines</td><td>
Enables nodes to snap to gridlines.</td></tr>
<tr>
<td>
Connectable</td><td>
Enables a node to connect to the connector.</td></tr>
<tr>
<td>
AllowPan</td><td>
Enables panning on the node.</td></tr>
<tr>
<td>
InheritSnapping </td><td>
Enables to inherit the value of SnapToLines and SnapAngle from the SfDiagram by SnapConstraints in SnapSettings.</td></tr>
<tr>
<td>
InheritSnapToObject </td><td>
Enables to inherit the value to SnapToObject from the SfDiagram by SnapConstraints in SnapSettings.</td></tr>
<tr>
<td>
InheritPortVisibility </td><td>
Enables to inherit the value for PortVisibility from the SfDiagram. </td></tr>
<tr>
<td>
Inherit </td><td>
Enables to inherit all the Snapping, SnapToObject, and PortVisibility from the SfDiagram. </td></tr>
<tr>
<td>
AspectRatio</td><td>
Enables node to be Resized in all the direction </td></tr>
<tr>
<td>
Default</td><td>
Enables all behaviors of the control.</td></tr>
<tr>
<td>
ResizeNorthEast</td><td>
Enables or disables resizing nodes in the north east.</td></tr>
<tr>
<td>
ResizeEast</td><td>
Enables or disables resizing nodes in the east.</td></tr>
<tr>
<td>
ResizeSouthEast</td><td>
Enables or disables resizing nodes in the south east.</td></tr>
<tr>
<td>
ResizeSouth</td><td>
Enables or disables resizing nodes in the south.</td></tr>
<tr>
<td>
ResizeSouthWest</td><td>
Enables or disables resizing nodes in the south west.</td></tr>
<tr>
<td>
ResizeWest</td><td>
Enables or disables resizing nodes in the west.</td></tr>
<tr>
<td>
ResizeNorthWest</td><td>
Enables or disables resizing nodes in the north west.</td></tr>
<tr>
<td>
ResizeNorth</td><td>
Enables or disables resizing nodes in the north.</td></tr>
</table>


The default value for NodeConstraints property is Default.

#### Example 1

The following code example illustrates how to disable Dragging a Node in the SfDiagram:

{% highlight c# %}

node.Constraints = node.Constraints &~ NodeConstraints.Selectable &~ NodeConstraints.Draggable;

{% endhighlight %}

#### Example 2

The following code example illustrates how to disable the resizing node in a particular direction.

{% highlight c# %}

//Disables Selector Thumb Resize in a particular direction

node.Constraints = node.Constraints & ~(NodeConstraints.ResizeNorthWest | NodeConstraints.ResizeNorthEast | NodeConstraints.ResizeSouthWest | NodeConstraints.ResizeSouthEast);

{% endhighlight %}

Here, node is instance of a Node.

![](Nodes_images/Nodes_img6.png)



N> NodeConstraints property is manipulated using bitwise operations. For more information about bitwise operations, see_ Bitwise Operations.

## Aspect Ratio 

Aspect Ratio is used to enable/disable proportional resizing of Nodes. When the width of a node is resized to double its value, its height also automatically doubles to maintain its Aspect Ratio.

The following code example illustrates how to enable Aspect Ratio.

{% highlight c# %} 

//Enables AspectRatio. 

node.Constraints = node.Constraints | NodeConstraints.AspectRatio;

{% endhighlight %}