---
layout: post
title: Overview of SfSpreadsheet | SfSpreadsheet | Syncfusion
description: This section provides an overview about SfSpreadsheet and it's important key features for Syncfusion Essential WPF.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Overview

The SfSpreadsheet is excel inspired control that allows you to create, edit, view and format the Microsoft Excel files without excel installed. It provides absolute ease of use UI experience with integrated ribbon to cover any possible business scenario. SfSpreadsheet comes with built-in calculation engine with support for 400+ most widely used formulas. 

## Key Features

* **Ribbon** – Ribbon integrated with organically enhanced UI experience.

* **Editing** **and** **Selection**- Interactive support for editing and cell selection in workbook.

* **Formulas** - Provides support for 400+ most widely used formulas which any business user needs and allows you to add, remove and edit the formulas like in excel.

* **Name** **Manager** – Supports the name ranges in the formulas. By using the name ranges, you can specify the name of the cell range, and then you can use it in the formula more easily without hassling of remembering cell locations.

* **Data** **validation** – Provides support to ensure the data integrity by enforcing end users to enter valid data into the cells and if entered data does not meet the specified criteria, and error message is displayed.

* **Floating** **Cells**- Provides support for floating cell mode that is when the text exceeds the length of the cell, it will float the text to the adjacent cell.

* **Merge** **Cells** - Merge two or more adjacent cells into a single cell and display the contents of one cell in the merged cell.

* **Conditional** **Formatting**- Provides support for excel compatible conditional formatting and allows you to apply formats to a cell or range of cells depending on the value of cells or formula that meet specific criteria. Also provides support to define and import the conditional formatting.  rules such as Data Bars, Icon Sets and Color Scales options which are used to visualize the data.

* **Cell** **Comments**- Supports comments that provide additional information about a cell such as what the value represents. And it would be useful if you want the end users to understand the data in the cells more deeply.

* **Hyperlinks** **and** **Bookmarks**- Provides support to import, create, and edit hyperlinks and bookmarks. The hyperlink is a convenient way to navigate or browse data within a worksheet or other worksheets in a workbook.

* **Undo**/**Redo** - Provides support to undo or redo the changes that you have made in the workbook.

* **Clipboard** **Operations** – Provides support for Cut/Copy/Paste Operations in Spreadsheet.

* **Fill** **Series** – Provides support to automatically fill cells with data that follows or completes a pattern.

* **Freeze** **panes** – Provides support to freeze rows/columns.

* **Resizing** **and** **Hiding** – Provides interactive support to resize or hide/unhide the rows and columns.

* **Charts**, **Pictures** **and** **Textboxes** - Provides support to import Charts, Pictures and Textboxes.

* **Sparklines** – Provides support to import Sparklines.

* **Outlines** - Provides support to group or ungroup rows and columns.

* **Workbook** **and** **Worksheet** **Protection**- Provides support to protect the worksheet and also supports to lock-down the structure and window of workbook, which enables you to prevent workbook from any structural change or from any change in size.

* **Conversion** – Provides support to export the workbook to PDF, HTML, Image and CSV.

* **Zooming** – Provides support to zoom in and zoom out of the worksheet view.

* **Localization** - Provides support to localize all the static text in a Ribbon and all dialogs to any desired language.

* **Supported file types** - Ability to import the different types of excel which are XLS, XLSX, XLSM, XLT, XLTX, CSV(Comma delimited) respectively.

## Choose between SfSpreadsheet and Spreadsheet control

WPF suite contains **SfSpreadsheet** and **Spreadsheet** control for viewing and editing the excel files. SfSpreadsheet is an alternate for Spreadsheet control which is marked as classic control. Hence it is recommended to use SfSpreadsheet which provides better performance and rich set features over Spreadsheet control. 

Below are the features that SfSpreadsheet have over Spreadsheet control,

<table>
<tr>
<th>
Feature</th><th>
SfSpreadsheet</th></tr>
<tr>
<td>
Scrolling performance</td><td>
Supports fast and fluid scrolling even if the excel has a huge set of data .Thus its  performance is high compared to Spreadsheet control.</td></tr>
<tr>
<td>
Copy Paste</td><td>
Supports various paste options similar to excel options like Paste, Formulas, Values, Formula and Source Formatting, Values and Source Formatting and Formatting alone. It also provides a good performance compared to Spreadsheet control.</td></tr>
<tr>
<td>
Undo/Redo</td><td>
Supports undo/redo functionalities similar to those achieved with Microsoft Office-type applications. This operation records the changes in the whole workbook while Spreadsheet Control records the changes in sheet level only.</td></tr>
<tr>
<td>
Formula calculation</td><td>
Provides support for 400+ most widely used formulas and uses Multi-threading concept So, the calculation speed is also high compared to Spreadsheet control.</td></tr>
<tr>
<td>
Floating Cells</td><td>
Provides support to float cell both in display and edit mode.</td></tr>
<tr>
<td>
Hyperlinks</td><td>
Provides support for Hyperlink feature which you can create hyperlink for existing files or web page and email addresses too.</td></tr>
<tr>
<td>
Conditional Formatting</td><td>
Provides support to define and import the conditional formatting rules such as Data Bars, Icon Sets and Color Scales options which are used to visualize the data.</td></tr>
<tr>
<td>
Data validation</td><td>
Provides support for validation for cross sheet references and list validation with formula/cell references compared to Spreadsheet control.</td></tr>
</table>

### Properties table

Below are the properties difference between SfSpreadsheet and Spreadsheet control,

<table>
<tr>
<th>
SfSpreadsheet</th><th>
Spreadsheet</th><th>
Description</th></tr>
<tr>
<td>
{{ '[ActiveGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_ActiveGrid)'| markdownify }}</td><td>
GridProperties->ActiveSpreadsheetGrid</td><td>
Gets the active SpreadsheetGrid</td></tr>
<tr>
<td>
{{'[IsCustomTabItemContextMenuEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_IsCustomTabItemContextMenuEnabled)'| markdownify }}</td><td>
TabStyleManager -> IsCustomTabItemContextMenuEnabled</td><td>
Gets or sets whether Custom ContextMenu is to be Enabled</td></tr>
<tr>
<td>
{{ '[ShowTabItemContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_ShowTabItemContextMenu)' | markdownify }}</td><td>
TabStyleManager -> ShowTabItemContextMenu</td><td>
Gets or sets whether TabItemContextMenu is to be displayed</td></tr>
<tr>
<td>
{{ '[TabItemContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_TabItemContextMenu)' | markdownify }}</td><td>
TabStyleManager ->TabItemContextMenu</td><td>
Gets or sets the ContextMenu Items for TabItem</td></tr>
<tr>
<td>
{{ '[ActiveSheet](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_ActiveSheet)' | markdownify }}</td><td>
ExcelProperties->Workbook->ActiveSheet</td><td>
Gets the Current ActiveSheet</td></tr>
<tr>
<td>
{{ '[Workbook](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_Workbook)' | markdownify }}</td><td>
ExcelProperties->Workbook</td><td>
</td></tr>
<tr>
<td>
{{ '[CurrentCellStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_CurrentCellStyle)' | markdownify }}</td><td>
GridProperties->CurrentCellStyle</td><td>
Gets the Style of the Current Cell</td></tr>
<tr>
<td>
{{ '[HistoryManager](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_HistoryManager)' | markdownify }}</td><td>
GridProperties.ActiveSpreadsheetGrid.Model.CommandStack</td><td>
Gets the command stack of the SfSpreadsheet.By default it has been enabled</td></tr>
<tr>
<td>
{{ '[SheetName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SheetName)' | markdownify }}</td><td>
GridProperties->CurrentSheetName</td><td>
Gets the tab sheet name</td></tr>
</table>
