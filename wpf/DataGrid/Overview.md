---
layout: post
title: About WPF DataGrid control | Syncfusion
description: Learn here all about introduction of Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# WPF DataGrid (SfDataGrid) Overview

The SfDataGrid (DataGrid) control for WPF is used to display collection of data in rows and columns. The SfDataGrid control includes editing, exporting and data shaping features (sorting, grouping, filtering and etc) that allows the end users to easily manage the data. 

Following are the key features of SfDataGrid control

* **Data binding** – Supports to bind different types of data sources.
* **Selection** – Support for row and also cell selection.
* **Editing** – Interactive support to edit with different column types.
* **Columns** – Support for various column types including unbound columns.
* **Sorting** – Interactive support to sort the data in SfDataGrid.
* **Grouping** – Interactive support to group the data in SfDataGrid.
* **Summaries** – Extensive support to show concise information about the individual data columns or groups of rows.
* **Filtering** – Interactive support for filtering data as like in Excel.
* **Data validation** – Support to validate the data on errors.
* **Data virtualization** – Support for different modes of data virtualization such as paging, incremental loading.
* **Master-Detail View** – Support to display relational data using hierarchies. 
* **Printing and Exporting** – Support to print and also export the data to Excel, PDF.
* **Styling** – Extensive support for customizing styles of cells and rows in SfDataGrid.
* **Stacked Headers** – Extensive support to show multiple headers called stacked headers.
* **Unbound rows** – Support to display unbound rows.
* **Touch support** – Complete support for resizing, drag-drop column, sorting, filtering, grouping and etc in touch devices.

## Choose between different Grid's

Syncfusion WPF suite comes up with following different Grid’s namely,

1. [GridControl](https://www.syncfusion.com/wpf-ui-controls/excel-like-grid)
2. [GridTreeControl](https://help.syncfusion.com/wpf/classic/gridtree/overview) and [SfTreeGrid](https://www.syncfusion.com/wpf-ui-controls/treegrid)
3. [GridDataControl](https://help.syncfusion.com/wpf/classic/griddata/overview) and [SfDataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid)

### GridControl

[GridControl](http://help.syncfusion.com/wpf/grid/overview) is designed based on the cell-oriented architecture that does not make any assumptions about the structure of the data and provides support for Excel-like features. This control can be used when the data is populated in on demand using virtualization or its internal storage. It is not possible to bind the data source directly. 

### GridTreeControl and SfTreeGrid

The [GridTreeControl](https://help.syncfusion.com/wpf/classic/gridtree/overview) and [SfTreeGrid](https://www.syncfusion.com/wpf-ui-controls/treegrid) control is a data-oriented control that displays self-relational data in a tree structure user interface like multicolumn treeview. The data can be loaded on demand. You can move items between parent nodes by using the built-in row drag-and-drop functionality. Its rich feature set includes editing with different column types, selection, and node selection with check boxes, sorting, and filtering.

### GridDataControl and SfDataGrid

The [GridDataControl](https://help.syncfusion.com/wpf/classic/griddata/overview) and [SfDataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) controls are used to display collection of data in rows and columns. These controls support the data binding directly. 

1. **SfDataGrid** - SfDataGrid is designed based on the WPF template-based architecture that provides support to customize the Grid easily and fully supports binding. 
2. **GridDataControl** - GridDataControl is designed based on the cell-oriented architecture of the Windows Forms Grid control that provides more control over cells and supports for Excel-like features. 

Both SfDataGrid and GridDataControl almost have the same set of features. But SfDataGrid control offers rich set of features over GridDataControl. When you want cell level customization and excel-like features you can use GridDataControl. When you want performance, customization features like styles & template features specific to WPF, you can use SfDataGrid control. Comparatively, the performance of SfDataGrid control is better than the GridDataControl.

N> `GridDataControl` is marked as classic control. In future, new features & enhancements will be added only in `SfDataGrid`. It recommended to use `SfDataGrid`.

You can see the list of some of the specific API difference between `GridDataControl` and `SfDataGrid` as follows:

<table>
<tr>
<th>GridDataControl</th>
<th>SfDataGrid</th>
<th>Description</th>
</tr>
<tr>
<td>AutoPopulateColumns</td>
<td>AutoGenerateColumns</td>
<td>To Generate the Columns</td></tr>
<tr>
<td>AllowEdit</td>
<td>AllowEditing</td>
<td>To Edit the GridCells</td>
</tr>
<tr>
<td>AllowGroup</td>
<td>AllowGrouping</td>
<td>To Group the Column header</td>
</tr>
<tr>
<td>AllowResizeColumns</td>
<td>AllowResizingColumns</td>
<td>To Resize the columns</td>
</tr>
<tr>
<td>AllowDragColumns</td>
<td>AllowDraggingColumns</td>
<td>To Drag the columns</td>
</tr>
<tr>
<td>AllowSort</td>
<td>AllowSorting</td>
<td>To Sort the columns</td>
</tr>
<tr>
<td>ShowFilters</td>
<td>AllowFiltering</td>
<td>To Show the Filters in a Grid</td>
</tr>
<tr>
<td>VisibleColumn</td>
<td>Column</td>
<td>To Specify the GridColumns</td>
</tr>
<tr>
<td>AllowExcelLikeResizing</td>
<td>AllowResizingHiddenColumns</td>
<td>To Allow Resizing on the Hidden Columns</td>
</tr>
<tr>
<td>ShowHoveringBackground</td>
<td>AllowRowHoverHighlighting</td>
<td>To show the Hovers for Highlighting rows.</td>
</tr>
<tr>
<td>EnableTriStateSorting</td>
<td>AllowTristateSorting</td>
<td>To allow Tri State Sorting</td>
</tr>
<tr>
<td>ExpandGroupsWhenGrouped</td>
<td>AutoExpandGroups</td>
<td>To Allow Auto Expand groups </td>
</tr>
<tr>
<td>AutoPopulateRelations</td>
<td>AutoGenerateRelations</td>
<td>To set an item source for child Grid.</td>
</tr>
<tr>
<td>SortColumns</td>
<td>SortColumnDescriptions</td>
<td>The column sorting based on the column descriptions that are given in a particular column.</td>
</tr>
<tr>
<td>ShowSortNumber</td>
<td>ShowSortNumbers</td>
<td>To Show the Sorted Numbers when sorting.</td>
</tr>
<tr>
<td>HideColumnsWhenGrouped</td>
<td>ShowColumnsWhenGrouped</td>
<td>To Show the Columns when grouped.</td>
</tr>
<tr>
<td>HighlightSelectionBackground</td>
<td>RowSelectionBrush</td>
<td>To give a color for RowSelection.</td>
</tr>
<tr>
<td>ListBoxSelectionMode</td>
<td>SelectionMode</td>
<td>To Specify the Selection Mode for a selection.</td>
</tr>
<tr>
<td>DefaultHeaderRowHight</td>
<td>HeaderRowHeight</td>
<td>Specifies the Header Row and Height.</td>
</tr>
<tr>
<td>SummaryRows</td>
<td>GroupSummaryRows</td>
<td>To Group the Summary row based on the Summary given in that row.</td>
</tr>
<tr>
<td>FrozenRows</td>
<td>FrozenRowsCount</td>
<td>The number of rows is freeze from Top.</td>
</tr>
<tr>
<td>FooterRows</td>
<td>FooterRowsCount</td>
<td>The number of rows is freeze from bottom.</td>
</tr>
<tr>
<td>FrozenColumns</td>
<td>FrozenColumnCount</td>
<td>The number of columns is freeze from left.</td>
</tr>
<tr>
<td>FooterColumns</td>
<td>FooterColumnCount</td>
<td>The number of columns is freeze from right.</td>
</tr>
</table>
You can see the list of rich set of features in `SfDataGrid` over `GridDataControl` as follows:

Rich set of features in `SfDataGrid` over `GridDataControl`.

<table>
<tr>
<th>Feature</th>
<th>Description</th>
</tr>
<tr>
<td>AutoRowHeight</td>
<td>
SfDataGrid enables fitting the height of the row based on its content on demand for all columns or certain columns 
by using {{ '[AutoRowHeight](http://help.syncfusion.com/wpf/sfdatagrid/row-height-customization#autorowheight)' | markdownify }}.
</td>
</tr>
<tr>
<td>
CellTemplate Support for all columns
</td>
<td>
SfDataGrid provides support for {{ '[CellTemplate](http://help.syncfusion.com/wpf/sfdatagrid/columns#celltemplate)' | markdownify }}. It is used to customize columns in display mode that present cells with DataTemplate.
</td>
</tr>
<tr>
<td>
IEditableObjectSupport
</td>
<td>
SfDataGrid supports to roll back the changes when you press <kbd>Esc</kbd> Key by implementing IEditableObject interface. 
For more information about IEditableObject refer {{ '[IEditableObject](http://help.syncfusion.com/wpf/sfdatagrid/editing)' | markdownify }}.
</td>
</tr>
<tr>
<td>
Incremental Loading
</td>
<td>
{{ '[IncrementalLoading](http://help.syncfusion.com/wpf/sfdatagrid/data-virtualization#incremental-loading)' | markdownify }} allows you to load a subset of data to 
SfDataGrid sequentially. It provides support for fast and fluid scrolling and loading a huge set of data.
</td>
</tr>
<tr>
<td>
Printing
</td>
<td>
The Printing feature in SfDataGrid is more flexible and customizable. It also provides a good performance when 
compared to GridDataControl.For more information about CustomPrinting, click {{ '[here](http://help.syncfusion.com/wpf/sfdatagrid/printing)' | markdownify }}.The PrintManager of SfDataGrid is designed to support different orientations, sizes, margins etc.
</td>
</tr>
<tr>
<td>
Exporting To Excel
</td>
<td>
SfDataGrid control provides support to Export data to Excel and returns an ExcelEngine that contains the exported 
workbook. SfDataGrid Exporting is faster than GridDataControl. It exports the content only to the excel sheet. It 
takes very less time to export the huge amounts of data. To know more about exporting in SfDataGrid, 
click {{ '[here](http://help.syncfusion.com/wpf/sfdatagrid/export-to-excel)' | markdownify }}.
</td>
</tr>
<tr>
<td>
Exporting To PDF
</td>
<td>
SfDataGrid control provides support for exporting the data into a PDF file. You can decide what are the contents 
is need to export in PDF file. You can export Grouping, Filtering, Summaries and DetailsView, StackedHeaders in to 
PDF file.To get more information about {{ '[ExportToPdf](http://help.syncfusion.com/wpf/sfdatagrid/export-to-pdf)' | markdownify }}.
</td>
</tr>
<tr>
<td>
FilterPopupPerformance
</td>
<td>
When you have a large amount of data, it takes time to load the Filter popup. Though, you are having lots of data, 
you can get better performance while loading Filter popup, by setting CanGenerateUniqueItems to False. To know more 
about FilterPopupPerformance, click {{ '[here](http://help.syncfusion.com/wpf/sfdatagrid/performance#filter-popup-performance)' | markdownify }}.
</td>
</tr>
<tr>
<td>
DataVirtualization
</td>
<td>
{{ '[DataVirtualization](http://help.syncfusion.com/wpf/sfdatagrid/data-virtualization)' | markdownify }} is a term that achieves Virtualization 
for the actual data objects that are bound to the DataGrid. For small collection of basic data objects, the memory consumption is not significant. However for large collections, the memory consumption becomes very significant.
</td>
</tr>
</table>


