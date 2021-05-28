---
layout: post
title: Events in WPF GridData Control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF GridDataControl (Classic) control, its elements and more details.
platform: wpf
control: GridData (Classic)
documentation: ug
---
# Events in WPF GridDataControl (Classic)

The GridData control declares a number of events that it can handle, in response to the activities either by the end user or by the system. An event is a message that is handled, to notify an object or a class of the occurrence of an action. When an event is handled, all the event handlers are notified.

The GridData control offers technical benefits by declaring all its events as Routed Events. Hence, being the high level visual element in the visual tree, it need not hook the same event on all of its descendants (e.g. rows, columns and cells), such as MouseMove. Instead, it hooks the event on itself and hence, when the mouse moves over one of its descendants, the grid can be notified appropriately, whenever the event is handled without expecting its descendants to notify it.

## Subscribing to Events

In order to get event notifications, the grid needs to be wired up with the required events. This process is called as subscribing to the events. It can be done using either XAML or C# code.

{% tabs %}

{% highlight xaml %}

<syncfusion:GridDataControl x:Name="dataGrid" AutoPopulateColumns="True" ItemsSource="{StaticResource ordersSource}"

MouseMove="dataGrid_MouseMove">

{% endhighlight  %}

{% highlight c# %}

this.dataGrid.MouseMove+=new MouseEventHandler(dataGrid_MouseMove);

{% endhighlight  %}

{% endtabs %}


For either of the above code languages, you should have the following C# code to handle the MouseMove event.

{% highlight c# %}

private void dataGrid_MouseMove(object sender, MouseEventArgs e)

{

    Console.WriteLine("Mouse cursor Postion:" + e.GetPosition(sender as IInputElement));

}

{% endhighlight  %}

N> These Grid WPF mouse events are more advantageous than using any other default mouse events because the default mouse events are controlled by Mouse Controller that makes it very hard to access the underlying data; whereas in case of Grid mouse events, it is directly possible to access the underlying data easily.

## Unsubscribe the events

If you do not want the grid to listen to the event, you can unwire the event from the grid as follows.

{% highlight c# %}

this.dataGrid.MouseMove-=new MouseEventHandler(dataGrid_MouseMove);

{% endhighlight %}

_GridData Control Events_

<table>
<tr>
<th>
Event</th><th>
Description</th></tr>
<tr>
<td>
CurrentCellActivating</td><td>
This event is handled before the grid activates the specified cell as current cell.</td></tr>
<tr>
<td>
CurrentCellActivated</td><td>
This event is handled after the grid activates the specified cell as current cell.</td></tr>
<tr>
<td>
CurrentCellActivateFailed</td><td>
This event is handled after the grid fails to activate a specific cell as current cell.</td></tr>
<tr>
<td>
CurrentCellDeactivating</td><td>
This event is handled before the grid deactivates the current cell.</td></tr>
<tr>
<td>
CurrentCellDeactivated</td><td>
This event is handled after the grid deactivates current cell.</td></tr>
<tr>
<td>
CurrentCellDeactivateFailed</td><td>
This event is handled after the grid fails to deactivate the current cell.</td></tr>
<tr>
<td>
CurrentCellConfirmChangesFailed</td><td>
This event is handled when the grid fails to save the changes made to the active current cell.</td></tr>
<tr>
<td>
CurrentCellAcceptedChanges</td><td>
This event is handled when the grid accepts the changes made to the active current cell.</td></tr>
<tr>
<td>
CurrentCellChanging</td><td>
This event is handled when the user wants to modify contents of the current cell.</td></tr>
<tr>
<td>
CurrentCellStartEditing</td><td>
This event is handled before the current cell switches to the editing mode.</td></tr>
<tr>
<td>
CurrentCellEditingComplete</td><td>
This event is handled when the grid completes editing the active current cell.</td></tr>
<tr>
<td>
CurrentCellRejectedChanges</td><td>
This event is handled when the grid rejects the changes made to the active current cell.</td></tr>
<tr>
<td>
CurrentCellChanged</td><td>
This event is handled when the user changes the contents of the current cell.</td></tr>
<tr>
<td>
CurrentCellMoved</td><td>
This event is handled when the current cell is successfully moved to a new position.</td></tr>
<tr>
<td>
CurrentCellMoveFailed</td><td>
This event is handled when the current cell fails to move to a new position.</td></tr>
<tr>
<td>
CurrentCellMoving</td><td>
This event is handled when the current cell is about to be moved to a new position.</td></tr>
<tr>
<td>
CurrentCellValidating</td><td>
This event is handled when the grid is validating the contents of the active current cell.</td></tr>
<tr>
<td>
CurrentCellValidated</td><td>
This event is handled when the grid has completed validating the contents of the active current cell.</td></tr>
<tr>
<td>
CellButtonClick</td><td>
This event is handled when the button in the grid cell is clicked.</td></tr>
<tr>
<td>
DropDownSelectionChanged</td><td>
This event is handled when the selected item in the grid drop-down is changed.</td></tr>
<tr>
<td>
CellClick</td><td>
This event is handled when the grid cell is clicked.</td></tr>
<tr>
<td>
CellCursor</td><td>
This event is handled when the cell has a cursor.</td></tr>
<tr>
<td>
CellMouseHoverEnter</td><td>
This event is handled when the mouse hits the cell and signals that the cell wants to handle the mouse events. This event is handled before the CellMouseHover event.</td></tr>
<tr>
<td>
CellMouseHover</td><td>
This event is handled when the mouse is moved over a grid cell.</td></tr>
<tr>
<td>
CellMouseHoverLeave</td><td>
This event is handled when the mouse leaves a cell.</td></tr>
<tr>
<td>
CellMouseDown</td><td>
This event is handled when the mouse button is pressed.</td></tr>
<tr>
<td>
CellMouseMove</td><td>
This event is handled when the mouse is moved over the cell.</td></tr>
<tr>
<td>
CellMouseUp</td><td>
This event is handled when the mouse button is released.</td></tr>
<tr>
<td>
CellCancelMode</td><td>
This event is handled when any current user interaction is canceled, example-Cancel select cells when Escape key is pressed.</td></tr>
<tr>
<td>
CellRestoreMode</td><td>
This event is handled when a cell is trying to restore the canceled changes.</td></tr>
<tr>
<td>
ResizingColumns</td><td>
This event is handled when the user is about to resize a column or is in the process of re-sizing a column.</td></tr>
<tr>
<td>
QueryAllowDragColumn</td><td>
This event is handled when the user hovers over a column header  or drags a column header using mouse.</td></tr>
<tr>
<td>
ResizingRows</td><td>
This event is handled when the user is about to resize a row or is in the process of re-sizing a row.</td></tr>
<tr>
<td>
RowValueCommitting</td><td>
This event triggers before the RowValue commit. This event works only when the UpdateMode is RowCacheMode.</td></tr>
<tr>
<td>
RowValueCommitted</td><td>
This event triggers after the RowValue commit. This event works only when the UpdateMode is RowCacheMode.</td></tr>
<tr>
<td>
RowValueCommittingCancelled</td><td>
If the RowValue committing is canceled in the RowValueCommitting event, then the RowValueCommittingCancelled event is fired. This event works only when the UpdateMode is RowCacheMode.</td></tr>
<tr>
<td>
RowValidating</td><td>
This event triggers when the focus moves from the current row to any other row.</td></tr>
</table>
