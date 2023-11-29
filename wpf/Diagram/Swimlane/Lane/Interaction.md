---
layout: post
title: Visualize graphical object using Swimlanes | Syncfusion
description: How to select, resize(with and without selection) and swap the lane and how to add the child element into lane?
platform: wpf
control: SfDiagram
documentation: ug
---

# Lane interaction in WPF Diagram(SfDiagram)

The diagram provides support to select, resize, or swap the lane interactively. 

### Select

A Lane can be selected by clicking (tap) the [`header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.LaneViewModel.html#Syncfusion_UI_Xaml_Diagram_LaneViewModel_Header) of the lane.

## Resizing lane

* Lane can be resized in the bottom and right direction.
* Lane can be resized by using the resize selector of the lane.
* Lane can be resized by resizing the bottom and right border of the lane without make a selection.
* Once you can resize the lane, the swimlane will be resized automatically.
* The lane can be resized either resizing the selector or the tight bounds of the child object. If the child node move to edge of the lane it can be automatically resized.
* The [`SwimlaneChildChangedEvent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_SwimlaneChildChangedEvent) will notify the [`UnitHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildViewModel_UnitHeight) and [`UnitWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildViewModel_UnitWidth) changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [SwimlaneChildChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html) 
The following image shows how resize the lane.

![Lane Resizing](../Swimlane-images/Lane_Resize.gif)

## Lane swapping

* Lanes can be swapped by dragging the lanes over another lane.
* Helper should intimate the insertion point while lane swapping.
The following image shows how swapping the lane.
* The `SwimlaneChildChangedEvent` will notify the [`RowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildChangedEventArgs.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildChangedEventArgs_RowIndex) and [`ColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildChangedEventArgs.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildChangedEventArgs_ColumnIndex) changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [SwimlaneChildChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html) 

![Lane Swapping](../Swimlane-images/Lane_Swapping.gif)

## Children interaction in lanes

* You can resize the child node within swimlanes.
* You can drag the child nodes within lane.
* Interchange the child nodes from one lane to another lane.
* Drag and drop the child nodes from lane to diagram.
* Drag and drop the child nodes from diagram to lane.
* Based on the child node interactions,the lane size should be updated.
The following image show children interaction in lane.

![Lane Children Interaction](../Swimlane-images/Child_Interaction.gif)

## See Also

* [How to restrict node’s dragging from native lane to other lanes in diagram?](https://www.syncfusion.com/kb/13208/how-to-restrict-nodes-dragging-from-native-lane-to-other-lanes-in-wpf-diagramsfdiagram)