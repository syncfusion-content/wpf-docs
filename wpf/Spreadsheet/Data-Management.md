---
layout: post
title: Data Management in WPF Spreadsheet control | Syncfusion
description: Learn here all about Data Management support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Data Management in WPF Spreadsheet (SfSpreadsheet)
This section explains about how to import and export the DataTable in `SfSpreadsheet`.

## Import from DataTable

SfSpreadsheet provides support to import the data. The following list of data can be imported into the worksheet

* Data Table
* Data Column
* Data View
* Business Objects
* Array

To import the data from a data table, you can use [ImportDataTable](http://help.syncfusion.com/file-formats/xlsio/working-with-data#importing-data-to-worksheets) 
method

{% tabs %}
{% highlight c# %}
spreadsheet.ActiveSheet.ImportDataTable(data_table, true, 1, 1);
spreadsheet.ActiveGrid.InvalidateCells();
{% endhighlight %}
{% endtabs %}

For more details regarding importing of data, please refer the [XlsIO UG](http://help.syncfusion.com/file-formats/xlsio/working-with-data#importing-data-to-worksheets)

## Export to DataTable

SfSpreadsheet provides support to export the data. To Export the data from a data table, you can use [ExportDataTable](http://help.syncfusion.com/file-formats/xlsio/working-with-data#exporting-from-worksheet-to-data-table)
method

{% tabs %}
{% highlight c# %}
IWorksheet sheet = spreadsheet.Workbook.Worksheets[0];
IRange range = sheet.Range["A1:K50"];
DataTable data_table = sheet.ExportDataTable(range, ExcelExportDataTableOptions.ColumnNames);
{% endhighlight %}
{% endtabs %}

For more details regarding exporting of data, please refer the [XlsIO UG](http://help.syncfusion.com/file-formats/xlsio/working-with-data#exporting-from-worksheet-to-data-table)

