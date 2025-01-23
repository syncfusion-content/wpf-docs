---
layout: post
title: Node in WPF Diagram control | Syncfusion
description: Learn here all about Node support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Node in WPF Diagram (SfDiagram)

The nodes are graphical objects used to visually represent the geometrical information, process flow, internal business procedure, or any other kind of data, and it represents the functions of a complete system in regards of how it interacts with external entities.

![WPF Diagram Node Content](Node_images/wpf-diagram-node-content.PNG)

## Create node

A node can be created and added to the Diagram, either programmatically or interactively. Nodes are stacked on the Diagram area from bottom to top in the order they are added.

### Add Node through Nodes collection 

To create a node, you have to define the [`node object`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html) and add that to [`Nodes`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Nodes) collection of the Diagram.

{% tabs %}
{% highlight xaml %}

<!--Resource Dictionary which contains predefined shapes for Node-->
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml"/>
</ResourceDictionary.MergedDictionaries>

<!--Shape style for Node-->
<Style x:Key="ShapeStyle" TargetType="Path">
  <Setter Property="Fill" Value="#FF5B9BD5"/>
  <Setter Property="Stretch" Value="Fill"/>
  <Setter Property="Stroke" Value="#FFEDF1F6"/>
</Style>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Nodes>
    <!--Initialize the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Initialize the Node-->
      <syncfusion:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" 
                                Shape="{StaticResource Ellipse}" 
                                ShapeStyle="{StaticResource ShapeStyle}" 
                                UnitHeight="40" UnitWidth="120"/>
      </syncfusion:NodeCollection>
  </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}
{% highlight c# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize NodeCollection to SfDiagram
diagram.Nodes = new NodeCollection();
//Initialize ConnectorCollection to SfDiagram
diagram.Connectors = new ConnectorCollection();

//Creating the NodeViewModel
NodeViewModel Begin = new NodeViewModel()
{
  ID = "Begin",
  UnitWidth = 120,
  UnitHeight = 40,
  OffsetX = 300,
  OffsetY = 60,
  //Specify shape to the Node from built-in Shape Dictionary
  Shape = App.Current.Resources["Ellipse"],
  //Apply style to Shape
  ShapeStyle = App.Current.Resources["ShapeStyle"] as Style,
};

//Add Node to Nodes property of the Diagram
(diagram.Nodes as NodeCollection).Add(Begin);

{% endhighlight %}
{% endtabs %} 

Now, node will be as follows.

![WPF Diagram Adding Node](Node_images/wpf-diagram-adding-node.png)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Node/Sample-for-NodeCreation)

### Add node from stencil

Nodes can be predefined and added to the stencil and can be dropped into the Diagram when needed. For more information about adding Nodes from `Stencil`, refer to the [Stencil](https://help.syncfusion.com/wpf/diagram/stencil/stencil).

### Create node through data source

Nodes can be generated automatically with the information provided through data source. For more information about data source, refer to the [Data Source](https://help.syncfusion.com/wpf/diagram/datasource).

### Draw nodes

Nodes can be drawn interactively by clicking and dragging the Diagram surface by using the [`Drawing Tool`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DrawingTool.html). For more information about drawing nodes, refer to the [Draw Nodes](https://help.syncfusion.com/wpf/diagram/tools#shapes).

## Visualize a node

You can use text, image, controls, panels, or any UIElement or template to visualize a node as follows:
   1) Content template
   2) Content 
   3) Geometry
   4) Custom shapes
   5) Built-in resource

### Using content template
[`Node`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html) is a `ContentControl`, so you can use `DataTemplate` to display the content of the node using the [`ContentTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_ContentTemplate) property. Refer to the following code example to define node's shape through `ContentTemplate`.

{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="NodeTemplate">
  <Border BorderThickness="2" BorderBrush="Black">
      <TextBlock Text="NodeTemplate" Width="100" Height="100" Background="White"/>
  </Border>
</DataTemplate>

<!--Initialize the Node-->
<syncfusion:NodeViewModel UnitHeight="100" UnitWidth="100" 
                          OffsetX="100" OffsetY="100" 
                          ContentTemplate="{StaticResource NodeTemplate}"/>  

{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
  //sets the size
  UnitHeight = 100,
  UnitWidth = 100,
  //sets the position
  OffsetX = 100,
  OffsetY = 100,    
  ContentTemplate = App.Current.Resources["NodeTemplate"] as DataTemplate
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

### Using content

[`Node`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html) is a `ContentControl`, so you can set text, image, or any UIElement as node content using the [`Content`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_Content) property. Refer to the following code example to define image as content of the `Node`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Node-->
<syncfusion:NodeViewModel UnitHeight="100" UnitWidth="100"
                          OffsetX="100" OffsetY="100">
  <!--Assigning user image as Node's Content-->
  <syncfusion:NodeViewModel.Content>         
    <Image Source="/Image/user_image.png" Height="100" Width="100"/> 
  </syncfusion:NodeViewModel.Content>
</syncfusion:NodeViewModel>

{% endhighlight %}

{% highlight C# %}

Image img = new Image();
BitmapImage bmp = new BitmapImage();
bmp.BeginInit();
bmp.UriSource = new Uri("Image/user_image.png", UriKind.Relative);
bmp.EndInit();
img.Stretch = Stretch.Fill;
img.Source = bmp;
img.Height = 100;
img.Width = 100;  

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 100,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    //set image as content
    Content = img   
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

### Using geometry

The [`Shape`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_Shape) property of the `Node` class allows to visualize any geometry path as node's content. Refer to the following code example to define geometry for node's shape.

{% tabs %}
{% highlight xaml %}

<Style TargetType="syncfusion:Node">
  <Setter Property="ShapeStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Fill" Value="#FF5B9BD5"/>
        <Setter Property="Stretch" Value="Fill"/>
        <Setter Property="Stroke" Value="#FFEDF1F6 "/>
      </Style>
    </Setter.Value>
  </Setter>
</Style>

<!--Initialize the Node-->
<syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" 
                          OffsetX="100" OffsetY="100">
  <syncfusion:NodeViewModel.Shape>
    <RectangleGeometry Rect="100,100,100,100"/>
  </syncfusion:NodeViewModel.Shape>
</syncfusion:NodeViewModel>
   
{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 100,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    Shape = new RectangleGeometry() { Rect = new Rect(100, 100, 100, 100) }
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

### Custom shapes 

#### How to add custom shape using path data

Refer to the following code example to define custom path as node's shape.
 
{% tabs %}
{% highlight xaml %}

<!--Namespace to define String in XAML-->
xmlns:sys="clr-namespace:System;assembly=mscorlib"

<sys:String x:Key="Rectangle">
  M242,1078L231,1078L231,1067L242,1067z
</sys:String>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Nodes>
    <!--Initialize the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Initialize the Node-->
      <syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" 
                                OffsetX="100" OffsetY="100" 
                                Shape="{StaticResource Rectangle}" 
                                ShapeStyle="{StaticResource ShapeStyle}"/>
    </syncfusion:NodeCollection>
  </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>  

{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 100,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    Shape= App.Current.Resources["Rectangle"] as Style,
    //Apply style to Shape
    ShapeStyle = App.Current.Resources["ShapeStyle"] as Style,
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Custom Shape Using Path Data](Node_images/wpf-diagram-custom-shape-using-path-data.png)

#### How to add custom shape using data template

Refer to the following code example to define data template for node's custom shape,
 
{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="Square">
  <Path Stretch="Fill" Data="M242,1078L231,1078L231,1067L242,1067z" Fill="#FF5B9BD5" Stroke="#FFC4C4C4" StrokeThickness="2"/>
</DataTemplate>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Nodes>
    <!--Initialize the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Initialize the Node-->
      <syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" OffsetX="100" OffsetY="100" ContentTemplate="{StaticResource Square}" />
    </syncfusion:NodeCollection>
  </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>  

{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 100,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    ContentTemplate = this.Resources["Square"] as DataTemplate,
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Custom Node using DataTemplate](Node_images/wpf-diagram-custom-node-using-datatemplate.png)

#### How to add image as node shape

Refer to the following code example to add image as node shape,
 
{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="User">
  <Image Stretch="Uniform" HorizontalAlignment="Center" Source="Images\User.png"/>
</DataTemplate>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Nodes>
    <!--Initialize the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Initialize the Node-->
      <syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" OffsetX="100" OffsetY="100" ContentTemplate="{StaticResource User}" />
    </syncfusion:NodeCollection>
  </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>  

{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 100,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    ContentTemplate = this.Resources["User"] as DataTemplate,
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Add Image as Node Shape](Node_images/wpf-diagram-add-image-as-node-shape.png)

#### How to add framework element as node content

Refer to the following code example to add framework elements as node content,
 
{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="UserProfile">
  <Border  BorderThickness="1" Background ="#2E95D8" BorderBrush="LightGray">
    <Grid>
      <Grid.ColumnDefinitions>
        <ColumnDefinition Width="60" />
        <ColumnDefinition Width="100" />
      </Grid.ColumnDefinitions>
      <Grid Grid.Column="0">
        <Border Grid.Column="0" VerticalAlignment="Stretch" Background="Transparent" BorderBrush="#FF5DC3B1" Padding="5">
          <Image Stretch="Uniform" HorizontalAlignment="Center" Source="Images\User.png"/>
        </Border>
      </Grid>
      <Grid Grid.Column="1">
        <Grid.RowDefinitions>
          <RowDefinition Height="25" />
          <RowDefinition Height="25" />
        </Grid.RowDefinitions>
        <TextBlock x:Name="Name" Grid.Row="0"
                   HorizontalAlignment="Left"
                   VerticalAlignment="Center"
                   FontFamily="Segoe UI"
                   FontSize="12"
                   FontWeight="Bold"
                   Foreground="White"
                   Text="Daniel Tonini"
                   TextAlignment="Left" />
        <TextBlock x:Name="Designation" Grid.Row="1"
                   HorizontalAlignment="Left"
                   VerticalAlignment="Top"
                   FontFamily="Segoe UI"
                   FontSize="11"
                   FontWeight="SemiBold"
                   Foreground="White"
                   Text="Project Lead"
                   TextAlignment="Left" />
      </Grid>
    </Grid>
  </Border>
</DataTemplate>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Nodes>
    <!--Initialize the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Initialize the Node-->
      <syncfusion:NodeViewModel UnitWidth="150" UnitHeight="50" OffsetX="100" OffsetY="100" ContentTemplate="{StaticResource UserProfile}" />
    </syncfusion:NodeCollection>
  </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 50,
    UnitWidth = 150,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    ContentTemplate = this.Resources["UserProfile"] as DataTemplate,
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Framework Elements as Node Content](Node_images/wpf-diagram-framework-elements-as-node-content.png)

### Built-in resource

Some basic built-in shapes are provided as ResourceDictionary. For more information, refer to the [Shapes](https://help.syncfusion.com/wpf/diagram/shapes). 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Node/Node-with-CustomShapes)

## Position

Position of a node is controlled by using its [`OffsetX`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_OffsetX) and [`OffsetY`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_OffsetY) properties. By default, these `Offset` properties represent the distance between origin of the diagram’s page and node’s center point. You may expect this Offset values to represent the distance between page origin and node’s top left corner instead of center. The [`Pivot`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_Pivot) property helps solve this problem. Default value of node’s pivot point is (0.5, 0.5), that means center of node.

The following table explains how `Pivot` relates `Offset` values with `Node` boundaries:

| Pivot | Offset |
|---|---|
| (0,5, 0.5) |  OffsetX and OffsetY values are considered as the node’s center point. |
| (0,0) | OffsetX and OffsetY values are considered as the top left corner of node. |
| (1,1) | OffsetX and OffsetY values are considered as the bottom right corner of the node. |

{% tabs %}
{% highlight xaml %}

<!--Initialize the Node with Pivot-->
<syncfusion:NodeViewModel UnitHeight="65" UnitWidth="100" 
                          OffsetX="100" OffsetY="100" Pivot="0,0" 
                          Shape="{StaticResource Rectangle}"/>
        
{% endhighlight %}

{% highlight C# %}

//Define the Node
NodeViewModel node = new NodeViewModel()
{
    //sets the size
    UnitHeight = 65,
    UnitWidth = 100,
    //sets the position
    OffsetX = 100,
    OffsetY = 100,
    //sets the Pivot point
    Pivot=new Point(0,0),
    Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
};
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Node Position](Node_images/wpf-diagram-node-position.PNG)

## Flip

Diagram provides support to flip the node.[`Flip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_Flip) is performed to give the mirrored node of the original element.
The [`Flip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Flip.html) types are:
* **Flip**
 `Flip` that involves both vertical and horizontal changes of the element. 
* **VerticalFlip**
 `VerticalFlip` that involves changes in the vertical direction of the element.
* **HorizontalFlip**
 `HorizontalFlip` that involves changes in the horizontal direction of the element.

{% tabs %}
{% highlight xaml %}

<!--Initialize Vertical Flip to the Node-->
<syncfusion:NodeViewModel Flip="VerticalFlip" 
                          UnitHeight="100" UnitWidth="100" 
                          OffsetX="200" OffsetY="100" 
                          Shape="{StaticResource Triangle}" 
                          ShapeStyle="{StaticResource ShapeStyle}"/>
        
{% endhighlight %}

{% highlight C# %}

//Define the Node
 NodeViewModel node = new NodeViewModel()
  {
    UnitHeight = 100,
    UnitWidth = 100,        
    OffsetX=200,
    OffsetY=100,
    //Initialize Vertical Flip to the Node
    Flip = Flip.VerticalFlip,
    Shape = App.Current.Resources["Triangle"],
    ShapeStyle = App.Current.Resources["ShapeStyle"] as Style,
  };
            
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{% endtabs %}

![WPF Diagram Node Vertical Flip](Node_images/wpf-diagram-node-vertical-flip.PNG)

## Padding

`Padding` is used to leave space between the connector’s end point and the object to where it is connected. The [`ConnectorPadding`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_ConnectorPadding) property of `Node` defines the space to be left between the node bounds and its edges.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDiagram.Nodes>
  <syncfusion:NodeCollection>
    <!--Initialize connector padding to the Node-->
    <syncfusion:NodeViewModel ID="node1" ConnectorPadding="5" 
                              UnitHeight="65" UnitWidth="100" 
                              OffsetX="200" OffsetY="200" 
                              Shape="{StaticResource Rectangle}" 
                              ShapeStyle="{StaticResource ShapeStyle}"/>
    <syncfusion:NodeViewModel ID="node2" UnitHeight="65" UnitWidth="100" 
                              OffsetX="400" OffsetY="200" 
                              Shape="{StaticResource Rectangle}" 
                              ShapeStyle="{StaticResource ShapeStyle}"/>
  </syncfusion:NodeCollection>
</syncfusion:SfDiagram.Nodes>
<syncfusion:SfDiagram.Connectors>
  <syncfusion:ConnectorCollection>
    <!--Establish connection between the nodes-->
    <syncfusion:ConnectorViewModel SourceNodeID="node1" TargetNodeID="node2"/>
  </syncfusion:ConnectorCollection>
</syncfusion:SfDiagram.Connectors>

{% endhighlight %}

{% highlight c# %}

//Define NodeProperty
NodeViewModel node1 = AddNode(200,200,65,100);
//Space between Connector and Node
node1.ConnectorPadding = 5;
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node1);
NodeViewModel node2 = AddNode(400,200,65,100);
(diagram.Nodes as NodeCollection).Add(node2);
//Define ConnectorCollection
diagram.Connectors = new ConnectorCollection();
ConnectorViewModel conn1 = new ConnectorViewModel()
{
    SourceNode = node1,
    TargetNode=node2
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(conn1);

//Method for Creating Node
public NodeViewModel AddNode(double offsetX, double offsetY,double height,double width)
{
    NodeViewModel node = new NodeViewModel();
    node.OffsetX = offsetX;
    node.OffsetY = offsetY;
    node.UnitHeight = height;
    node.UnitWidth = width;
    node.Shape = new RectangleGeometry { Rect = new Rect(0, 0, 10, 10) } ;
    return node;
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram Node Padding](Node_images/wpf-diagram-node-padding.PNG)

## Appearance

You can customize the appearance of a node by changing its [`ShapeStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_ShapeStyle). The following code explains how to customize the appearance of the [`Shape`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_Shape).

{% tabs %}

{% highlight xaml %}

<Style TargetType="Path" x:key="shapestyle">
  <Setter Property="Fill" Value="#FF41719C"/>
  <Setter Property="Stretch" Value="Fill"/>
  <Setter Property="Stroke" Value="#FFEDF1F6"/>
  <Setter Property="StrokeDashArray" Value="4,5"/>
  <Setter Property="StrokeThickness" Value="2"/>
</Style>

{% endhighlight %}

{% highlight C# %}

Style style = new Style(typeof(Path));
style.Setters.Add(new Setter(Path.FillProperty, Brushes.SteelBlue));
style.Setters.Add(new Setter(Path.StrokeProperty, Brushes.WhiteSmoke));
style.Setters.Add(new Setter(Path.StrokeThicknessProperty, 2d));
style.Setters.Add(new Setter(Path.StrokeDashArrayProperty, new DoubleCollection() { 5 }));
style.Setters.Add(new Setter(Path.StretchProperty, Stretch.Fill));
return style;

{% endhighlight %}

{% endtabs %}

![WPF Diagram Custom Node using ShapeStyle](Node_images/wpf-diagram-custom-node-using-shape-style.PNG)
 
[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Node/Node-with-properties)

## Interaction

Diagram provides support to drag, resize, or rotate the node interactively. 

### Select

Node can be selected by clicking (tap) it.

* The [`IsSelected`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_IsSelected) Property is used to select or unselect the node at runtime.

* [`ItemSelectingEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemSelectingEvent) and [`ItemSelectedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemSelectedEvent) for selecting an element, will notify you the item and its original source. To explore about arguments, refer to the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [ItemSelectedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemSelectedEventArgs.html).

* [`ItemUnselectingEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemUnSelectingEvent) and [`ItemUnselectedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemUnSelectedEvent) for unselecting an element, will notify you the item and its original source. To explore about arguments, refer to the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html).

![WPF Diagram Node Selection](Node_images/wpf-diagram-node-selection.jpg)

To explore about selection and selection related events, refer to the [Selection](https://help.syncfusion.com/wpf/diagram/interaction/selection).

### Drag  

* Selected object can be dragged by clicking and dragging it. When multiple elements are selected, dragging any one of the selected elements move every selected element.

* Instead of dragging original object, preview of the node alone can be dragged. For preview dragging, refer to the [PreviewSettings](https://help.syncfusion.com/wpf/diagram/interaction/dragging/previewsettings/preview-settings). 

* While dragging, the objects are snapped towards the nearest objects to make better alignments. For better alignments, refer to the [Snapping](https://help.syncfusion.com/wpf/diagram/snapping/definesnapping "Snapping").

* The [`BoundaryConstraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ChangeEventArgs-2.html#Syncfusion_UI_Xaml_Diagram_ChangeEventArgs_2_BoundaryConstraints) argument in the [`NodeChangedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_NodeChangedEvent) is used to restrict the dragging of the Nodes in the given region.

* The [`NodeChangedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_NodeChangedEvent) will notify the [`OffsetX`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_OffsetX) and [`OffsetY`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_OffsetY) changes with their old and new values. Along with that, this event will give information about interaction state. To explore about aruguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) .

![WPF Diagram Drag Node](Node_images/wpf-diagram-drag-node.gif)

### Resize

* Selector is surrounded by eight thumbs. When dragging these thumbs, selected items can be resized smaller or larger.
* When one corner of the selector is dragged, opposite corner is in a static position.
* Enable [AspectRatio NodeConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeConstraints.html) to maintain the aspect ratio of the node when its being resized. 
* While resizing, the objects are snapped towards the nearest objects to make better alignments. For better alignments, refer to the [Snapping](https://help.syncfusion.com/wpf/diagram/snapping/definesnapping "Snapping").

* The [`NodeChangedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_NodeChangedEvent) will notify the [`UnitHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_UnitHeight) and [`UnitWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_UnitWidth) changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) .

![WPF Diagram Resize Node](Node_images/wpf-diagram-resize-node.gif)

### Rotate

* A rotate handler is placed above the selector. Clicking and dragging the handler in a circular direction lead to rotate the node.
* The node is rotated with reference to the static pivot point.
* `Pivot` thumb (thumb at the middle of the Node) appears when rotating the node to represent the static point. For more information about pivot, refer to [`Position`](https://help.syncfusion.com/wpf/diagram/node#position)

* The [`NodeChangedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_NodeChangedEvent) will notify the [`RotateAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_RotateAngle) changes with their old and new values. Along with that, this event will give information about interaction state. To explore about arguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) .

![WPF Diagram Rotate Node](Node_images/wpf-diagram-rotate-node.gif)

## Events

* The [`ItemTappedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemTappedEvent) is invoked on clicking the node. To explore about arguments, refer to the [ItemTappedEventargs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemTappedEventargs.html).
* The [`ItemDoubleTappedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemDoubleTappedEvent) is invoked on double-clicking the node. To explore about arguments, refer to the [ItemDoubleTappedEventargs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemDoubleTappedEventargs.html).
* The [`MouseDown`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_MouseDown) and [`MouseUp`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_MouseUp) are invoked as similar to framework element that is raised together with either MouseLeftButtonUp or MouseRightButtonUp. To explore about arguments, refer to the [MouseDownEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MouseDownEventArgs.html) and [MouseUpEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MouseUpEventArgs.html).  

## Constraints

The [`Constraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Node.html#Syncfusion_UI_Xaml_Diagram_Node_Constraints) property of node allows you to enable or disable certain features. For more information about node constraints, refer to the [Node Constraints](https://help.syncfusion.com/wpf/diagram/constraints#node-constraints).

## See Also
 
[How to add Annotations to the Node?](https://help.syncfusion.com/wpf/diagram/annotation)

[How to add Port to the Node?](https://help.syncfusion.com/wpf/diagram/port/port#node-port)

[How to add Nodes to the stencil?](https://help.syncfusion.com/wpf/diagram/stencil#using-the-diagram-elements)

[How to apply built-in theme for node and connector?](https://support.syncfusion.com/kb/article/9995/how-to-apply-built-in-theme-for-node-and-connector-in-wpf-diagram-sfdiagram)

[How to customize the connection indicator style of node and port?](https://support.syncfusion.com/kb/article/10048/how-to-customize-the-connection-indicator-style-of-node-and-port-in-wpf-diagram-sfdiagram)

[How to host different UI elements as node content?](https://support.syncfusion.com/kb/article/8182/how-to-host-different-ui-elements-as-node-content-in-the-wpf-diagram-sfdiagram)

[How to restrict the child node dragging whereas allow group dragging?](https://support.syncfusion.com/kb/article/9921/how-to-restrict-the-child-node-dragging-whereas-allow-group-dragging-in-wpf-diagram)

[How to restrict the node dragging within boundaries?](https://support.syncfusion.com/kb/article/6121/how-to-restrict-the-node-dragging-within-boundaries-in-the-wpf-diagram-sfdiagram)

[How to show assistants to the parent node of the organization layout?](https://support.syncfusion.com/kb/article/9115/how-to-show-assistants-to-the-parent-node-of-the-organization-layout-in-wpf-diagram)

[How to create port at runtime though SetTool?](https://support.syncfusion.com/kb/article/9967/how-to-create-port-at-runtime-through-set-tool-in-wpf-diagram-sfdiagram)

[How to customize the context menu?](https://support.syncfusion.com/kb/article/9270/how-to-customize-the-contextmenu-in-wpf-diagram-sfdiagram)

[How to drag node from one diagram to another diagram?](https://support.syncfusion.com/kb/article/6270/how-to-enable-drag-the-node-from-one-diagram-to-another-wpf-diagram-sfdiagram)

[How to restrict node’s dragging from native lane to other lanes in diagram?](https://support.syncfusion.com/kb/article/11744/how-to-restrict-nodes-dragging-from-native-lane-to-other-lanes-in-wpf-diagramsfdiagram)

[How to add ToolTip for Diagram objects of Node, NodePort in Diagram?](https://support.syncfusion.com/kb/article/11748/how-to-add-tooltip-for-diagram-objects-of-node-nodeport-in-wpf-diagramsfdiagram)

[How to add image annotations to a Node?](https://support.syncfusion.com/kb/article/6078/how-to-add-image-annotations-to-a-node-in-wpf-diagram-sfdiagram-control)

[How to notify state of operation performed on node?](https://support.syncfusion.com/kb/article/5523/how-to-notify-state-of-operation-performed-on-node-in-wpf-diagram)

[How to remove all its children nodes when deleting a parent node?](https://support.syncfusion.com/kb/article/10027/how-to-remove-all-its-children-when-deleting-a-parent-node-in-wpf-diagram-sfdiagram)

[How to restrict annotation editing by double-clicking the node or connector?](https://support.syncfusion.com/kb/article/8539/how-to-restrict-annotation-editing-by-double-clicking-the-node-or-connector-in-wpf-diagram)

[How to disable the animation while creating a connection in diagram?](https://support.syncfusion.com/kb/article/8187/how-to-disable-the-animation-while-creating-a-connection-in-wpf-diagram-sfdiagram)

[How to enable or disable the QuickCommands for node in WPF Diagram ?](https://support.syncfusion.com/kb/article/5902/how-to-enable-or-disable-quickcommands-in-wpf-diagram)

[How to bring the specific diagram object to the center or viewport of the Diagram?](https://support.syncfusion.com/kb/article/8390/how-to-bring-the-specific-object-to-the-center-or-viewport-of-the-diagram-in-wpf)

[How to programmatically Show/Hide the Annotations of node and connector?](https://support.syncfusion.com/kb/article/6281/how-to-programmatically-showhide-annotations-in-wpf-diagram-)

[How to hide the specific default QuickCommands of a node?](https://support.syncfusion.com/kb/article/11519/how-to-hide-specific-default-quickcommands-of-node-in-wpf-diagram)

[How to show the copied diagram elements as preview image along with the mouse pointer?](https://support.syncfusion.com/kb/article/12037/how-to-show-the-copied-diagram-elements-as-preview-image-along-with-the-mouse-pointer-in)

[How to serialize the Content and ContentTemplate properties of a Node?](https://support.syncfusion.com/kb/article/11574/how-to-serialize-content-and-contenttemplate-properties-of-a-node-in-wpf-diagramsfdiagram)

[How to use ContentTemplateSelector based on the Content of the Node?](https://support.syncfusion.com/kb/article/11398/how-to-use-contenttemplateselector-based-on-the-content-of-the-node)

[How to customize the appearance of the node selector?](https://support.syncfusion.com/kb/article/10605/how-to-customize-the-appearance-of-the-selector-in-wpf-diagram-sfdiagram)

[How to update the Zindex of the dragged node?](https://support.syncfusion.com/kb/article/10388/how-to-update-the-zindex-of-the-dragged-node-in-wpf-diagram-sfdiagram)

[How to restrict diagram objects dragging in the positive side?](https://support.syncfusion.com/kb/article/9917/how-to-restrict-diagram-objects-dragging-in-the-positive-side-in-wpf-diagram)

[How to use the property grid for diagram elements?](https://support.syncfusion.com/kb/article/9861/how-to-use-the-property-grid-in-the-wpf-diagram-sfdiagram)

[How to add multiple ports for Node?](https://support.syncfusion.com/kb/article/9948/how-to-add-multiple-ports-for-node-in-the-wpf-diagram-sfdiagram)

[How to override the default cursors while interact on diagram objects?](https://support.syncfusion.com/kb/article/9997/how-to-override-the-default-cursors-while-interaction-in-wpf-diagram-sfdiagram)

[How to create parent and child relationship by drag and drop nodes?](https://support.syncfusion.com/kb/article/10008/how-to-create-parent-and-child-relationship-by-drag-and-drop-nodes-in-wpf-diagram-sfdiagram)

[How to connect only with port not with node?](https://support.syncfusion.com/kb/article/8241/how-to-connect-only-with-port-not-with-node-in-wpf-diagram-sfdiagram)

[How to Notify when diagramming object is duplicated with source?](https://support.syncfusion.com/kb/article/6268/how-to-notify-when-diagramming-object-is-duplicated-with-source-in-wpf-diagram-sfdiagram)

[How to enable the behaviour of drag the node from one diagram to another diagram?](https://support.syncfusion.com/kb/article/6270/how-to-enable-drag-the-node-from-one-diagram-to-another-wpf-diagram-sfdiagram)

[How to draw nodes in diagram?](https://support.syncfusion.com/kb/article/5989/how-to-draw-node-in-wpf-diagram-sfdiagram)

[How to remove the rotator thumb of the node?](https://support.syncfusion.com/kb/article/5943/how-to-remove-rotator-of-the-node-in-wpf-diagram-sfdiagram)

[How to add space between connector decorator and node?](https://support.syncfusion.com/kb/article/5448/how-to-add-space-between-decorator-and-node-in-wpf-diagram-sfdiagram)

[How to disable the selection of diagram objects?](https://support.syncfusion.com/kb/article/5495/how-to-disable-the-selection-in-wpf-diagram)

[How to get base node interface while dropping a symbol from stencil?](https://support.syncfusion.com/kb/article/5494/how-to-get-base-node-interface-while-dropping-a-symbol-from-stencil-to-wpf-diagram)

[How to enable the AspectRatio for node?](https://support.syncfusion.com/kb/article/5473/how-to-enable-the-aspectratio-of-node-in-wpf-diagram-sfdiagram)

[How to manage the node's visibility when it is dropped onto another node in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18312/how-to-manage-the-nodes-visibility-when-it-is-dropped-onto-another-node-in-wpf-diagram-sfdiagram)

[How to use the WPF SfDiagram as the Content of the Node?](https://support.syncfusion.com/kb/article/18397/how-to-use-the-wpf-sfdiagram-as-the-content-of-the-node)

[How to Prevent Nodes from being Unselected when Right-Clicking in WPF SfDiagram?](https://support.syncfusion.com/kb/article/18348/how-to-prevent-nodes-from-being-unselected-when-right-clicking-in-wpf-sfdiagram)

[How to Obtain InConnectors and OutConnectors of Node in WPF Diagram?](https://support.syncfusion.com/kb/article/18250/how-to-obtain-inconnectors-and-outconnectors-of-node-in-wpf-diagram)

[How to highlight the node when selecting an annotation of the node and vice versa in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18245/how-to-highlight-the-node-when-selecting-an-annotation-of-the-node-and-vice-versa-in-the-wpf-diagram-sfdiagram)

[How to disable Ctrl + Drag duplicate behavior in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18502/how-to-disable-ctrl--drag-duplicate-behavior-in-wpf-diagramsfdiagram)

[How to Fit Selected Nodes and Connectors to the WPF Diagram Window?](https://support.syncfusion.com/kb/article/18062/how-to-fit-selected-nodes-and-connectors-to-the-wpf-diagram-window)

[How to add a node as a child of a container using the context menu in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18053/how-to-add-a-node-as-a-child-of-a-container-using-the-context-menu-in-the-wpf-diagram-sfdiagram)

[How to set the rotation angle for a node based on the angle of the connector decorator's shape in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17744/how-to-set-the-rotation-angle-for-a-node-based-on-the-angle-of-the-connector-decorators-shape-in-wpf-diagram-sfdiagram)

[How to set the semi-transparent color to Nodes in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17882/how-to-set-the-semi-transparent-color-to-nodes-in-the-wpf-diagram-sfdiagram)

[How to update the ShapeStyle of the selected node at runtime in WPF Diagram (SfDiagram) ?](https://support.syncfusion.com/kb/article/17728/how-to-update-the-shapestyle-of-the-selected-node-at-runtime-in-wpf-diagram-sfdiagram-)

[How to add a container as parent of the selected node using the context menu in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17747/how-to-add-a-container-as-parent-of-the-selected-node-using-the-context-menu-in-the-wpf-diagram-sfdiagram)

[How to prevent nodes from moving to a negative index when nudging in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17732/how-to-prevent-nodes-from-moving-to-a-negative-index-when-nudging-in-wpf-diagram-sfdiagram)

[How to clone the NodeViewModel in SfDiagram?](https://support.syncfusion.com/kb/article/17763/how-to-clone-the-nodeviewmodel-in-sfdiagram)

[How to apply styles to nodes based on key values in the WPF Diagram?](https://support.syncfusion.com/kb/article/16203/how-to-apply-styles-to-nodes-based-on-key-values-in-the-wpf-diagram)

[How to Get the Node or Connector in the MouseMove Event in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/15646/how-to-get-the-node-or-connector-in-the-mousemove-event-in-the-wpf-diagram-sfdiagram)

[How to Restrict Node is being removed from its Parent Container when Dragging in WPF Diagram (SfDiagram)](https://support.syncfusion.com/kb/article/15644/how-to-restrict-node-is-being-removed-from-its-parent-container-when-dragging-in-wpf-diagram-sfdiagram)

[How to avoid the node clipping while export in the WPF Diagram?](https://support.syncfusion.com/kb/article/15536/how-to-avoid-the-node-clipping-while-export-in-the-wpf-diagram)

[How to manage the visibility of node and connector objects in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/14995/how-to-manage-the-visibility-of-node-and-connector-objects-in-the-wpf-diagram-sfdiagram)

[How to customize the connection indicator style of node and port in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/10048/how-to-customize-the-connection-indicator-style-of-node-and-port-in-wpf-diagram-sfdiagram)

[How to notify state of operation performed on node in WPF Diagram?](https://support.syncfusion.com/kb/article/5523/how-to-notify-state-of-operation-performed-on-node-in-wpf-diagram)

[How to remove all its children when deleting a parent node in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/10027/how-to-remove-all-its-children-when-deleting-a-parent-node-in-wpf-diagram-sfdiagram)

[How to restrict annotation editing by double-clicking the node or connector in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/8539/how-to-restrict-annotation-editing-by-double-clicking-the-node-or-connector-in-wpf-diagram)

[How to hide specific default QuickCommands of node in WPF Diagram?](https://support.syncfusion.com/kb/article/11519/how-to-hide-specific-default-quickcommands-of-node-in-wpf-diagram)

[How to restrict Connector's source/target changing from native Nodes to other Nodes in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/11796/how-to-restrict-connectors-source-target-changing-from-native-nodes-to-other-nodes-in-wpf)

[How to serialize Content and ContentTemplate properties of a Node in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/11574/how-to-serialize-content-and-contenttemplate-properties-of-a-node-in-wpf-diagramsfdiagram)

[How to create filled PolyLine Node in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/10255/how-to-create-filled-polyline-node-in-wpf-diagram-sfdiagram)

[How to bring the specific node to the center or viewport in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/9918/how-to-bring-the-specific-node-to-the-center-or-viewport-in-wpf-diagram-sfdiagram)

[How to switch the visibility of an icon in the ContentTemplate in WPF Diagram (SfDiagram) ?](https://support.syncfusion.com/kb/article/17725/how-to-switch-the-visibility-of-an-icon-in-the-contenttemplate-in-wpf-diagram-sfdiagram-)