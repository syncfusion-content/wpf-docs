---
layout: post
title: Supports to edit nodes, connectors and page at runtime | Syncfusion.
description: How to select, delete, zoompan and edit the user handles of the nodes and connectors during runtime?
platform: wpf
control: SfDiagram
documentation: ug
---

## Keyboard

Diagram provides support to interact with the elements with key gestures. By default, some in-built commands are bound with a relevant set of key combinations.

The following table illustrates list of Commands with key Gesture.


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
| Ctrl + Shift + U | UnGroup | UnGrouping the element in the diagram. |
| Ctrl + Shift + B | SendToBack | Moves the selected element behind all the other overlapped elements. |
| Ctrl + [ | SendBackward | Moves the selected element behind the underlying element. |
| Ctrl + Shift + F | BringFront | Brings the selected element to front over all the other overlapped elements. |
| Ctrl + ] | BringForward | Moves the selected element over the nearest overlapping element. |
| Ctrl + |Zoom | Zoom in the diagram. |
| Ctrl - | Zoom | Zoom out the diagram. |
| Ctrl + 0 (number 0) | Reset | To reset horizontal Offset, vertical Offset, and zoom level of the Diagram. |
| Ctrl + Shift + W | FitToPage | Fit the diagram content into the view with respect to either width, height, or at the whole. |
| Fn + F2 | EditAnnotation | Enable annotation editing mode of the first selected diagram element. |
| Esc | Cancel | Stop the annotation editing and accept the curent value,Clear the Keyboard focus,Clear the selection of the diagram elements,reset the diagram tool to select tool |

### SelectTool

`SelectTool` command of the [DrawingTool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_DrawingTool) helps to change the `SelectTool` and [Tool](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Tool) properties to specified values.This command will receive `SelectToolCommandParameter` as command which contains the `Tool`, `DrawingTool` and `ConnectorType` informations to enable drawing tool option in diagram.

| Shortcut Key | Tool | Description |
|---|---|---|
| Ctrl + 1 | PointerTool | Allows us to select the elements in the diagram.|
| Ctrl + 2 | TextTool | Allows you to create text node. |
| Ctrl + 3 | ConnectorTool |Allows you to create orthogonal connector by click and drag on the diagram.|
| Ctrl + 5 | FreedomTool |Allows you to create Free hand drawing connections.|
| Ctrl + 6 | LineTool |Allows you to create a straight line connector by click and drag on the diagram.|
| Ctrl + 8 | RectangleTool | Allows you to create a rectangle shaped Node by click and drag on the diagram.|
| Ctrl + 9 | EllipseTool | Allows you to create an ellipse shaped Node by click and drag on the diagram.|

To add custom commands, configure or modify key or mouse gesture through [Command Manager](/wpf/sfdiagram/commands#command-manager "Command Manager")

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Interaction/KeyboardShortcuts-sample)

## See Also

* [How to map the custom commands to existing gestures (keyboard shortcuts and mouse)?](https://www.syncfusion.com/kb/9932/how-to-map-the-custom-commands-to-existing-gestures-keyboard-shortcuts-and-mouse)

