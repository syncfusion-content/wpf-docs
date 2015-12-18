---
layout: post
title: Data Management | SfSpreadsheet | WPF | Syncfusion
description: data management
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Data Management

SfSpreadsheet provides support to import data from a Datatable to a SfSpreadSheet and export data from a SfSpreadSheet to a DataTable respectively.

To import the data from a datatable, you can use [ImportDataTable](http://help.syncfusion.com/file-formats/xlsio/working-with-data#importing-data-to-worksheets) 
method

{% highlight c# %}

spreadsheet.ActiveSheet.ImportDataTable(datatable, true, 1, 1);

spreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

To Export the data from a datatable, you can use [ExportDataTable](http://help.syncfusion.com/file-formats/xlsio/working-with-data#exporting-from-worksheet-to-data-table)
method

{% highlight c# %}

IWorksheet sheet = spreadsheet.Workbook.Worksheets[0];

IRange range = sheet.Range["A1:K50"];

DataTable Dt = sheet.ExportDataTable(range, ExcelExportDataTableOptions.ColumnNames);

{% endhighlight %}

