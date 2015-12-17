---
layout: post
title: Outline | SfSpreadsheet | WPF | Syncfusion
description: outline
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Outline (Group)

SfSpreadsheet provides support for outlines like in excel which makes your data easier to view. You can group the data’s either by rows or columns.

To group the rows

{% highlight c# %}

var gridrange = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

var excelrange = gridrange.ConvertGridRangeToExcelRange(spreadsheet.ActiveGrid);

spreadsheet.ActiveSheet.Range[excelrange].Group(ExcelGroupBy.ByRows);

spreadsheet.ActiveGrid.CurrentCell.Refresh();

spreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

To group the columns

{% highlight c# %}


var gridrange = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

var excelrange = gridrange.ConvertGridRangeToExcelRange(spreadsheet.ActiveGrid);

spreadsheet.ActiveSheet.Range[excelrange].Group(ExcelGroupBy.ByColumns);

spreadsheet.ActiveGrid.CurrentCell.Refresh();

spreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

