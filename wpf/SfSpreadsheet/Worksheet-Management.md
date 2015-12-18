---
layout: post
title: Worksheet Management | SfSpreadsheet | WPF | Syncfusion
description: worksheet management
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Worksheet Management
 This section explains about the operations that are performed with the worksheet
<br/>

## Insert and Delete

SfSpreadsheet provides support to insert and delete the worksheets in a workbook.

{% highlight c# %}

//Insert Sheet

spreadsheet.AddSheet();
	
//Insert sheet with name

spreadsheet.AddSheet("Sheet4", 3);

//Delete Sheet

spreadsheet.RemoveSheet("Sheet2");

{% endhighlight %}
<br/>

## Hide and Unhide

SfSpreadsheet provides support to hide and unhide the worksheets in a workbook.

{% highlight c# %}

//Hide Sheet

spreadsheet.HideSheet("Sheet 2");

//Unhide Sheet

spreadsheet.UnhideSheet("Sheet 2");

{% endhighlight %}
<br/>

## GridLines

SfSpreadsheet provides support to control the visibility and color of the Gridlines in a worksheet.

{% highlight c# %}

//To show GridLines

spreadsheet.ActiveGrid.ShowGridLines = true;

spreadsheet.ActiveSheet.IsGridLinesVisible = true;

spreadsheet.ActiveGrid.InvalidateCells();

//To hide GridLines

spreadsheet.ActiveGrid.ShowGridLines = false;

spreadsheet.ActiveSheet.IsGridLinesVisible = false;

spreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}
<br/>

## Headings

SfSpreadsheet provides support to control the visibility of row and column headers in a worksheet

{% highlight c# %}

/For Header cells visibility

spreadsheet.ActiveSheet.IsRowColumnHeadersVisible = true;

spreadsheet.ActiveGrid.RowHeights.SetHidden(0, 0, false);

spreadsheet.ActiveGrid.ColumnWidths.SetHidden(0, 0, false);

{% endhighlight %}
<br/>

## Zooming

SfSpreadsheet provides support to zoom in and zoom out of a worksheet view. The property [AllowZooming](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6319.html) determines whether to allow zooming or not.

{% highlight c# %}

//zoomfactor

spreadsheet.SetZoomFactor("Sheet1", 200);

{% endhighlight %}

The Events associated with the Zooming are 

. [ZoomFactorChanged](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6346.html)

. [ZoomFactorChanging](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6347.html)
<br/>

## Protection
<br/>

### Workbook Protection

SfSpreadsheet provides support to protect the structure and windows of a workbook. By protecting the structure, prevent a user from adding or deleting worksheets or from displaying hidden worksheets. By protecting the windows in the workbook, you can control the size of the workbook, etc.

{% highlight c# %}

// To Protect the Workbook 

spreadsheet.Protect(true, true, "123");

//To Unprotect the Workbook

spreadsheet.Unprotect("123");

{% endhighlight %}
<br/>

### Worksheet Protection

SfSpreadsheet provides support to protect the worksheet with or without password. This helps to prevent a user from modifying the contents of the worksheet. The protection of worksheet can be done with protection options also.

{% highlight c# %}

//Protect the sheet with password

spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123");

//Protect the sheet with Protection options

spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123", ExcelSheetProtection.All);

//Unprotect the sheet

spreadsheet.UnProtectSheet(spreadsheet.ActiveSheet, "123");

{% endhighlight %}

