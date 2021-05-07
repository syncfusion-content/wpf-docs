---
layout: post
title: Keyboard in WPF Diagram control | Syncfusion
description: Learn here all about Keyboard support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
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
| Ctrl + Shift + F | BringToFront | Brings the selected element to front over all the other overlapped elements. |
| Ctrl + ] | BringForward | Moves the selected element over the nearest overlapping element. |
| Ctrl + |Zoom | Zoom in the diagram. |
| Ctrl - | Zoom | Zoom out the diagram. |
| Ctrl + 0 (number 0) | Reset | To reset horizontal Offset, vertical Offset, and zoom level of the Diagram. |
| Ctrl + Shift + W | FitToPage | Fit the diagram content into the view with respect to either width, height, or at the whole. |
| F2 | EditAnnotation | Enable annotation editing mode of the first selected diagram element. |
| Ctrl + 1 | Pointer Tool | To select, move or resize the elements in the diagram. |
| Ctrl + 2 | Text Tool | To draw a text node. |
| Ctrl + 3 | Connector Tool | To draw a orthogonal connector. |
| Ctrl + 5 | Freehand Tool | To draw a free hand connections. |
| Ctrl + 6 | Line Tool | To draw a straight line connector. |
| Ctrl + 8 | Rectangle Tool | To draw a rectangle shaped node. |
| Ctrl + 9 | Ellipse Tool | To draw an ellipse shaped node.|
| Esc | Cancel | Stops the annotation editing or clears the selection of a diagram element. |

To add custom commands, configure or modify key or mouse gesture through [Command Manager](/wpf/sfdiagram/commands#command-manager "Command Manager")

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Interaction/KeyboardShortcuts-sample)

## See Also

* [How to map the custom commands to existing gestures (keyboard shortcuts and mouse)?](https://www.syncfusion.com/kb/9932/how-to-map-the-custom-commands-to-existing-gestures-keyboard-shortcuts-and-mouse)

