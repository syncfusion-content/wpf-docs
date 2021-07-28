---
layout: post
title: Selection in WPF Spreadsheet control | Syncfusion
description: Learn here all about Selection support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Selection in WPF Spreadsheet (SfSpreadsheet)

This section explains about the Selection behavior in SfSpreadsheet.

The SfSpreadsheet control provides support for selection in grid by using mouse, keyboard and touch interactions.

By default, Selection behavior will be enabled in `SfSpreadsheet`,but if you want to disable the selection in SfSpreadsheet, then set the [AllowSelection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_AllowSelection) Property to be false.

{% tabs %}
{% highlight c# %}
void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    spreadsheet.ActiveGrid.AllowSelection = false;
}
{% endhighlight %}
{% endtabs %}

## Accessing the Current cell

SfSpreadsheet allows the user to access the active cell by using the `CurrentCell` property of [SelectionController](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SelectionController.html) Class.

{% tabs %}
{% highlight c# %}
var cell= spreadsheet.ActiveGrid.SelectionController.CurrentCell;
{% endhighlight %}
{% endtabs %}

## Accessing the Selected ranges

SfSpreadsheet allows the user to access the selected ranges of the `SpreadsheetGrid` using [SelectedRanges](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectedRanges) property of `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}
var rangeList = spreadsheet.ActiveGrid.SelectedRanges;
{% endhighlight %}
{% endtabs %}

N> To get the active range in the selected ranges list, use [ActiveRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridRangeInfoList.html#Syncfusion_UI_Xaml_CellGrid_GridRangeInfoList_ActiveRange) property of [GridRangeInfoList](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridRangeInfoList.html) class.

## Adding or Clearing the Selection

SfSpreadsheet allows the user to add and clear the selection in the Active `SpreadsheetGrid` for the given range.

{% tabs %}
{% highlight c# %}
//To Add the Selection for range,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cells(4,6,5,8));

//To Add the Selection for particular row,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Row(4));

//To Add the Selection for multiple rows,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Rows(4,9));

//To Add the Selection for particular column,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Col(5));

//To Add the Selection for multiple columns,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cols(5,10));

//To Clear the Selection,
spreadsheet.ActiveGrid.SelectionController.ClearSelection();
{% endhighlight %}
{% endtabs %}

## Move Current Cell

SfSpreadsheet allows the user to move the current cell to the mentioned cell in `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}

//Moves current cell to the mentioned row and column index of cell,
spreadsheet.ActiveGrid.CurrentCell.MoveCurrentCell(5, 5);

//For moving the current cell to a different sheet,
spreadsheet.SetActiveSheet("Sheet2");
spreadsheet.ActiveGrid.CurrentCell.MoveCurrentCell(6, 5);

{% endhighlight %}
{% endtabs %}

## Converting GridRangeInfo into IRange

SfSpreadsheet allows the user to convert the `GridRangeInfo` into the equivalent `IRange` by using [ConvertGridRangeToExcelRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.Helpers.GridExcelHelper.html#Syncfusion_UI_Xaml_Spreadsheet_Helpers_GridExcelHelper_ConvertGridRangeToExcelRange_Syncfusion_UI_Xaml_CellGrid_GridRangeInfo_Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_) method of [GridExcelHelper](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.Helpers.GridExcelHelper.html) class.

{% tabs %}
{% highlight c# %}
var excelRange = GridExcelHelper.ConvertGridRangeToExcelRange(GridRangeInfo.Cell(4, 5), spreadsheet.ActiveGrid);
{% endhighlight %}
{% endtabs %}

T> Users can also convert the `IRange` into equivalent `GridRangeInfo` by using [ConvertExcelRangeToGridRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.Helpers.GridExcelHelper.html#Syncfusion_UI_Xaml_Spreadsheet_Helpers_GridExcelHelper_ConvertExcelRangeToGridRange_Syncfusion_XlsIO_IRange_) method of  [GridExcelHelper](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.Helpers.GridExcelHelper.html) class.

## Properties, Methods and Events

Below table lists the events associated with selection behavior,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
{{ '[CellClick](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html) ' | markdownify }}</td><td>
 Occurs when you click on the cell.</td></tr>
<tr>
<td>
{{ '[CurrentCellActivating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html)' | markdownify }}</td><td>
Occurs when the current cell is going to be activated. This event allow to cancel the current cell activation.</td></tr>
<tr>
<td>
{{ '[CurrentCellActivated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html)' | markdownify }}</td><td>
Occurs after the current cell is activated.</td></tr>
<tr>
<td>
{{ '[SelectionChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html)' | markdownify }}</td><td>
Occurs when the selection is going to be changed. This event allows to cancel the selection change.</td></tr>
<tr>
<td>
{{ '[SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html)' | markdownify }}</td><td>
Occurs after the selection is changed.</td></tr>
</table>

Below table lists the properties associated with selection,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[SelectedRanges](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectedRanges)' | markdownify }}</td><td>
Gets or sets the collection of selected ranges from grid.</td></tr>
<tr>
<td>
{{ '[SelectionBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectionBrush)' | markdownify }}</td><td>
Gets or sets the selected area brush.</td></tr>
<tr>
<td>
{{ '[SelectionBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectionBorderBrush)' | markdownify }}</td><td>
Gets or sets the selection border brush.</td></tr>
<tr>
<td>
{{ '[SelectionBorderThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectionBorderThickness)' | markdownify }}</td><td>
Gets or sets the thickness of selection border.</td></tr>
<tr>
<td>
{{ '[SelectionController](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_SelectionController) ' | markdownify }}</td><td>
Gets the Selection Controller which provides the selection of content when the user drags the pressed mouse to an edge of the control.</td></tr>
<tr>
<td>
{{ '[AllowSelection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_AllowSelection) ' | markdownify }}</td><td>
Gets or Sets the value whether to allow the selection in the ActiveGrid or not.</td></tr>
<tr>
<td>
{{ '[ShowTouchIndicator](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SelectionController.html#Syncfusion_UI_Xaml_CellGrid_SelectionController_ShowTouchIndicator) ' | markdownify }}</td><td>
Determines whether the touch indicator will be shown or not.</td></tr>
<tr>
<td>
{{ '[TouchHitTestPrecision](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SelectionController.html#Syncfusion_UI_Xaml_CellGrid_SelectionController_TouchHitTestPrecision) ' | markdownify }}</td><td>
Gets or sets the distance of touch precision point from touch indicator.</td></tr>
</table>
 
Below table lists the properties associated with [CurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_CurrentCell) of SpreadsheetGrid,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[CellRowColumnIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_CellRowColumnIndex) ' | markdownify }}</td><td>
Gets the row and column index of the CurrentCell.</td></tr>
<tr>
<td>
{{ '[RowIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_RowIndex) ' | markdownify }}</td><td>
Gets the row index of the CurrentCell.</td></tr>
<tr>
<td>
{{ '[ColumnIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_ColumnIndex) ' | markdownify }}</td><td>
Gets the column index of the CurrentCell.</td></tr>
<tr>
<td>
{{ '[Range](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_Range) ' | markdownify }}</td><td>
Gets the range of the CurrentCell.</td></tr>
<tr>
<td>
{{ '[HasCurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_HasCurrentCell) ' | markdownify }}</td><td>
 Gets the value indicating whether the Grid has CurrentCell or not.</td></tr>
<tr>
<td>
{{ '[PreviousRowColumnIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_PreviousRowColumnIndex) ' | markdownify }}</td><td>
Gets or sets the row and column index of old CurrentCell.</td></tr>
</table>

Below table lists the methods associated with selection,

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
{{ '[AddSelection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SelectionController.html#Syncfusion_UI_Xaml_CellGrid_SelectionController_AddSelection_Syncfusion_UI_Xaml_CellGrid_GridRangeInfo_)' | markdownify }}</td><td>
Adds/Extends the Selection to the mentioned range .</td></tr>
<tr>
<td>
{{ '[ClearSelection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SelectionController.html#Syncfusion_UI_Xaml_CellGrid_SelectionController_ClearSelection)' | markdownify }}</td><td>
Clears the Selection.</td></tr>
<tr>
<td>
{{ '[MoveCurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.GridCurrentCell.html#Syncfusion_UI_Xaml_CellGrid_GridCurrentCell_MoveCurrentCell_Syncfusion_UI_Xaml_Grid_ScrollAxis_RowColumnIndex_System_Boolean_)' | markdownify }}</td><td>
Move the Current cell to mentioned row and column index.</td></tr>
</table>

## Key Navigation

Below table lists the key combinations associated with selection,

<table>
<tr>
<th>
Key Combination</th><th>
Description</th></tr>
<tr>
<td>
HOME</td><td>
Moves to the first cell of the current row .</td></tr>
<tr>
<td>
END</td><td>
Moves to the last cell of the current row .</td></tr>
<tr>
<td>
UPARROW
</td><td>
Moves to one cell up of the current cell in the worksheet.</td></tr>
<tr>
<td>
DOWNARROW
</td><td>
Moves to one cell down of the current cell in the worksheet.</td></tr>
<tr>
<td>
LEFTARROW
</td><td>
Moves to one cell left of the current cell in the worksheet.</td></tr>
<tr>
<td>
RIGHTARROW
</td><td>
Moves to one cell right of the current cell in the worksheet.</td></tr>
<tr>
<td>
PAGEUP</td><td>
Moves to the first visible cell of the current column.</td></tr>
<tr>
<td>
PAGEDOWN</td><td>
Moves to the last visible cell of the current column.</td></tr>
<tr>
<td>
CTRL+HOME</td><td>
Moves to the beginning cell of a worksheet.</td></tr>
<tr>
<td>
CTRL+END</td><td>
Moves to the last cell of a worksheet.</td></tr>
<tr>
<td>
ALT+PAGE UP</td><td>
Moves one screen to the left in a worksheet.</td></tr>
<tr>
<td>
ALT+PAGE DOWN</td><td>
Moves one screen to the right in a worksheet.</td></tr>
<tr>
<td>
CTRL + ARROW KEYS</td><td>
Moves to the  first/last cell of the current cell based on Arrow directions .</td></tr>
<tr>
<td>
ENTER</td><td>
Moves the active current cell to one cell down in the selection.</td></tr>
<tr>
<td>
SHIFT+ENTER</td><td>
Moves the active current cell to one cell up in the selection.</td></tr>
<tr>
<td>
TAB</td><td>
Moves the active current cell in one cell to the right of the selection.</td></tr>
<tr>
<td>
SHIFT+TAB</td><td>
Moves the active current cell in  one cell to the left of the selection.</td></tr>
<tr>
<td>
BACKSPACE</td><td>
Begins the edit operation for the active cell in the selection.</td></tr>
<tr>
<td>
CTRL+A</td><td>
Selects the entire worksheet.</td></tr>
<tr>
<td>
SHIFT+ARROW KEYS</td><td>
Extends the selection by one cell based on the arrow direction.</td></tr>
<tr>
<td>
CTRL+SHIFT+ARROW KEYS</td><td>
Extend the selection to the last cell in a row or column.</td></tr>
<tr>
<td>
SHIFT+HOME</td><td>
Extends the selection to the first column from the active cell.</td></tr>
<tr>
<td>
CTRL+SHIFT+HOME</td><td>
Extends the selection from the active cell to the first cell.</td></tr>
<tr>
<td>
SHIFT+PAGE DOWN</td><td>
Extends the selection down in a worksheet.</td></tr>
<tr>
<td>
SHIFT+PAGE UP</td><td>
Extends the selection up in a worksheet.</td></tr>
</table>


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.