---
layout: post
title: Helpers in WPF DataGrid control | Syncfusion
description: Learn about Helpers support in Syncfusion WPF DataGrid (SfDataGrid) control and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Helpers in WPF DataGrid (SfDataGrid)

## IndexResolver

SfDataGrid has GridIndexResolver static class present in Syncfusion.UI.Xaml.Grid namespace that has some extension methods used to Resolve from row or column index to record or visible column index and vice versa. 

## Example: You can find the record index from row index using ResolveToRecordIndex method.

Prototype Table

<table>
<tr>
<th>
ProtoType</th><th>
Description</th></tr>
<tr>
<td>
ResolveToRecordIndex(int rowIndex)</td><td>
Resolves Record index from the RowIndex. When RowIndex does not find any records it returns -1. RecordIndex denotes the index of Record in SfDataGrid.View.Records</td></tr>
<tr>
<td>
ResolveToRowIndex(int recordIndex)</td><td>
Resolves RowIndex from the record index associated with SfDataGrid.View.Records.When record index is lesser than 0 it returns the -1.</td></tr>
<tr>
<td>
ResolveToRowIndex(object recordItem)</td><td>
Resolves row index from the record associated with SfDataGrid.View.Records.When the given record is not available in the collection it returns -1.</td></tr>
<tr>
<td>
ResolveStartIndexOfGroup(Group group)</td><td>
Resolves the start index of group in DataGrid associated with SfDataGrid.View.Groups.When there is no group in DataGrid it returns -1.</td></tr>
<tr>
<td>
ResolveToTableSummaryIndex(int rowIndex)</td><td>
Resolves TableSummaryIndex associated with SfDataGrid.View.Records.TableSummaries. When the row is not a TableSummaryRow, it returns -1.</td></tr>
<tr>
<td>
ResolveToGridVisibleColumnIndex(int visibleColumnIndex)</td><td>
Resolves the GridColumn index from the visible column index. It excludes the RowHeader and IndentColumn.</td></tr>
<tr>
<td>
ResolveStartIndexBasedOnPosition()</td><td>
Resolves the start index based on position. It includes the stacked header also. By default it returns 0.</td></tr>
<tr>
<td>
ResolveToScrollColumnIndex(int gridColumnIndex)</td><td>
Resolves column index from the Grid column index associated with SfDataGrid.Columns.It includes the IndentColumn and RowHeader also.</td></tr>
<tr>
<td>
ResolveToStartColumnIndex()</td><td>
Returns start column index of the VisibleColumn. </td></tr>
<tr>
<td>
GetGridDetailsViewRowIndex(DetailsViewDataGrid detailsViewDataGrid)</td><td>
Returns the RowIndex of DetailsViewGrid. You can pass the DetailsViewDataGrid as argument. When the DetailsView is not found it returns the -1.</td></tr>
<tr>
<td>
GetGridDetailsViewRecord(DetailsViewDataGrid detailsViewDataGrid)</td><td>
Returns the DetailsView record. You can pass the DetailsViewDataGrid.When there is no item it returns null value.</td></tr>
<tr>
<td>
GetTableSummaryCount(TableSummaryRowPosition position)</td><td>
Returns the TableSummary count from TableSummaryRowPosition.Position. </td></tr>
<tr>
<td>
GetHeaderIndex()</td><td>
Returns the header row index.</td></tr>
<tr>
<td>
IsInDetailsViewIndex(int rowIndex)</td><td>
Decides whether the given row index is DetailsView index or not.</td></tr>
<tr>
<td>
IsAddNewIndex(int rowIndex)</td><td>
Decides whether the given row index is AddNewRow index or not.</td></tr>
<tr>
<td>
IsTableSummaryIndex(int rowIndex)</td><td>
Decides whether the given row index is TableSummary index or not.</td></tr>
<tr>
<td>
IsHeaderTableSummaryRow(int rowIndex)</td><td>
Decides whether the given row index is HeaderTableSummaryRow or not.</td></tr>
</table>


## Dispose

The method is associated with relinquishes memory and clears all references associated with SfDataGrid. When you call this method, it releases all the reference for SfDataGrid. So the memory it is occupying using the DataGrid is reclaimed. You have to call SfDataGrid.Dispose method to release the memory.



