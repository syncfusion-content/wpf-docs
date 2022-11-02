---
layout: post
title: Keyboard in WPF Diagram control | Syncfusion
description: Learn here all about Keyboard support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Keyboard support in WPF Diagram

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
| LeftArrow | MoveLeft | MoveLeft (move the selected elements towards the left by one pixel). |
| Shift + LeftArrow | MoveLeft | MoveLeft (move the selected elements towards the left by ten pixels). |
| RightArrow | MoveRight | MoveRight (move the selected elements towards the right by one pixel). |
| Shift + RightArrow | MoveRight | MoveRight (move the selected elements towards the right by ten pixels). |
| UpArrow | MoveUp | MoveUp (move the selected elements upwards by one pixel). |
| Shift + UpArrow | MoveUp | MoveUp (move the selected elements upwards by ten pixels). |
| DownArrow | MoveDown | MoveDown (move the selected elements downwards by one pixel). |
| Shift + DownArrow | MoveDown | MoveDown (move the selected elements downwards by ten pixels). |
| MouseScroll | Zoom | Scrolls the diagram page up and down in a vertical direction. |
| Shift + MouseScroll | Zoom | Scrolls the diagram page left and right in a horizontal direction. |
| Ctrl + MouseScroll | Zoom | Zoom(Zoom in/Zoom out the diagram). |
| Ctrl + G | Group | Grouping the element in the diagram. |
| Ctrl + Shift + U | UnGroup | UnGrouping the element in the diagram. |
| Ctrl + Shift + B | SendToBack | Moves the selected element behind all the other overlapped elements. |
| Ctrl + [ | SendBackward | Moves the selected element behind the underlying element. |
| Ctrl + Shift + F | BringToFront | Brings the selected element to front over all the other overlapped elements. |
| Ctrl + ] | BringForward | Moves the selected element over the nearest overlapping element. |
| Ctrl + PlusKey(+)|Zoom | Zoom in the diagram. |
| Ctrl + MinusKey(-)| Zoom | Zoom out the diagram. |
| Ctrl + 0 (number 0) | Reset | To reset horizontal Offset, vertical Offset, and zoom level of the Diagram. |
| Ctrl + Shift + W | FitToPage | Fit the diagram content into the view with respect to either width, height, or at the whole. |
| F2 | EditAnnotation | Enable annotation editing mode of the first selected diagram element. |
| Enter | SelectFocusedItem | Selects the focused item. |
| Tab | FocusToNextItem | Focus on the item next to the selected item. |
| Shift + Tab | FocusToPreviousItem | Focus on the item previous to the selected item. |
| Ctrl + R | RotateRight | Rotates the selected node clockwise to 90 degrees. |
| Ctrl + L | RotateLeft | Rotates the selected node anticlockwise to 90 degrees. |
| Ctrl + H | HorizontalFlip | Flips the selected node in a horizontal direction. |
| Ctrl + J | VerticalFlip | Flips the selected node in a vertical direction. |
| Ctrl + B | ToggleBold | Adds and removes the Bold text style to the annotation. |
| Ctrl + I | ToggleItalic | Adds and removes the Italic text style to the annotation. |
| Ctrl + U | ToggleUnderline | Adds and removes the Underline text style to the annotation. |
| Ctrl + 1 | Pointer Tool | To select, move or resize the elements in the diagram. |
| Ctrl + 2 | Text Tool | To draw a text node. |
| Ctrl + 3 | Connector Tool | To draw a orthogonal connector. |
| Ctrl + 5 | Freehand Tool | To draw a free hand connections. |
| Ctrl + 6 | Line Tool | To draw a straight line connector. |
| Ctrl + 8 | Rectangle Tool | To draw a rectangle shaped node. |
| Ctrl + 9 | Ellipse Tool | To draw an ellipse shaped node.|
| Esc | Cancel | Stops the annotation editing or clears the selection of a diagram element. |

To add custom commands, configure or modify key or mouse gesture through [Command Manager](/wpf/diagram/commands/alignment#command-manager "Command Manager")

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Interaction/KeyboardShortcuts-sample)

## See Also

* [How to map the custom commands to existing gestures (keyboard shortcuts and mouse)?](https://www.syncfusion.com/kb/9932/how-to-map-the-custom-commands-to-existing-gestures-keyboard-shortcuts-and-mouse)

