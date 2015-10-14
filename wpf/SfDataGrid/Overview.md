---
layout: post
title: Overview | SfDataGrid | WPF | Syncfusion
description: overview
platform: wpf
control: SfDataGrid
documentation: ug
---

# Overview

The SfDataGrid control for WPF is the most advanced DataGrid control that delivers unmatched performance and flexibility. SfDataGrid assists you to create entirely customizable and highly interactive features used to display and manipulate the huge amount of data. It displays data in tabular view and it has built-in touch support.

The following lists the key features of DataGrid control.

* DataBinding - Supports to bind with different types of data sources.
* Master-Detail View - Interactive support to display related data using hierarchies.
* Editing - Interactive support to edit with different cell types.
* DataValdiataion	 - Interactive support to validate data on errors.
* Selection and Key Navigation Support - Interactive support to select the row by mouse and touch.
* Grouping - Interactive support to group the columns.
* Summaries - Extensive support to show concise information about the individual data columns or groups of rows.
* Filtering - Support to filter the data.
* Sorting - Interactive support to Sort the columns in Ascending or Descending order.
* Paging - Support to perform Paging on the data.
* Column Resizing Support - Interactive support to resize the columns at Execute time.
* Column Freezing - Supports to freeze the columns in horizontal scrolling.
* Unbound Column Support - Extensive support for unbound columns.
* Columns Drag and Drop Support - Interactive support to reorder the columns by dragging.
* Stacked Headers - Extensive support to show multiple headers called stacked headers.
* Printing	- Interactive support to print the displayed data.
* Exporting - Interactive support to export the DataGrid to excel and PDF
* Styles and Templates - Extensive support to customize every control inside the DataGrid.

## Choose between Different Grids 


This section explains different Grids that are provided and used in your application. The following are the different Grid controls to display data with unmatched performance.

* GridControl
* GridTreeControl
* DataGrid Control

### GridControl

GridControl is designed based on the cell-oriented architecture that does not make any assumptions about the structure of the data and support for Excel-like features. You can use this control when you need to populate the data on demand using virtualization or you can use its internal storage. In GridControl, you cannot directly bind the data source.

### GridTreeControl

The GridTreeControl is a Grid that displays self-referencing lists in a multicolumn tree format. The data is loaded on demand so that large lists are quickly displayed. You can use this control when you want to display data in Grid like Tree.

### DataGrid

DataGrid is the control that displays data in tabular view. This supports data binding directly. You can use this control when you want to populate data using ObservableCollections, ADO.NET DataTables, LINQ to SQL and ADO.NET. There are two types of DataGrid as follows.

* GridDataControl
* SfDataGrid

#### GridDataControl

GridDataControl is designed based on the cell-oriented architecture of the Windows Forms Grid control that provides more control over cells and supports for Excel-like features. 

#### SfDataGrid

SfDataGrid is designed based on the WPF template-based architecture that provides support to customize the Grid easily and fully supports binding.

Both SfDataGrid and GridDataControl almost have the same set of features. But SfDataGrid has some features that are richer than GridDataControl. When you want cell level customization and excel-like features you can use GridDataControl. When you want customization like styles and template features, specific to WPF, you can use SfDataGrid.

Comparatively, the performance of SfDataGrid control is better than the GridDataControl. You can see the list of some of the specific API difference between GridDataControl and SfDataGrid as follows:

Property Table

<table>
<tr>
<th>
GridDataControl</th><th>
SfDataGrid</th><th>
Description</th></tr>
<tr>
<td>
AutoPopulateColumns</td><td>
AutoGenarateColumns</td><td>
To Generate the Columns</td></tr>
<tr>
<td>
AllowEdit</td><td>
AllowEditing</td><td>
To Edit the GridCells</td></tr>
<tr>
<td>
AllowGroup</td><td>
AllowGrouping</td><td>
To Group the Column header</td></tr>
<tr>
<td>
AllowResizeColumns</td><td>
AllowResizingColumns</td><td>
To Resize the columns</td></tr>
<tr>
<td>
AllowDragColumns</td><td>
AllowDraggingColumns</td><td>
To Drag the columns</td></tr>
<tr>
<td>
AllowSort</td><td>
AllowSorting</td><td>
To Sort the columns</td></tr>
<tr>
<td>
ShowFilters</td><td>
AllowFiltering</td><td>
To Show the Filters in a Grid</td></tr>
<tr>
<td>
VisibleColumn</td><td>
Column</td><td>
To Specify the GridColumns</td></tr>
<tr>
<td>
AllowExcelLikeResizing</td><td>
AllowResizingHiddenColumns</td><td>
To Allow Resizing on the Hidden Columns</td></tr>
<tr>
<td>
ShowHoveringBackground</td><td>
AllowRowHoverHighlilgting</td><td>
To show the Hovers for Highlighting rows.</td></tr>
<tr>
<td>
EnableTriStateSorting</td><td>
AllowTristateSorting</td><td>
To allow Tri State Sorting</td></tr>
<tr>
<td>
ExpandGroupsWhenGrouped</td><td>
AutoExpandGroups</td><td>
To Allow Auto Expand groups </td></tr>
<tr>
<td>
AutoPopulateRelations</td><td>
AutoGenerateRelations</td><td>
To set an item source for child Grid.</td></tr>
<tr>
<td>
SortColumns</td><td>
SortColumnDescriptions</td><td>
The column sorting based on the column descriptions that are given in a particular column.</td></tr>
<tr>
<td>
ShowSortNumber</td><td>
ShowSortNumbers</td><td>
To Show the Sorted Numbers when sorting.</td></tr>
<tr>
<td>
HideColumnsWhenGrouped</td><td>
ShowColumnswhenGrouped</td><td>
To Show the Columns when grouped.</td></tr>
<tr>
<td>
HighlightSelectionBackground</td><td>
RowSelectionBrush</td><td>
To give a color for RowSelection.</td></tr>
<tr>
<td>
ListBoxSelectionMode</td><td>
SelectionMode</td><td>
To Specify the Selection Mode for a selection.</td></tr>
<tr>
<td>
DefaultHeaderRowHight</td><td>
HeaderRowHeight</td><td>
Specifies the Header Row and Height.</td></tr>
<tr>
<td>
SummaryRows</td><td>
GroupSummaryRows</td><td>
To Group the Summary row based on the Summary given in that row.</td></tr>
<tr>
<td>
FrozenRows</td><td>
FrozenRowsCount</td><td>
The number of rows is freeze from Top.</td></tr>
<tr>
<td>
FooterRows</td><td>
FooterRowsCount</td><td>
The number of rows is freeze from bottom.</td></tr>
<tr>
<td>
FrozenColumns</td><td>
FrozenColumnCount</td><td>
The number of columns is freeze from left.</td></tr>
<tr>
<td>
FooterColumns</td><td>
FooterColumnCount</td><td>
The number of columns is freeze from right.</td></tr>
</table>
You can see the list of rich set of features in SfDataGrid over GridDataControl as follows:

Rich set of features in SfDataGrid over GridDataControl

<table>
<tr>
<th>
Feature</th><th>
Description</th></tr>
<tr>
<td>
AutoRowHeight</td><td>
SfDataGrid enables fitting the height of the row based on its content on demand for all columns or certain columns 
by using {{ '[AutoRowHeight](http://docs.syncfusion.com/wpf/sfdatagrid/row-height-customization#autorowheight)' | markdownify }}.</td></tr>
<tr>
<td>
CellTemplate Support for all columns</td><td>
SfDataGrid provides support for {{ '[CellTemplate](http://docs.syncfusion.com/wpf/sfdatagrid/columns#celltemplate)' | markdownify }}. It is used to customize columns in display mode that present cells with datatemplate.</td></tr>
<tr>
<td>
IEditableObjectSupport</td><td>
SfDataGrid supports to rollback the changes when you press Esc Key by implementing IEditableObject interface. 
For more information about IEditableObject refer {{ '[IEditableObject](http://docs.syncfusion.com/wpf)' | markdownify }}.</td></tr>
<tr>
<td>
Incremental Loading</td><td>
{{ '[IncrementalLoading](http://docs.syncfusion.com/wpf)' | markdownify }} allows you to load a subset of data to 
SfDataGrid sequentially. It provides support for fast and fluid scrolling and loading a huge set of data.</td></tr>
<tr>
<td>
Printing</td><td>
The Printing feature in SfDataGrid is more flexible and customizable. It also provides a good performance when 
compared to GridDataControl.For more information about CustomPrinting, click {{ '[here](http://docs.syncfusion.com/wpf)' | markdownify }}.The PrintManager of SfDataGrid is designed to support different orientations, sizes, margins etc.</td></tr>
<tr>
<td>
Exporting To Excel</td><td>
SfDataGrid control provides support to Export data to Excel and returns an ExcelEngine that contains the exported 
workbook. SfDataGrid Exporting is faster than GridDataControl. It exports the content only to the excel sheet. It 
takes very less time to export the huge amounts of data. To know more about exporting in SfDataGrid, 
click {{ '[here](http://docs.syncfusion.com/wpf/sfdatagrid/exporting#export-to-excel)' | markdownify }}.</td></tr>
<tr>
<td>
Exporting To Pdf</td><td>
SfDataGrid control provides support for exporting the data into a pdf file. You can decides what are the contents 
is need to export in pdf file. You can export Grouping, Filtering, Summaries and DetailsView, StackedHeaders in to 
pdf file.To get more information about {{ '[ExportToPdf](http://docs.syncfusion.com/wpf/sfdatagrid/exporting#export-to-pdf)' | markdownify }}.</td></tr>
<tr>
<td>
FilterPopupPerformance</td><td>
When you have a large amount of data, it takes time to load the Filter popup. Though, you are having lots of data, 
you can get better performace while loading Filter popup, by setting CanGenerateUniqueItems to False. To know more 
about FilterPopupPerformance, click {{ '[here](http://docs.syncfusion.com/wpf/sfdatagrid/performance#filter-popup-performance)' | markdownify }}.</td></tr>
<tr>
<td>
DataVirtualiazation</td><td>
{{ '[DataVirtualization](http://docs.syncfusion.com/wpf/sfdatagrid/data-virtualization)' | markdownify }} is a term that achieves Virtualization 
for the actual data objects that are bound to the DataGrid. For small collection of basic data objects, the memory consumption is not significant. However for large collections, the memory consumption becomes very significant.</td></tr>
</table>


