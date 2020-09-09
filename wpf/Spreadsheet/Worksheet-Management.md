---
layout: post
title: Worksheet Management in WPF Spreadsheet | Syncfusion
description: This document explains how to perform worksheet related operations(insert, delete, hide, etc.) in Spreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Worksheet Management
This section explains about the operations that are performed with the worksheet.

## Insert and Delete worksheet

SfSpreadsheet provides support to insert and delete the worksheets in a workbook.

{% tabs %}
{% highlight c# %}
//Insert Sheet
 spreadsheet.AddSheet();
	
//Insert sheet with name
 spreadsheet.AddSheet("Sheet4", 3);

//Delete Sheet
spreadsheet.RemoveSheet("Sheet2");
{% endhighlight %}
{% endtabs %}

## Hide and Unhide worksheets

SfSpreadsheet provides support to hide and unhide the worksheets in a workbook.

{% tabs %}
{% highlight c# %}
//Hide Sheet
spreadsheet.HideSheet("Sheet 2");

//Unhide Sheet
spreadsheet.UnhideSheet("Sheet 2");
{% endhighlight %}
{% endtabs %}

## Hide or unhide sheet tabs

Spreadsheet provides support to hide and unhide the all worksheet tabs in the workbook using the [ShowSheetTabs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_ShowSheetTabs) property. The Default value is `true`.

{% tabs %}
{% highlight c# %}

private void SpreadsheetControl_Loaded(object sender, RoutedEventArgs e)
{
    spreadsheetControl.ShowSheetTabs = false;
}

{% endhighlight %}
{% highlight XAML %}

<syncfusion:SfSpreadsheet x:Name="spreadsheetControl" ShowSheetTabs ="False" />

{% endhighlight %}
{% endtabs %}

## Rename a worksheet

SfSpreadsheet provides support to rename a worksheet in the workbook by using [RenameSheet](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~RenameSheet.html) method. After invoking this method, the sheet tab enters into editing mode and now the users can change the name of the sheet in the tab. 

{% tabs %}
{% highlight c# %}
//Rename sheet
spreadsheet.RenameSheet("Sheet1");
{% endhighlight %}
{% endtabs %}

### Rename a worksheet programmatically

SfSpreadsheet provides support to rename a worksheet in the workbook programmatically by using [RenameSheet](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_RenameSheet_System_String_System_String_) method.

{% tabs %}
{% highlight c# %}
//To Rename a sheet programmatically
spreadsheet.RenameSheet("ExistingSheetName", "NewSheetName");
{% endhighlight %}
{% endtabs %}


## Worksheet Protection

### Protecting a worksheet

SfSpreadsheet provides support to protect the worksheet with or without password. This helps to prevent a user from modifying the contents of the worksheet. The protection of worksheet can be done with [ExcelSheetProtection](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.ExcelSheetProtection.html) options also.

The Protect sheet options are

* LockedCells         - Allows the users to select the locked cells of the protected worksheet.

* UnLockedCells       - Allows the users to select the unlocked cells of the protected worksheet.

* FormattingCells     - Allows the users to format any cell on a protected worksheet.

* FormattingRows      - Allows the users to format any row on a protected worksheet.

* FormattingColumns   - Allows the users to format any column on a protected worksheet.

* InsertingRows       - Allows the users to insert rows on the protected worksheet.

* InsertingColumns    - Allows the users to insert columns on the protected worksheet.

* InsertingHyperlinks - Allows the users to insert hyperlinks on the protected worksheet.

* DeletingRows        - Allows the users to delete rows on the protected worksheet.

* DeletingColumns     - Allows the users to delete columns on the protected worksheet.

* Objects             - Allows the users to edit the objects such as Graphic cells like charts,rich textbox, etc.

{% tabs %}
{% highlight c# %}
//Protect the sheet with password
spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123");

//Protect the sheet with Protection options
spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123", ExcelSheetProtection.FormattingCells);

//Unprotect the sheet
spreadsheet.UnProtectSheet(spreadsheet.ActiveSheet, "123");
{% endhighlight %}
{% endtabs %}

### Protecting a workbook

SfSpreadsheet provides support to protect the structure and windows of a workbook. By protecting the structure, prevent a user from adding or deleting worksheets or from displaying hidden worksheets. By protecting the windows in the workbook, you can control the size of the workbook, etc.

{% tabs %}
{% highlight c# %}
// To Protect the Workbook 
spreadsheet.Protect(true, true, "123");

//To Unprotect the Workbook
spreadsheet.Unprotect("123");
{% endhighlight %}
{% endtabs %}

## Gridlines

SfSpreadsheet provides support to control the visibility and color of the Gridlines in a worksheet.

{% tabs %}
{% highlight c# %}
//To show GridLines
spreadsheet.SetGridLinesVisibility(true);

//To hide GridLines
spreadsheet.SetGridLinesVisibility(false);
{% endhighlight %}
{% endtabs %}

## Headings

SfSpreadsheet provides support to control the visibility of row and column headers in a worksheet

{% tabs %}
{% highlight c# %}
//To hide the Header cells visibility
spreadsheet.SetRowColumnHeadersVisibility(false);
{% endhighlight %}
{% endtabs %}

## Zooming

SfSpreadsheet provides support to zoom in and zoom out of a worksheet view. The property [AllowZooming](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~AllowZooming.html) determines whether to allow zooming or not.

{% tabs %}
{% highlight c# %}
//zoom factor
spreadsheet.SetZoomFactor("Sheet1", 200);
{% endhighlight %}
{% endtabs %}

The Events associated with the Zooming are 

. [ZoomFactorChanged](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanged_EV.html)

. [ZoomFactorChanging](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanging_EV.html)

## Events

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
{{ '[WorkbookCreating](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorkbookCreating_EV.html) ' | markdownify }}</td><td>
Occurs when the workbook is to be created in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorkbookLoaded](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorkbookLoaded_EV.html) ' | markdownify }}</td><td>
Occur when the workbook is loaded in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorksheetAdding](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorksheetAdding_EV.html) ' | markdownify }}
</td><td>
Occurs when the worksheet is to be added in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorksheetAdded](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorksheetAdded_EV.html) ' | markdownify }}
</td><td>
Occurs when the worksheet is added in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorksheetRemoving](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorksheetRemoving_EV.html) ' | markdownify }}
</td><td>
Occurs when the worksheet is to be removed from SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorksheetRemoved](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorksheetRemoved_EV.html) ' | markdownify }}
</td><td>
Occurs when the worksheet is removed from SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[WorkbookUnloaded](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~WorkbookUnloaded_EV.html) ' | markdownify }}</td><td>
Occurs when the workbook is unloaded or removed from the SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[ZoomFactorChanged](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanged_EV.html) ' | markdownify }}</td><td>
Occurs when the zoom factor in SfSpreadsheet is changed.</td></tr>
<tr>
<td>
{{ '[ZoomFactorChanging](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanging_EV.html) ' | markdownify }}</td><td>
Occurs when the zoom factor in SfSpreadsheet is to be changed.</td></tr>
<tr>
<td>
{{ '[ResizingColumns](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~ResizingColumns_EV.html) ' | markdownify }}</td><td>
Occurs when performing the resizing columns in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[ResizingRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~ResizingRows_EV.html) ' | markdownify }}</td><td>
Occurs when performing the resizing rows in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[CellCommentOpening](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CellCommentOpening_EV.html) ' | markdownify }}</td><td>
Occurs when opening the comments in the cells of SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[CellTooltipOpening](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CellTooltipOpening_EV.html) ' | markdownify }}</td><td>
Occurs when opening the tool tips of cells in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[CellContextMenuOpening](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CellContextMenuOpening_EV.html) ' | markdownify }}</td><td>
Occurs when opening the context menu of the cell in SfSpreadsheet.</td></tr>
<tr>
<td>
{{ '[QueryRange](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid~QueryRange_EV.html) ' | markdownify }}</td><td>
Occurs when grid queries for <code>IRange</code> information about a specific cell while rendering.</td></tr>
</table>

