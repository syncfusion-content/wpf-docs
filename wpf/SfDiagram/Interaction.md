---
layout: post
title: Interactively edit nodes and connectors during runtime.
description: How to select and edit nodes and connectors during runtime?
platform: wpf
control: SfDiagram
documentation: ug
---

# Interaction

## Selection

Selector provides a visual representation of selected elements. It behaves like a container and enables you to update the size, position, and rotation angle of the selected elements through interaction and programmatically. Single or multiple elements can be selected at a time.

### Single Selection

An element can be selected by clicking that element. During single click, all previously selected items are cleared. The following image shows how the selected elements are visually represented.

![](Interaction_images/Interaction_img2.jpeg)

![](Interaction_images/Interaction_img4.jpeg)

### Selecting a Group

When a child element of any Group is clicked, its contained Group is selected instead of the child element. With consecutive clicks on the selected element, selection is changed from top to bottom in the hierarchy of parent Group to its children.

### Multiple Selection

Multiple elements can be selected with the following ways.

1. Ctrl+Click

During single click, any existing item in the selection list be cleared, and only the item clicked recently is there in the selection list. To avoid cleaning the old selected item, Ctrl key must be on hold when clicking.

2. Selection rectangle / Rubber band selection

Clicking and dragging the Diagram area allows to create a rectangular region. The elements that are covered under the rectangular region are selected at the end.

Multiple selected elements are visually represented as shown.

![](Interaction_images/Interaction_img5.jpeg)

* `SelectorChangedEvent` will notify you the OffsetX, OffsetY, Height, Width, Rotate Angle and interaction state with their old and new values.To explore about arguments, please refer to [SelectorChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SelectorChangedEventArgs.html) .

### Select/Unselect the elements programmatically

The IsSelected Property is used to select/unselect the elements at runtime.

The following code example illustrates how to select/unselect an item through programmatically.

{% tabs %}
{% highlight C# %}

// Selects an elements 

node.IsSelected = true;

// Unselect an element

node.IsSelected = false;

{% endhighlight %}
{% endtabs %}

## Events 

* `ItemSelectingEvent` and `ItemselectedEvent` for selecting an element, will notify you the item and its original source. To explore about arguments ,please refer to [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [ItemSelectedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ItemSelectedEventArgs.html) .

* `ItemUnselectingEvent` and `ItemUnselectedEvent` for unselecting an element, will notify you the item and its original source.To explore about arguments ,please refer to [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html) .

## Preview Dragging

SfDiagram provides support to drag objects as an outline without affecting original object. When multiple elements are selected, outline of every selected element will be moved.

Preview Dragging can be enabled by assigning values other than `PreviewMode.Preview` to `SfDiagram.PreviewSettings.PreviewMode`.

![](Interaction_images/PreviewDragging_img1.gif)

By default, Outline of the connectors connected to the dragging objects will be in disabled state. But, you can able to view the outline of the connectors, by holding dragging objects for certain time span. `ConnectorRefreshingSpan` property of `PreviewSettings` allows you to specify the time span and the value should be greater than 300ms.

{% highlight C# %}

this.diagram.PreviewSettings = new PreviewSettings() { PreviewMode = PreviewMode.Preview, ConnectorRefreshingSpan = 300 };

{% endhighlight %}

![](Interaction_images/PreviewDragging_img2.gif)

### Appearance

Appearance of the preview can be modified using `PreviewStyle` property of `PreviewSettings`.

{% highlight C# %}

var previewStyle = new Style();
previewStyle.TargetType = typeof(Shape);
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeProperty, Value = new SolidColorBrush(Colors.CornflowerBlue) });
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeThicknessProperty, Value = 1.5 });
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeDashArrayProperty, Value = new DoubleCollection { 3, 3 } });
this.diagram.PreviewSettings = new PreviewSettings() { PreviewMode = PreviewMode.Preview, ConnectorRefreshingSpan = 300, PreviewStyle = previewStyle };

{% endhighlight %}

![](Interaction_images/PreviewDragging_img3.gif)

## Drag and Drop Nodes over other elements

Diagram provides support to drop a node/connector over another node/connector. Drop event is raised to notify that an element is dropped over another one and it is disabled by default. It can enabled with the `AllowDrop` constraints property for both node and connector.

{% tabs %}
{% highlight C# %}

//Enable of AllowDrop Constraints for Node

Node.Constraints |= NodeConstraints.AllowDrop;

{% endhighlight %}
{% endtabs %}

## Events

* `ItemDropEvent`, `DragEnter`, `DragOver` and `DragLeave` events will notify you the Source and elements that are interacted with the dropped element(target).To explore about arguments, please refer to [ItemDropEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html) .

## Automatic Alignment

SfDiagram provide supports to arrange the nodes and connectors neatly by adjusting node's position. For example, on a diagram with full of nodes and connectors, you want to place a node without intersecting any other elements.

Using `GetCollisionFreeLocation` method, you can able to find a possible position without intersecting others for any given node.

{% highlight C# %}

// Invoking SelectorChanged Event
(this.diagram.Info as IGraphInfo).SelectorChangedEvent += OnSelectorChangedEvent;

{% endhighlight %}

{% highlight C# %}

private void OnSelectorChangedEvent(object sender, SelectorChangedEventArgs args)
{
    // Need to adjust selected node's position, if it in contact with any other elements on drag complete
    if (args.Item is SelectorViewModel && args.NewValue.InteractionState == NodeChangedInteractionState.Dragged)
    {
        var selectorViewModel = (SelectorViewModel)args.Item;
        if (selectorViewModel.Nodes is IEnumerable<object>)
        {
            var selectedNodes = ((IEnumerable<object>)selectorViewModel.Nodes).ToList();
            if (selectedNodes.Count == 1 && selectedNodes[0] is NodeViewModel)
            {
                var selectedNode = (NodeViewModel)selectedNodes[0];
                var collisionState = new CollisionState() { Item = selectedNode };
                ((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);
                        
                // Re-arranging node's position
                selectedNode.OffsetX = collisionState.Offset.X;
                selectedNode.OffsetY = collisionState.Offset.Y;
            }
        }
    }
}

{% endhighlight %}

![](Interaction_images/AutomaticAlignment_img1.gif)

In some cases, there may requirement for repositioning overlapping objects, rather than selected object. Using `GetOverlappingObjects` method, you can able to find all overlapping objects(such as Node/Connector/Annotation) for a given node.

{% highlight C# %}

private void OnSelectorChangedEvent(object sender, SelectorChangedEventArgs args)
{
    if (args.Item is SelectorViewModel && args.NewValue.InteractionState == NodeChangedInteractionState.Dragged)
    {
        var selectorViewModel = (SelectorViewModel)args.Item;
        if (selectorViewModel.Nodes is IEnumerable<object>)
        {
            var selectedNodes = ((IEnumerable<object>)selectorViewModel.Nodes).ToList();
            if (selectedNodes.Count == 1 && selectedNodes[0] is NodeViewModel)
            {
                var selectedNode = (NodeViewModel)selectedNodes[0];
                var collisionState = new CollisionState() { Item = selectedNode };
                
                // Finding overlapping nodes & connectors for the selected node.
                var intercepts = ((IGraphInfo)this.diagram.Info).GetOverlappingObjects(collisionState);

                foreach (var intercept in intercepts)
                {
                    if (intercept is NodeViewModel)
                    {
                        var intersectingNode = (NodeViewModel)intercept;
                        var collisionState1 = new CollisionState() { Item = intersectingNode };
                        ((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState1);

                        // Re-arranging node's position
                        intersectingNode.OffsetX = collisionState1.Offset.X;
                        intersectingNode.OffsetY = collisionState1.Offset.Y;
                    }
                }
            }
        }
    }
}

{% endhighlight %}

![](Interaction_images/AutomaticAlignment_img2.gif)

### Spacing

The `Space` property of CollisionState allows you to change the spacing distance.

{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, Space = 5 };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}

### Ignore objects as an overlap

By default, annotation's of other elements were also considered as an intercepts for any given node. This can be disabled with the help of `IncludeSubElements` property of CollisionState.

{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, IncludeSubElements = false };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}

In addition to this,`IgnoreList` property of CollisionState allows you to restrict specific elements as not an intercepts. For example, you can ignore aligning nodes if same shaped node were collided.

![](Interaction_images/AutomaticAlignment_img3.gif)

A sample application can be downloaded from the following location:

http://www.syncfusion.com/downloads/support/directtrac/177341/ze/Automatic-Alignment942886659 

## QuickCommand

QuickCommands are used to execute the commonly or frequently used commands around the Nodes, Connectors and Groups. There are 3 default QuickCommands for Nodes and Groups to execute Draw, Delete and Duplicate commands.

### Create QuickCommand

QuickCommand can be created and added in Commands collection programmatically. It can be set for either Node or Connector or both. 

### Add QuickCommand through Commands collection

To create a QuickCommand, you have to define the QuickCommand object and add that to Commands collection of the SelectorViewModel.

The following code example illustrates how to create and add a Quick Command in Commands Collection.

{% highlight xml %}
<!--Style for QuickCommand-->

<Style TargetType="Path" x:Key="QuickCommandstyle">

<Setter Property="Fill" Value="#4D4D4D"/>

<Setter Property="StrokeThickness" Value="1"/>

<Setter Property="Stretch" Value="Fill"></Setter>

</Style>

{% endhighlight %}

{% highlight c# %}
QuickCommandViewModel quick = new QuickCommandViewModel();

// To define the Icon Shape

quick.Content = "F1M11.8,11.1L11.1,11.8L8,8.7L4.9,11.8L4.2,11.1L7.3,8L4.2,4.93L4.93,4.22L8,7.3L11.1,4.22L11.8,4.93L8.8,8z";

// To define the Background Shape

quick.Shape = "F1M23.467,11.733C23.467,18.213 18.214,23.466 11.734,23.466 5.253,23.466 0,18.213 0,11.733 0,5.253 5.253,0 11.734,0 18.214,0 23.467,5.253 23.467,11.733";

// To define the Background style

quick.ShapeStyle = this.Resources["QuickCommandstyle"] as Style;

// Adding new QuickCommand object in Commands collection

(Diagram.SelectedItems as SelectorViewModel).Commands = new QuickCommandCollection
{

quick

};

{% endhighlight %}

![](Interaction_images/QuickCommand_img1.jpeg)


### Appearance

Appearance of the QuickCommand can be modified by Shape, ShapeStyle, Content and ContentTemplate.

The following table illustrates the definition of the Shape,ShapeStyle,Content and ContentTemplate.

| Property | Description |
|---|---|
| Shape | To define the shape of the background area by set any path data. |
| ShapeStyle | To define the style for the background area by set the Style with TargetType of Path. |
| Content | To define the Icon shape by set any path Data. |
| ContentTemplate |To define the Icon shape by set any DataTemplate. |

![](Interaction_images/QuickCommand_img2.jpg)

The below code example illustrates, how to use customize the appearance of the QuickCommand. 

{% highlight xml %}
<!--Style for QuickCommand-->

<Style TargetType="Path" x:Key="CustomQuickCommandstyle">

<Setter Property="Fill" Value="Indigo"></Setter>

<Setter Property="Stroke" Value="LightCoral"></Setter>

<Setter Property="StrokeThickness" Value="2"></Setter>

<Setter Property="Stretch" Value="Fill"></Setter>

</Style>

<!--ContentTemplate for QuickCommand-->

<DataTemplate x:Key="Template">

<Image HorizontalAlignment="Center" VerticalAlignment="Center" Width="18" Height="18" Source="{Binding Path=Content,RelativeSource={RelativeSource Mode=TemplatedParent}}"/>

</DataTemplate>

{% endhighlight %}

{% highlight c# %}
QuickCommandViewModel Quick = new QuickCommandViewModel();

// To define the Icon Shape

Quick.Content = "./Image/Icon_Delete.png";

Quick.OffsetX = 0;

Quick.OffsetY = 0.5;

// To define the Icon Template

Quick.ContentTemplate = this.Resources["Template"] as DataTemplate;

Quick.Margin = new Thickness( -25,0, 0, 0);

// To define the Background Shape

Quick.Shape = "M0.5,0.5L25.5,0.5L25.5,25.557L0.5,25.557z";

Quick.Command = (Diagram.Info as IGraphInfo).Commands.Zoom;

ZoomPositionParamenter parameter = new ZoomPositionParamenter()
 {
  ZoomCommand = ZoomCommand.ZoomIn
 };
Quick.CommandParameter = parameter;

// To define the Background style

Quick.ShapeStyle = this.Resources["CustomQuickCommandstyle"] as Style;

// Adding new QuickCommand object in Commands collection

(Diagram.SelectedItems as SelectorViewModel).Commands = new QuickCommandCollection

{

Quick

};

{% endhighlight %}

![](Interaction_images/QuickCommand_img3.jpg)

N>To define the host of the QuickCommand either Node or Connector or both. By default, the VisibilityMode as Node. The following code example illustrates to represent the VisibilityMode.

{% highlight c# %}
// Set QuickCommand Visibility for Node
quick.VisibilityMode = VisibilityMode.Node;

// Set QuickCommand Visibility for Connector
quick.VisibilityMode = VisibilityMode.Connector;
{% endhighlight %}

### Alignment

QuickCommand can be aligned relative to boundaries of the Node or segments of the Connector. It has Margin, Offset, Horizontal and Vertical Alignment settings. It is quite tricky when all four alignments are used together but gives you more control over alignment.

### Offset

The `OffsetX` and `OffsetY` property of QuickCommand is used to align the QuickCommand based on fractions. 0 represents Top / Left corner, 1 represents Bottom / Right corner, and 0.5 represents half of Width / Height.

### Horizontal and Vertical alignments

The `HorizontalAlignment` property of QuickCommand is used to set how the QuickCommand is horizontally aligned at the QuickCommand position and its can determined from the fraction values. The `VerticalAlignment` property is used to set how QuickCommand is vertically aligned at the QuickCommand position.

The following table illustrates all the possible alignments visually with `Offset (0, 0)`.


| Horizontal Alignment | Vertical Alignment | Output with OffsetX and OffsetY as (0,0)|
|---|---|---|
| Left | Top | ![](Interaction_images/QuickCommand_img4.jpeg) |
| Center | | ![](Interaction_images/QuickCommand_img5.jpeg) |
| Right | | ![](Interaction_images/QuickCommand_img6.jpeg) |
| Left | Center | ![](Interaction_images/QuickCommand_img7.jpeg) |
| Center | | ![](Interaction_images/QuickCommand_img8.jpeg) |
| Right | | ![](Interaction_images/QuickCommand_img9.jpeg) |
| Left | Bottom | ![](Interaction_images/QuickCommand_img10.jpeg) |
| Center | | ![](Interaction_images/QuickCommand_img11.jpeg) |
| Right | | ![](Interaction_images/QuickCommand_img12.jpeg) |


### Margin

`Margin` is an absolute value used to add some blank space in any one of its four sides. You can displace the QuickCommand with the `Margin` property. The following code example illustrates how to align a QuickCommand based on its Offset, HorizontalAlignment, VerticalAlignment and Margin values.

{% highlight c# %}
quick.Margin=new Thickness(0,70,0,0);

HorizontalAlignment = HorizontalAlignment.Left;

VerticalAlignment = VerticalAlignment.Top;

{% endhighlight %}

![](Interaction_images/QuickCommand_img13.jpeg)

### QuickCommand Interaction 

### Command

Command is used to execute the certain action. By default, diagram have several commands. For more information about Commands, refer to [Commands](/wpf/sfdiagram/Commands "Commands").

### DragCommand

We can define the Commands which are needed to be executed while dragging the QuickCommand. This DragCommand will be executed when click on QuickCommand and move the mouse while keeping the mouse button pressed State. 

Example: Duplicate, Draw  

### CommandParameter

A parameter can be passed through the "CommandParameter" property. CommandParameter is effective only for the parameter required Commands. ( Example: ZoomIn and ZoomOut)

## Automatic Port creation

We have provided support to create a Port at the intersection point on Node or Connector at runtime. This can be achieved by using the combination of SetTool and ObjectDrawnEvent.

### Enable Drawing in SetTool

This SetTool method will be invoked when Mouse/Pointer is over on Diagramming Element. In this method, We can make decision to start drawing of the Connector.

Please refer to the code example as below

{% highlight C# %}

//Override the SetTool method
protected override void SetTool(SetToolArgs args)
{
    if (args.Source is INode || args.Source is IConnector)
    {
    	args.Action = ActiveTool.Draw;
    }
    else
    {
    	base.SetTool(args);
    }
}

{% endhighlight %}

### Set Port for intersection

The `ObjectDrawn` event will be invoked while drawing the objects. We have provided two properties in the argument of this event to set Source and Target Port of the Connector.

Please refer to the code example as below

{% highlight C# %}

//Hook the ObjectDrawn Event
(diagram.Info as IGraphInfo).ObjectDrawn += MainWindow_ObjectDrawn;

+private void MainWindow_ObjectDrawn(object sender, ObjectDrawnEventArgs args)
{
    //SourcePort should be set on Started state
    if (args.State == DragState.Started)
    {
    	if (args.Item is IConnector)
        {
        	IConnector connector = args.Item as IConnector;
        	if (connector.SourceNode != null)
        	{
            	if ((connector.SourceNode as NodeViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.SourceNode as NodeViewModel).Ports = new ObservableCollection<IPort>();

				//Set the TargetPort as NodePort to the Node
                args.SourcePort = new NodePortViewModel();
			}
            if (connector.SourceConnector != null)
            {
            	if ((connector.SourceConnector as ConnectorViewModel).Ports == null)
            		//Initialize the Port collection
                	(connector.SourceConnector as ConnectorViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as ConnectorPort to the Connector
                args.SourcePort = new ConnectorPortViewModel();
         	}
		}
	}

	//TargetPort should be set on Started state
    if (args.State == DragState.Completed)
    {
    	if (args.Item is IConnector)
        {
        	IConnector connector = args.Item as IConnector;
            if (connector.TargetNode != null)
            {
            	if ((connector.TargetNode as NodeViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.TargetNode as NodeViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as NodePort to the Node
                args.TargetPort = new NodePortViewModel();
			}
            if (connector.TargetConnector != null)
            {
          		if ((connector.TargetConnector as ConnectorViewModel).Ports == null)
                	//Initialize the Port collection
                    (connector.TargetConnector as ConnectorViewModel).Ports = new ObservableCollection<IPort>();
				//Set the TargetPort as ConnectorPort to the Connector
                args.TargetPort = new ConnectorPortViewModel();
        	}
		}
	}
}

{% endhighlight %}

## ConnectionIndicator animation for Node

![](Interaction_images/Interaction_img13.jpeg)

## ConnectionIndicator animation for Connector

![](Interaction_images/Interaction_img14.jpeg)

## ConnectorPort to NodePort Connection

![](Interaction_images/Interaction_img15.jpeg)

## Customization and Validation on Connector Ends

This support used to decide on which element Connector is going dock with diagramming object at runtime.

### ConnectionParameter
This is used to Gets or sets the arguments to the ConnectionParameter. Here we are listed the arguments as below:


| Type | Name | Type | Description |
|---|---|---|---|
| Property | Connector | object | Returns the Connector which is edited at runtime. |
| Property | SourceNode | object | Defines the specific Node as Source of Connector. |
| Property | TargetNode | object | Defines the specific Node as Target of Connector. |
| Property | SourcePort | IPort | Defines the specific Port as Source of Connector. |
| Property | TargetPort | IPort | Defines the specific Port as Target of Connector. |
| Property | SourcePoint | Point | Defines the specific Point as Source of Connector. |
| Property | TargetPoint | Point | Defines the specific Point as Source of Connector. |
| Property | ConnectorEnd | ConnectorEnd | Returns the Connector end which is edited at runtime.

public enum ConnectorEnd
    {
        Source,
        Target,
    } |
| Property | SourceConnector | object | Defines the specific Connector as Source of Connector. |
| Property | TargetConnector | object | Defines the specific Connector as Target of Connector. |


The following code illustrates how to override ValidateConnection

[C#]

{% highlight C# %}

/// <summary>
/// Create custom class for diagram
/// </summary>
public class CustomDiagram : SfDiagram
{
     /// <summary>
    /// Override the validate connection
    /// </summary>
    /// <param name="args">Gets args value</param>
    protected override void ValidateConnection(ConnectionParameter args)
    {
        // set the target node and target port
        if (args.TargetPort == null && args.TargetNode != null)
        {
            if (args.TargetNode is NodeViewModel)
            {
                NodeViewModel node = args.TargetNode as NodeViewModel;
                if (node.Ports != null && (node.Ports as ObservableCollection<IPort>).Count() > 0)
                {
                    args.TargetPort = (node.Ports as ObservableCollection<IPort>)[0];
                }
            }
        }
    }
}

{% endhighlight %}

![](Interaction_images/Interaction_img16.jpg)


## Hit Padding

 Defines the connection with diagramming elements when the connector enters vicinity area of the diagramming elements.

For more information about HitPadding for Node, refer to [Hit Padding](/wpf/sfdiagram/Node#hit-padding "Hit Padding").
For more information about HitPadding for Connector, refer to [Hit Padding](/wpf/sfdiagram/Connector#hit-hadding "Hit Padding").

## Zoom pan 

* When a large Diagram is loaded, only certain portion of the Diagram is visible. The remaining portions are clipped. Clipped portions can be explored by scrolling the scrollbars or panning the Diagram.

* Diagram can be zoomed in or out by using Ctrl + mouse wheel.

## Drawing Tools

Drawing tool allow you to draw any kind of node/connector during runtime by clicking and dragging on the Diagram page.

### Shapes

To draw a shape, You have to activate the drawing tool by using the Tool property and you need to set the event for GetDrawType.

{% tabs %}
{% highlight xaml %}

<Style TargetType="Path" x:Key="shapestyle">
  <Setter Property="Fill" Value="#fbe172"></Setter>
  <Setter Property="Stroke" Value="Black"/>
  <Setter Property="Stretch" Value="Fill"></Setter>
</Style>

<Style TargetType="{x:Type diagram:Node}">
  <Setter Property="Shape" Value="M13.560 67.524 L 21.941 41.731 L 0.000 25.790 L
                                  27.120 25.790 L 35.501 0.000 L 43.882 25.790 L 71.000 
                                  25.790 L 49.061 41.731 L 57.441 67.524 L 35.501 
                                  51.583 z"></Setter>
 <Setter Property="ShapeStyle" Value="{StaticResource shapestyle}"></Setter>
</Style>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

//GetDrawType event is used to specify which item have to be drawn by the user.

(diagram.Info as IGraphInfo).GetDrawType += MainWindow_GetDrawType;
diagram.DrawingTool = DrawingTool.Node;
diagram.Tool = Tool.ContinuesDraw;

private void MainWindow_GetDrawType(object sender, DrawTypeEventArgs args)
{
	args.DrawItem = new TextBlock()
	{
		Text="Path",
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center
	};
}

{% endhighlight %}
{% endtabs %}

![](Tools_images/Tools_img2.jpeg)

* `GetDrawType` event will invoke when start drawing and get DrawItem (i.e which item you will draw) from the user.To explore about arguments, please refer to the [DrawTypeEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DrawTypeEventArgs.html) .

### Connectors

To draw Connectors, you have to set the Connector to DrawingTool property. The drawing tool can be activated by using the Tool property as shown. The following code example illustrates how to draw a straight line Connector.

{% tabs %}
{% highlight xaml %}

<Style x:Key="decoratorstyle" TargetType="Path">
  <Setter Property="Stroke" Value="Black" />
  <Setter Property="Fill" Value="Black" />
  <Setter Property="StrokeThickness" Value="1" />
</Style>

<Style TargetType="Path" x:Key="connectorstyle">
  <Setter Property="Stroke" Value="Black"></Setter>
  <Setter Property="StrokeThickness" Value="2"></Setter>
</Style>

<Style TargetType="{x:Type diagram:Connector}">
  <Setter Property="TargetDecoratorStyle" Value="{StaticResource decoratorstyle1}"/>
  <Setter Property="ConnectorGeometryStyle" Value="{StaticResource connectorstyle}"/>
</Style>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

diagram.DrawingTool = DrawingTool.Connector;
diagram.Tool = Tool.DrawOnce;

{% endhighlight %}
{% endtabs %}

![](Tools_images/Tools_img3.jpg)

Diagram allows you to establish connection with Node/Port as soon as you click on the Node/Port.

* `ObjectDrawn` event will invoke with drawing state.To explore about arguments,  please refer to the [ObjectDrawnEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ObjectDrawnEventArgs.html) .

## Keyboard

Diagram provides support to interact with the elements with key gestures. By default, some in-built commands are bound with a relevant set of key combinations.

The following table illustrates List of Commands with key Gesture.



| Shortcut Key | Command | Description |
|---|---|---|
| Ctrl + A | Select all | Select all the Nodes/Connectors in diagram. |
| Ctrl + C | Copy | Copy the selected elements in the diagram. |
| Ctrl + X | Cut | Cut the selected elements in the diagram. |
| Ctrl + V | Paste | Paste the cut or copy the elements in the diagram. |
| Ctrl + Z | Undo | Undo(Reverse the last editing action performed on diagram). |
| Ctrl + Y | Redo | Redo(Restores the last editing action when no other actions have occurred since the last undo on diagram). |
| Ctrl + D | Duplicate | Copies the selected element from the diagram and pastes the copied element into the diagram. |
| Delete | Delete | Delete the selected elements in the diagram. |
| LeftArrow | MoveLeft | MoveLeft (move the selected elements towards left by one pixel). |
| RightArrow | MoveRight | MoveRight (move the selected elements towards right by one pixel). |
| UpArrow | MoveUp | MoveUp (move the selected elements towards up by one pixel). |
| DownArrow | MoveDown | MoveDown (move the selected elements towards up by one pixel). |
| Ctrl + MouseScroll | Zoom | Zoom(Zoom in/Zoom out the diagram). |
| Ctrl + G | Group | Grouping the element in the diagram. |
| Ctrl + G | UnGroup | UnGrouping the element in the diagram. |
| Ctrl + Shift + [ | SendToBack | Moves the selected element behind all the other overlapped elements. |
| Ctrl + [ | SendBackward | Moves the selected element behind the underlying element. |
| Ctrl + Shift + ] | BringFront | Brings the selected element to front over all the other overlapped elements. |
| Ctrl + ] | BringForward | Moves the selected element over the nearest overlapping element. |

To add custom commands, configure or modify key/mouse gesture through [Command Manager](/wpf/sfdiagram/Commands#command-manager "Command Manager");


