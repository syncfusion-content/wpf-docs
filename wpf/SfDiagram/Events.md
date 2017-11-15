---
layout: post
title: Events are user actions such as key press, clicks, mouse movements, etc.
description: How to handle the various actions performed?
platform: wpf
control: SfDiagram
documentation: ug
---

## Mouse/Pointer Events

The Mouse events occurs due to user interacting with Pointing device. 

Following table describes the mouse related Events in Diagram and Diagramming elements.

| Event | Event Arguments | Description |
|---|---|---|
| MouseDown | MouseDownEventArgs | Occurs When the mouse button is pressed over the Diagram page or Diagramming Elements like Node, Connector, Port, Annotation. |
| MouseUp | MouseUpEventArgs | Occurs When the mouse button is released over the Diagram page or Diagramming Elements like Node, Connector, Port, Annotation. |
| ItemTapped | DiagramEventArgs | Occurs when the mouse button is tapped over the Diagram page or Diagramming Elements like Node, Connector, Port, Annotation. |
| ItemDoubleTapped | DiagramEventArgs | Occurs when the mouse button is double tapped over the Diagram page or Diagramming Elements like Node, Connector, Port, Annotation. |

Following table describes the details of the event arguments

### MouseDownEventArgs

| Property | Type | Description |
|---|---|---|
| Item | Object | Item returns Diagram or Diagramming elements (Node, Connector, Port, Annotation) which item is pressed by mouse point. |
| OriginalSource | Object | OriginalSource returns the Parent of the Item, which item is pressed by mouse point. <br> Diagram, Node, Connector, Port does not has OriginalSource. <br> Annotation has the OriginalSource (i.e Node/Connector) |
| MouseEventArgs | PointerPressedArgs | PointerPressedArgs has following properties. (This is Framework related arguments) <br> ButtonState <br> ChangedButton <br> ClickCount |
	
### MouseUpEventArgs 

| Property | Type | Description |
|---|---|---|
| Item | Object | Item returns Diagram or Diagramming elements (Node, Connector, Port, Annotation) which item is released by mouse point. |
| OriginalSource | Object | OriginalSource returns the Parent of the Item, which item is released by mouse point. <br> Diagram, Node, Connector, Port does not has OriginalSource. <br> Annotation has the OriginalSource (i.e Node/Connector) |
| MouseEventArgs | PointerPressedArgs | PointerPressedArgs has following properties. (This is Framework related arguments) <br> ButtonState <br> ChangedButton <br> ClickCount |

### ItemTappedEventArgs

| Property | Type | Description |
|---|---|---|
| Item | Object | Item returns Diagram or Diagramming elements (Node, Connector, Port, Annotation) which item is tapped by mouse point. |
| OriginalSource | Object | OriginalSource returns the Parent of the Item, which item is tapped by mouse point. <br> Diagram, Node, Connector, Port does not has OriginalSource. <br> Annotation has the OriginalSource (i.e Node/Connector) |

### ItemDoubleTappedEventArgs

| Property | Type | Description |
|---|---|---|
| Item | Object | Item returns Diagram or Diagramming elements (Node, Connector, Port, Annotation) which item is double tapped by mouse point. |
| OriginalSource | Object | OriginalSource returns the Parent of the Item, which item is double tapped by mouse point. <br> Diagram, Node, Connector, Port does not has OriginalSource. <br> Annotation has the OriginalSource (i.e Node/Connector) |