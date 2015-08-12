---
layout: post
title: Supported-Controls
description: supported controls
platform: wpf
control: QTP
documentation: ug
---

# Supported Controls

## Essential Grid

This section covers the supported properties and methods in Essential Grid. 

### Properties 

_Properties Table_

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Reference**' | markdownify }}</th></tr>
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
<td>
bool SetCurrentCell(int row, int col)</td><td>
Sets the CurrentCell based on Row and Column parameters.</td><td>
 int row, int col</td><td>
bool </td></tr>
<tr>
<td>
bool SetChkBoxCell(int row, int col, bool val)</td><td>
Sets the CheckBoxCell value by using Row, Column and Value parameters.</td><td>
int row, int col, bool val</td><td>
bool</td></tr>
<tr>
<td>
bool IsFormulaCell(int row, int col)</td><td>
Finds whether the cell is a formula cell.</td><td>
int row, int col</td><td>
bool</td></tr>
<tr>
<td>
int GetSelectedRowIndex()</td><td>
Gets the selected row from Grid.</td><td>
NA</td><td>
int</td></tr>
<tr>
<td>
int GetSelectedColIndex()</td><td>
Gets the selected Column from Grid.</td><td>
NA</td><td>
int</td></tr>
<tr>
<td>
void SetCellData(int row, int col, string val)</td><td>
Sets the cell data by using Row, Column and Value parameters.</td><td>
int row, int col, string val</td><td>
void</td></tr>
<tr>
<td>
void InsertColumns(int col, int count)</td><td>
Inserts the column by using Count and Target parameters.</td><td>
int col, int count</td><td>
void</td></tr>
<tr>
<td>
void InsertRows(int row, int count)</td><td>
Inserts the row by using Count and Target parameters.</td><td>
int row, int count</td><td>
void</td></tr>
<tr>
<td>
void RemoveColumns(int col, int count)</td><td>
Removes the columns by using Row parameter.</td><td>
int col, int count</td><td>
void</td></tr>
<tr>
<td>
void RemoveRows(int row, int count)</td><td>
Removes the Rows by using Row parameter.</td><td>
int row, int count</td><td>
void</td></tr>
<tr>
<td>
void MoveRows(int removeAtRowIndex, int count, int insertAtRowIndex)</td><td>
Moves the row by using From and Target parameters.</td><td>
int removeAtRowIndex, int count, int insertAtRowIndex</td><td>
void</td></tr>
<tr>
<td>
void MoveColumns(int removeAtColIndex, int count, int insertAtColIndex)</td><td>
Moves the column by using From and Target parameters.</td><td>
int removeAtColIndex, int count, int insertAtColIndex</td><td>
void</td></tr>
<tr>
<td>
void Cel
lClick(int row, int col)</td><td>
Performs a click action to the cell by using row and column parameters.</td><td>
int row, int col</td><td>
void</td></tr>
<tr>
<td>
void ResizeColumns(int fromColumn, int to, int width)</td><td>
Resizes the column by using column parameter.</td><td>
int fromColumn, int to, int width</td><td>
void</td></tr>
<tr>
<td>
void ResizeRows(int fromRow, int to, int height)</td><td>
Resizes the row by using row parameter.</td><td>
int fromRow, int to, int height</td><td>
void</td></tr>
<tr>
<td>
void SetScrollPosition( int vScrollPosition,  int hScrollPosition)</td><td>
Sets the scroll position based on vScrollPosition and hScrollPosition parameters.</td><td>
int vScrollPosition,  int hScrollPosition</td><td>
void</td></tr>
<tr>
<td>
void SelectRange(int topRow, int leftCol, int bottomRow, int rightCol)</td><td>
SelectRange by using Top,Left,Right and Bottom parameters.</td><td>
int topRow, int leftCol, int bottomRow, int rightCol</td><td>
void</td></tr>
<tr>
<td>
void ScrollInToView(int row, int col)</td><td>
Scrolls the cell into view, based on Row and Column parameters.</td><td>
int row, int col</td><td>
void</td></tr>
<tr>
<td>
void HideRows(int fromRow, int to)</td><td>
Hides rows based on Row parameter.</td><td>
int fromRow, int to</td><td>
void</td></tr>
<tr>
<td>
void HideCols(int fromCol, int to)</td><td>
Hides columns based on Column parameter.</td><td>
int fromCol, int to</td><td>
void</td></tr>
<tr>
<td>
void ShowHiddenRows(int fromRow, int to)</td><td>
Shows the hidden Rows in Grid.</td><td>
int fromRow, int to</td><td>
void</td></tr>
<tr>
<td>
void ShowHiddenCols(int fromCol, int to)</td><td>
Shows the hidden Columns in Grid.</td><td>
int fromCol, int to</td><td>
void</td></tr>
<tr>
<td>
string GetCellType(int row, int col)</td><td>
Gets the CellType as a string value based on Row and Column parameters.</td><td>
int row, int col</td><td>
string</td></tr>
<tr>
<td>
string GetCellBackground(int row, int col)</td><td>
Gets the background color as string value based on Row and Column parameter.</td><td>
int row, int col</td><td>
string</td></tr>
<tr>
<td>
string GetCellForeground(int row, int col)</td><td>
Gets the foreground color as string value, based on Row and Column parameters.</td><td>
int row, int col</td><td>
string</td></tr>
<tr>
<td>
string GetFromattedText(int row, int col)</td><td>
Gets the formatted text as string value based on Row and Column parameters.</td><td>
int row, int col</td><td>
string</td></tr>
</table>

## Essential Chart

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
<td>
SetScrollPosition</td><td>
To record the scrolling of Chart Area.</td><td>
(int area, int axis, double zoomposition) </td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ChartSegmentDragging</td><td>
Denotes the Segment that is dragged.</td><td>
(int series, int segment)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ChartZoomedIn</td><td>
To record the Zoom in of Chart Area.</td><td>
(int areaindex, double xzoomFactor, double yzoomFactor)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ChartZoomedOut</td><td>
To record the zoom out Chart Area.</td><td>
(int areaindex, double xzoomFactor, double yzoomFactor)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ChartZoomReset</td><td>
To record the Chart Area reset.</td><td>
(int areaindex, double xzoomFactor, double yzoomFactor)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ChartPanning</td><td>
To record the panning of Chart Area.</td><td>
(int area, double zoomXPosition, double zoomYPosition)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
LegendLocationChanged</td><td>
To record the change in location of Legend.</td><td>
(double dockX, double dockY)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ContextMenuOpening</td><td>
To record the ContextMenu support.</td><td>
(double isOpen)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
InteractiveCursorLocationChanged</td><td>
To record the Interactive Cursor.</td><td>
(double offsetX, double offsetY, int areaindex)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
</table>

## Essential SfDataGrid

### Properties

_Properties Table_

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
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
<td>
void SetCurrentCell(int row,int col);</td><td>
To Set the CurrentCell.</td><td>
 int row, int col</td><td>
void</td></tr>
<tr>
<td>
void GroupColumn(strin columnName);</td><td>
To Group the Column.</td><td>
String columnName</td><td>
void</td></tr>
<tr>
<td>
void UnGroupColumn(string columnName);</td><td>
To Un Group the column.</td><td>
String columnName</td><td>
void</td></tr>
<tr>
<td>
void SortColumn(string columnName,string state);</td><td>
To Sort the column.</td><td>
string columnName,string state</td><td>
Void</td></tr>
<tr>
<td>
void BeginEdit(int row,int col);</td><td>
To Enter the Edit mode for particular cell.</td><td>
int row,int col</td><td>
Void</td></tr>
<tr>
<td>
void EndEdit();</td><td>
To EndEdit the current cell.</td><td>
NA</td><td>
void</td></tr>
</table>

## Essential SfMultiColumnDropDownControl

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
<td>
void SetSelectedIndex(int index);</td><td>
To set the SelectedIndex from the Popup.</td><td>
 Int index</td><td>
void</td></tr>
<tr>
<td>
void ShowPopup();</td><td>
To open the Popup.</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
void HidePopup();</td><td>
To Close the Popup.</td><td>
NA</td><td>
void</td></tr>
</table>

## Essential SfDataPager

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
<td>
void SetCurrentPage(int pageIndex</td><td>
To set the current page in SfDataPager.</td><td>
 Int pageIndex</td><td>
void</td></tr>
</table>


