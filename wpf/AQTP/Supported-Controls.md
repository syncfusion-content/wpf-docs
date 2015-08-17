---
layout: post
title: Supported-Controls
description: supported controls
platform: wpf
control: QTP
documentation: ug
---

## Supported Controls

### Essential Grid

This section covers the supported properties and methods in Essential Grid. 

## Properties 

_Properties Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td><td>
{{ '**Reference**' | markdownify }}</td></tr>
<tr>
<td>
Int RowCount</td><td>
Gets the RowCount of the Grid.</td><td>
N/A</td><td>
int</td><td>
N/A</td></tr>
<tr>
<td>
Int ColCount</td><td>
Gets the ColCount of the Grid.</td><td>
N/A</td><td>
int</td><td>
N/A</td></tr>
</table>

## Methods

_Methods Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<th>
bool SetCurrentCell(int row, int col)</th><th>
Sets the CurrentCell based on Row and Column parameters.</th><th>
 int row, int col</th><th>
bool </th></tr>
<tr>
<th>
bool SetChkBoxCell(int row, int col, bool val)</th><th>
Sets the CheckBoxCell value by using Row, Column and Value parameters.</th><th>
int row, int col, bool val</th><th>
bool</th></tr>
<tr>
<th>
bool IsFormulaCell(int row, int col)</th><th>
Finds whether the cell is a formula cell.</th><th>
int row, int col</th><th>
bool</th></tr>
<tr>
<th>
int GetSelectedRowIndex()</th><th>
Gets the selected row from Grid.</th><th>
NA</th><th>
int</th></tr>
<tr>
<th>
int GetSelectedColIndex()</th><th>
Gets the selected Column from Grid.</th><th>
NA</th><th>
int</th></tr>
<tr>
<th>
void SetCellData(int row, int col, string val)</th><th>
Sets the cell data by using Row, Column and Value parameters.</th><th>
int row, int col, string val</th><th>
void</th></tr>
<tr>
<th>
void InsertColumns(int col, int count)</th><th>
Inserts the column by using Count and Target parameters.</th><th>
int col, int count</th><th>
void</th></tr>
<tr>
<th>
void InsertRows(int row, int count)</th><th>
Inserts the row by using Count and Target parameters.</th><th>
int row, int count</th><th>
void</th></tr>
<tr>
<th>
void RemoveColumns(int col, int count)</th><th>
Removes the columns by using Row parameter.</th><th>
int col, int count</th><th>
void</th></tr>
<tr>
<th>
void RemoveRows(int row, int count)</th><th>
Removes the Rows by using Row parameter.</th><th>
int row, int count</th><th>
void</th></tr>
<tr>
<th>
void MoveRows(int removeAtRowIndex, int count, int insertAtRowIndex)</th><th>
Moves the row by using From and Target parameters.</th><th>
int removeAtRowIndex, int count, int insertAtRowIndex</th><th>
void</th></tr>
<tr>
<th>
void MoveColumns(int removeAtColIndex, int count, int insertAtColIndex)</th><th>
Moves the column by using From and Target parameters.</th><th>
int removeAtColIndex, int count, int insertAtColIndex</th><th>
void</th></tr>
<tr>
<th>
void CellClick(int row, int col)</th><th>
Performs a click action to the cell by using row and column parameters.</th><th>
int row, int col</th><th>
void</th></tr>
<tr>
<th>
void ResizeColumns(int fromColumn, int to, int width)</th><th>
Resizes the column by using column parameter.</th><th>
int fromColumn, int to, int width</th><th>
void</th></tr>
<tr>
<th>
void ResizeRows(int fromRow, int to, int height)</th><th>
Resizes the row by using row parameter.</th><th>
int fromRow, int to, int height</th><th>
void</th></tr>
<tr>
<th>
void SetScrollPosition( int vScrollPosition,  int hScrollPosition)</th><th>
Sets the scroll position based on vScrollPosition and hScrollPosition parameters.</th><th>
int vScrollPosition,  int hScrollPosition</th><th>
void</th></tr>
<tr>
<th>
void SelectRange(int topRow, int leftCol, int bottomRow, int rightCol)</th><th>
SelectRange by using Top,Left,Right and Bottom parameters.</th><th>
int topRow, int leftCol, int bottomRow, int rightCol</th><th>
void</th></tr>
<tr>
<th>
void ScrollInToView(int row, int col)</th><th>
Scrolls the cell into view, based on Row and Column parameters.</th><th>
int row, int col</th><th>
void</th></tr>
<tr>
<th>
void HideRows(int fromRow, int to)</th><th>
Hides rows based on Row parameter.</th><th>
int fromRow, int to</th><th>
void</th></tr>
<tr>
<th>
void HideCols(int fromCol, int to)</th><th>
Hides columns based on Column parameter.</th><th>
int fromCol, int to</th><th>
void</th></tr>
<tr>
<th>
void ShowHiddenRows(int fromRow, int to)</th><th>
Shows the hidden Rows in Grid.</th><th>
int fromRow, int to</th><th>
void</th></tr>
<tr>
<th>
void ShowHiddenCols(int fromCol, int to)</th><th>
Shows the hidden Columns in Grid.</th><th>
int fromCol, int to</th><th>
void</th></tr>
<tr>
<th>
string GetCellType(int row, int col)</th><th>
Gets the CellType as a string value based on Row and Column parameters.</th><th>
int row, int col</th><th>
string</th></tr>
<tr>
<th>
string GetCellBackground(int row, int col)</th><th>
Gets the background color as string value based on Row and Column parameter.</th><th>
int row, int col</th><th>
string</th></tr>
<tr>
<th>
string GetCellForeground(int row, int col)</th><th>
Gets the foreground color as string value, based on Row and Column parameters.</th><th>
int row, int col</th><th>
string</th></tr>
<tr>
<th>
string GetFromattedText(int row, int col)</th><th>
Gets the formatted text as string value based on Row and Column parameters.</th><th>
int row, int col</th><th>
string</th></tr>
</table>

### Essential Chart

### Methods

_Methods Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<th>
SetScrollPosition</th><th>
To record the scrolling of Chart Area.</th><th>
(int area, int axis, double zoomposition) </th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ChartSegmentDragging</th><th>
Denotes the Segment that is dragged.</th><th>
(int series, int segment)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ChartZoomedIn</th><th>
To record the Zoom in of Chart Area.</th><th>
(int areaindex, double xzoomFactor, double yzoomFactor)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ChartZoomedOut</th><th>
To record the zoom out Chart Area.</th><th>
(int areaindex, double xzoomFactor, double yzoomFactor)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ChartZoomReset</th><th>
To record the Chart Area reset.</th><th>
(int areaindex, double xzoomFactor, double yzoomFactor)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ChartPanning</th><th>
To record the panning of Chart Area.</th><th>
(int area, double zoomXPosition, double zoomYPosition)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
LegendLocationChanged</th><th>
To record the change in location of Legend.</th><th>
(double dockX, double dockY)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ContextMenuOpening</th><th>
To record the ContextMenu support.</th><th>
(double isOpen)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
InteractiveCursorLocationChanged</th><th>
To record the Interactive Cursor.</th><th>
(double offsetX, double offsetY, int areaindex)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
</table>

### Essential SfDataGrid

### Properties

_Properties Table_

<table>
<tr>
<td>
{{ '**Method**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Parameters**' | markdownify }}</td><td>
{{ '**Return Type**' | markdownify }}</td></tr>
<tr>
<td>
Int RowCount</td><td>
Gets the RowCount of the SfDataGrid.</td><td>
N/A</td><td>
int</td><td>
N/A</td></tr>
<tr>
<td>
Int ColumnCount</td><td>
Gets the ColCount of the SfDataGrid.</td><td>
N/A</td><td>
int</td><td>
N/A</td></tr>
</table>

### Methods

_Methods Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<th>
void SetCurrentCell(int row,int col);</th><th>
To Set the CurrentCell.</th><th>
 int row, int col</th><th>
void</th></tr>
<tr>
<th>
void GroupColumn(strin columnName);</th><th>
To Group the Column.</th><th>
String columnName</th><th>
void</th></tr>
<tr>
<th>
void UnGroupColumn(string columnName);</th><th>
To Un Group the column.</th><th>
String columnName</th><th>
void</th></tr>
<tr>
<th>
void SortColumn(string columnName,string state);</th><th>
To Sort the column.</th><th>
string columnName,string state</th><th>
Void</th></tr>
<tr>
<th>
void BeginEdit(int row,int col);</th><th>
To Enter the Edit mode for particular cell.</th><th>
int row,int col</th><th>
Void</th></tr>
<tr>
<th>
void EndEdit();</th><th>
To EndEdit the current cell.</th><th>
NA</th><th>
void</th></tr>
</table>

### Essential SfMultiColumnDropDownControl

### Methods

_Methods Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<th>
void SetSelectedIndex(int index);</th><th>
To set the SelectedIndex from the Popup.</th><th>
 Int index</th><th>
void</th></tr>
<tr>
<th>
void ShowPopup();</th><th>
To open the Popup.</th><th>
NA</th><th>
void</th></tr>
<tr>
<th>
void HidePopup();</th><th>
To Close the Popup.</th><th>
NA</th><th>
void</th></tr>
</table>

### Essential SfDataPager

### Methods

_Methods Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<th>
void SetCurrentPage(int pageIndex</th><th>
To set the current page in SfDataPager.</th><th>
 Int pageIndex</th><th>
void</th></tr>
</table>


