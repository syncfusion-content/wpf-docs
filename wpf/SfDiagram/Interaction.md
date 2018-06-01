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

An element can be selected by clicking that element. During single click, all previously selected items are cleared.

### Selecting a Group

When a child element of any Group is clicked, its contained Group is selected instead of the child element. With consecutive clicks on the selected element, selection is changed from top to bottom in the hierarchy of parent Group to its children.

### Multiple Selection

Multiple elements can be selected with the following ways.

* Ctrl+Click
* Selection rectangle / Rubber band selection

#### Ctrl+Click

During single click, any existing item in the selection list be cleared, and only the item clicked recently is there in the selection list. To avoid cleaning the old selected item, Ctrl key must be on hold when clicking.

#### Selection rectangle / Rubber band selection

Clicking and dragging the Diagram area allows to create a rectangular region. The elements that are covered under the rectangular region are selected at the end.

Multiple selected elements are visually represented as shown.

![](Interaction_images/Interaction_img5.jpeg)

* `SelectorChangedEvent` will notify you the OffsetX, OffsetY, Height, Width, Rotate Angle and interaction state with their old and new values.To explore about arguments, please refer to [SelectorChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SelectorChangedEventArgs.html) .

### Select/Unselect the elements programmatically

The `IsSelected` Property is used to select/unselect the elements at runtime.

The following code example illustrates how to select/unselect an item through programmatically.

{% tabs %}
{% highlight C# %}

// Selects an elements 

node.IsSelected = true;

// Unselect an element

node.IsSelected = false;

{% endhighlight %}
{% endtabs %}

* `ItemSelectingEvent` and `ItemSelectedEvent` for selecting an element, will notify you the item and its original source. To explore about arguments ,please refer to [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [ItemSelectedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ItemSelectedEventArgs.html) .

* `ItemUnselectingEvent` and `ItemUnselectedEvent` for unselecting an element, will notify you the item and its original source.To explore about arguments ,please refer to [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html) .

## Preview Dragging

SfDiagram provides support to drag objects as an outline without affecting original object. When multiple elements are selected, outline of every selected element will be moved.

Preview Dragging can be enabled by assigning values other than `PreviewMode.Preview` to `SfDiagram.PreviewSettings.PreviewMode`.

![](Interaction_images/PreviewDragging_img1.gif)

By default, Outline of the connectors connected to the dragging objects will be in disabled state. But, you can able to view the outline of the connectors, by holding dragging objects for certain time span. `ConnectorRefreshingSpan` property of `PreviewSettings` allows you to specify the time span and the value should be greater than 300ms.

{% tabs %}
{% highlight C# %}

this.diagram.PreviewSettings = new PreviewSettings() { PreviewMode = PreviewMode.Preview, ConnectorRefreshingSpan = 300 };

{% endhighlight %}
{% endtabs %}

![](Interaction_images/PreviewDragging_img2.gif)

### Appearance

Appearance of the preview can be modified using `PreviewStyle` property of `PreviewSettings`.

{% tabs %}
{% highlight C# %}

var previewStyle = new Style();
previewStyle.TargetType = typeof(Shape);
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeProperty, Value = new SolidColorBrush(Colors.CornflowerBlue) });
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeThicknessProperty, Value = 1.5 });
previewStyle.Setters.Add(new Setter() { Property = Shape.StrokeDashArrayProperty, Value = new DoubleCollection { 3, 3 } });
this.diagram.PreviewSettings = new PreviewSettings() { PreviewMode = PreviewMode.Preview, ConnectorRefreshingSpan = 300, PreviewStyle = previewStyle };

{% endhighlight %}
{% endtabs %}

![](Interaction_images/PreviewDragging_img3.gif)

## Dragging based on DragLimit

Diagram provides support to drag the elements within the given limitations using `EditableArea`, `ScrollLimit.Limited` property and based on `SelectorChangedEvent` enabling/disabling of dragging within the limits occur.
In `SelectorChangedEvent` based on the arguments the process occurs,
* `Block`-If this boolean expression is set true, then the dragging occurs within the given rectangular area. If dragging exceeds than the limit, then it hit back to previous position.
Based on the `BlockPosition` the dragging of Block occurs.
* Block Position
 `SourcePosition` the element moves to the previous position if it exceeds the limitation during dragging.
 `CurrentPosition` the element present at the limited area position, it does not hit back to previous position during dragging.
* `Abort`- If this boolean is set to true, then dragging is occurs within the limit.
* `Cancel`- If this boolean is set to true, then the dragging of element does not occurs.   

![](Interaction_images/dragging.gif)

## Drag and Drop Nodes over other elements

Diagram provides support to drop a node/connector over another node/connector. Drop event is raised to notify that an element is dropped over another one and it is disabled by default. It can enabled with the `AllowDrop` constraints property for both node and connector.

{% tabs %}
{% highlight C# %}

//Enable of AllowDrop Constraints for Node

Node.Constraints |= NodeConstraints.AllowDrop;

{% endhighlight %}
{% endtabs %}

* `ItemDropEvent`, `DragEnter`, `DragOver` and `DragLeave` events will notify you the Source and elements that are interacted with the dropped element(target).To explore about arguments, please refer to [ItemDropEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html) .

## Automatic Alignment

SfDiagram provide supports to arrange the nodes and connectors neatly by adjusting node's position. For example, on a diagram with full of nodes and connectors, you want to place a node without intersecting any other elements.

Using [CollisionState](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.CollisionState_members.html) and `GetCollisionFreeLocation` method, you can able to find a possible position without intersecting others for any given node.


{% tabs %}
{% highlight C# %}

// Invoking SelectorChanged Event
(this.diagram.Info as IGraphInfo).SelectorChangedEvent += OnSelectorChangedEvent;

// SelectorChanged event - custom code
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
{% endtabs %}

![](Interaction_images/AutomaticAlignment_img1.gif)

In some cases, there may requirement for repositioning overlapping objects, rather than selected object. Using `GetOverlappingObjects` method, you can able to find all overlapping objects(such as Node/Connector/Annotation) for a given node.

{% tabs %}
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
{% endtabs %}

![](Interaction_images/AutomaticAlignment_img2.gif)

### Spacing

The `Space` property of CollisionState allows you to change the spacing distance.

{% tabs %}
{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, Space = 5 };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}
{% endtabs %}

### Ignore objects as an overlap

By default, annotation's of other elements were also considered as an intercepts for any given node. This can be disabled with the help of `IncludeSubElements` property of CollisionState.

{% tabs %}
{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, IncludeSubElements = false };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}
{% endtabs %}

In addition to this,`IgnoreList` property of CollisionState allows you to restrict specific elements as not an intercepts. For example, you can ignore aligning nodes if same shaped node were collided.

![](Interaction_images/AutomaticAlignment_img3.gif)

A sample application can be downloaded from the following location:[Automatic-Alignment]http://www.syncfusion.com/downloads/support/directtrac/177341/ze/Automatic-Alignment942886659.zip

## Quick Command

### Define QuickCommand

Quick Commands are used to execute the commonly or frequently used commands around the Nodes, Connectors and Groups. There are 3 default Quick Commands for Nodes and Groups to execute Draw, Delete and Duplicate commands.

{% tabs %}
{% highlight xaml %}

<!--Style for QuickCommand-->
<Style TargetType="Path" x:Key="QuickCommandstyle">
    <Setter Property="Fill" Value="#4D4D4D"/>
    <Setter Property="StrokeThickness" Value="1"/>
    <Setter Property="Stretch" Value="Fill"></Setter>
</Style>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

QuickCommandViewModel quick = new QuickCommandViewModel();

// To define the Icon Shape
quick.Content = "F1M11.8,11.1L11.1,11.8L8,8.7L4.9,11.8L4.2,11.1L7.3,8L4.2,4.93L4.93,4.22L8,7.3L11.1,4.22L11.8,4.93L8.8,8z";

// To define the Background Shape
Shape = App.Current.Resources["Ellipse"],

// To define the Background style
quick.ShapeStyle = this.Resources["QuickCommandstyle"] as Style;

// Adding new QuickCommand object in Commands collection
(Diagram.SelectedItems as SelectorViewModel).Commands = new QuickCommandCollection
{
    quick
};

{% endhighlight %}
{% endtabs %}   

![](Interaction_images/QuickCommand_img1.jpeg)

### Appearance

Appearance of the [QuickCommand](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.QuickCommandViewModel_members.html) can be customized by using `Shape`, `ShapeStyle`, `Content` and `ContentTemplate` properties.

![](Interaction_images/QuickCommand_img2.jpg)

Please refer to the sample to achieve above customization.

Sample link :[QuickCommand](http://www.syncfusion.com/downloads/support/directtrac/199409/ze/QuickCommand_Sample1221181958.zip).

By default QuickCommand will host on Node. [VisibilityMode](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.QuickCommandViewModel~VisibilityMode.html) property is to define the host of the QuickCommand either Node or Connector or both.    

### Alignment

QuickCommand can be aligned relative to boundaries of the Node or segments of the Connector. 

* `OffsetX` and `OffsetY` property of QuickCommand is used to align the QuickCommand based on fractions. 
* `HorizontalAlignment` and `VerticalAlignment`properties are used to align the quick commands for horizontal and vertical positions.
* `Margin` is an absolute value used to add some blank space in any one of its four sides.

The Alignment of QuickCommand is similar  to [Annotation Alignment](/wpf/sfdiagram/Annotation#alignment "Alignment").   

## Automatic Port creation

We have provided support to create a Port at the intersection point on Node or Connector at runtime. This can be achieved by using the combination of SetTool and ObjectDrawnEvent.

### Enable Drawing in SetTool

This SetTool method will be invoked when Mouse/Pointer is over on Diagramming Element. In this method, We can make decision to start drawing of the Connector.

Please refer to the code example as below

{% tabs %}
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
{% endtabs %}

### Set Port for intersection

The `ObjectDrawn` event will be invoked while drawing the objects. We have provided two properties in the argument of this event to set Source and Target Port of the Connector.

Please refer to the code example as below

{% tabs %}
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
{% endtabs %}

 ConnectionIndicator animation for Node:

![](Interaction_images/Interaction_img13.jpeg)

 ConnectionIndicator animation for Connector:

![](Interaction_images/Interaction_img14.jpeg)

ConnectorPort to NodePort Connection:

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

{% tabs %}
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
{% endtabs %}

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

### FreeHand drawing

Draw Bezier connections using freehand drawing. [DrawingTool](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.DrawingTool.html) property is used to choose the FreeHand drawing.

{% tabs %}
{% highlight C# %}

// Enable the FreeHand drawing
diagram.DrawingTool = DrawingTool.FreeHand;

// Enable the Tool
//diagram.Tool = Tool.DrawOnce;

{% endhighlight %}
{% endtabs %}

![](Interaction_images/FreeHand_img1.gif)

FreeFormEvent will notify the current drawing Connector and drawing State in [FreeFormDrawingEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.FreeFormDrawingEventArgs_members.html). 

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


