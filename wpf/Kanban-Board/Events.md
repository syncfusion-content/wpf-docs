---
layout: post
title: Events in WPF Kanban Board control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF Kanban Board (SfKanban) control, its elements and more.
platform: wpf
control: SfKanban
documentation: ug
---

# Events in WPF Kanban Board (SfKanban)

## CardTapped

This event is triggered when you tap on any card. The argument contains the following information.

* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn)          - Used to get the column of the selected card.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard) 			- Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex) 			- Used to get the index of the card in a column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's  column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfKanban. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference, based on which the event argument is shown.

>**NOTE**
The default value of the `CardTappedCommandParameter` is `null`.

## CardDoubleTapped

The [`CardDoubleTapped`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.SfKanban.html) event is triggered when you double tap on any card. The argument contains the following information:

* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedCard) - Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedCardIndex) - Used to get the index of dragging card in a column.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDoubleTappedEventArgs_SelectedColumn) - Used to get the column of the selected card.

## CardDragStart

This event is triggered when you start to drag a card. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragStartEventArgs_IsCancel)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard)			- Used to get the underlying model of the card.
* [`KeepCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragStartEventArgs_KeepCard)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) 	- Used to get the source column of card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex)		- Used to get the index of the card in source column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.

## CardDragEnd  

This event is triggered when whenever dragging is canceled. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_IsCancel)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex)		- Used to get the index of the card in source column.
* [`TargetKey`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetKey) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetColumn)	- Used to get the current column which is the drop target for the card.
* [`TargetCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetCardIndex)		- Used to get the index of the card in target column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.
* [`TargetRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetRowIndex) - Used to get the target row index where the card is going to be inserted.
* [`TargetColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEndEventArgs_TargetColumnIndex) - Used to get the target column index where the card is going to be inserted.

## CardDragEnter 

This event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_IsCancel)				- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard)				- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) 		- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex)			- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentColumn)		- Used to get the column upon which the card enters.
* [`CurrentIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentIndex)			- Used to get the index of the card in current column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentRowIndex) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEnterEventArgs_CurrentColumnIndex) - Used to get the current index of the card's column.

## CardDragLeave 

This event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard)                - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn)        - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex)         - Used to get the index of the card in source column.
* [`LeftColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_LeftColumn)		- Used to get the column from which the card leaves.
* [`PreviousCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousCardIndex)   -   used to get the index of the card left.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.
* [`PreviousRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousRowIndex) - Used to get the previous card's row index while drag enter into next column.
* [`PreviousColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragLeaveEventArgs_PreviousColumnIndex) - Used to get the previous card's column index while drag enter into next column.

## CardDragOver

This event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_IsCancel)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCard)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumn) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedCardIndex)		- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentColumn)	- Used to get the current column which is the drop target for the card.
* [`CurrentIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentIndex)		- Used to get the new index of the card in current column.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedColumnIndex) - Used to get the index of dragging card's column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragEventArgs_SelectedRowIndex) - Used to get the index of dragging card's row.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentRowIndex) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanDragOverEventArgs_CurrentColumnIndex) - Used to get the current index of the card's column.

## ColumnsGenerated 

This event will be fired after the columns are generated automatically. You can access the auto-generated columns using SfKanban.ActualColumns property.


## ColumnGenerated

This event is triggered when a column generated.

* [`Columns`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnsGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnsGeneratedEventArgs_Columns)  -  used to get the generated columns.
* [`IsCancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnGeneratedEventArgs_IsCancel)   -  used to cancel the generated column added to the SfKanban.
* [`CurrentColumn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs.html#Syncfusion_UI_Xaml_Kanban_KanbanColumnGeneratedEventArgs_CurrentColumn)   -   used to get the current generated column.
