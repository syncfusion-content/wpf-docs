---
layout: post
title: Supports to drag nodes, connectors and page at runtime | Syncfusion.
description: How to drag the nodes and connectors and avoid overlapping of the nodes with connectors during runtime?
platform: wpf
control: SfDiagram
documentation: ug
---
## Collision State in WPF Diagram (SfDiagram)

SfDiagram provide supports to arrange the nodes and connectors neatly by adjusting node's position. For example, on a diagram with full of nodes and connectors, you want to place a node without intersecting any other elements.

Using [CollisionState](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CollisionState.html) and [GetCollisionFreeLocation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_GetCollisionFreeLocation_Syncfusion_UI_Xaml_Diagram_CollisionState_) method, you can able to find a possible position without intersecting others for any given node.


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

![Find and position the node without overlapping](Drag_images/AutomaticAlignment_img1.gif)

In some cases, there may be requirement for repositioning overlapping objects, rather than selected object. Using [GetOverlappingObjects](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_GetOverlappingObjects_Syncfusion_UI_Xaml_Diagram_CollisionState_) method, you can able to find all overlapping objects(such as Node or Connector or Annotation) for a given node.

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

![Position the intersection object when currently dragging node get intersected](Drag_images/AutomaticAlignment_img2.gif)

## Spacing

The [Space](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CollisionState.html#Syncfusion_UI_Xaml_Diagram_CollisionState_Space) property of [CollisionState](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CollisionState.html) allows you to change the spacing distance.

{% tabs %}
{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, Space = 5 };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}
{% endtabs %}

## Ignore objects as an overlap

By default, annotation's of other elements were also considered as an intercepts for any given node. This can be disabled with the help of [IncludeSubElements](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CollisionState.html#Syncfusion_UI_Xaml_Diagram_CollisionState_IncludeSubElements) property of CollisionState.

{% tabs %}
{% highlight C# %}

var selectedNode = (NodeViewModel)selectedNodes[0];
var collisionState = new CollisionState() { Item = selectedNode, IncludeSubElements = false };
((IGraphInfo)this.diagram.Info).GetCollisionFreeLocation(collisionState);

{% endhighlight %}
{% endtabs %}

In addition to this,[IgnoreList](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CollisionState.html#Syncfusion_UI_Xaml_Diagram_CollisionState_IgnoreList) property of CollisionState allows you to restrict specific elements as not an intercepts. For example, you can ignore aligning nodes if same shaped node were collided.

![list to ignore detect overlapping](Drag_images/AutomaticAlignment_img3.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Collision%20State).

