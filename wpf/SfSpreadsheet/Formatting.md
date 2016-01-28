---
layout: post
title: Formatting | SfSpreadsheet | WPF | Syncfusion
description: formatting
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Formatting

This section explains about the formatting options similar to excel in SfSpreadsheet
<br/>
<br/>

## Cell Styles

Styles and formats defined in an Excel file are automatically imported. Users can also apply these settings to cells during run time. The following are the formatting attributes for the cell.

* Cell font settings (font name, size, color, style, etc.) 
* Cell background 
* Cell content alignment (vertical and horizontal alignment, indent and text wrapping) 
* Cell borders 
* Number Formatting
* Merge Cells

For your reference, for applying background color for the cells in SfSpreadsheet, set the color index for the particular XlsIO range and invalidate the range in order to update the view in SpreadsheetGrid.

For single cell

{% tabs %}
{% highlight c# %}

IRange range = spreadsheet.ActiveSheet.Range["A5"];

range.CellStyle.ColorIndex = Syncfusion.XlsIO.ExcelKnownColors.Blue;

spreadsheet.ActiveGrid.InvalidateCell(range.Row, range.Column);

{% endhighlight %}
{% endtabs %}

For selected range of cells,

{% tabs %}
{% highlight c# %}

var selectedRanges = spreadsheet.ActiveGrid.SelectedRanges;

foreach (var range in selectedRanges)
{
  string cell = GridExcelHelper.ConvertGridRangeToExcelRange(range, spreadsheet.ActiveGrid);
  spreadsheet.ActiveSheet.Range[cell].CellStyle.ColorIndex = ExcelKnownColors.Blue;
  spreadsheet.ActiveGrid.InvalidateCell(range, true);
}

{% endhighlight %}
{% endtabs %}

For more information regarding formatting options, please go through [XlsIO](http://help.syncfusion.com/file-formats/xlsio/working-with-cell-or-range-formatting)
<br/>
<br/>

## Merge Cells
<br/>

### Merge

SfSpreadsheet provides support to merge two or more cells. When a group of cells is merged, the contents of the upper-left cell will be taken as the content of the merged cell, rest will be deleted.

For merging the cells in SfSpreadsheet, you need to add the [CoveredCellInfo](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.CoveredCellInfo.html) into [CoveredCells](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CoveredCells.html) collection of SpreadsheetGrid and merge the range using [Merge](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IRange~Merge.html) method in XlsIO. Also to update the view, you need to invalidate the cells in the SpreadsheetGrid

{% tabs %}
{% highlight c# %}

var gridrange = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

var excelrange = gridrange.ConvertGridRangeToExcelRange(spreadsheet.ActiveGrid);

var coverCell = new CoveredCellInfo(gridrange.Top, gridrange.Left, gridrange.Bottom, gridrange.Right);

spreadsheet.ActiveGrid.CoveredCells.Add(coverCell);

spreadsheet.ActiveSheet.Range[excelrange].Merge();

spreadsheet.ActiveGrid.InvalidateCell(gridrange, true);

{% endhighlight %}
{% endtabs %}
<br/>

### Unmerge

You can also unmerge the merged cells in SfSpreadsheet.

For unmerging the cells in SfSpreadsheet, you need to clear the [CoveredCells](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CoveredCells.html) from the SpreadsheetGrid and unmerge the range using [UnMerge](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IRange~UnMerge.html) method in XlsIO. Also to update the view, you need to invalidate the cells in the SpreadsheetGrid

{% tabs %}
{% highlight c# %}

var gridrange = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

var excelrange = gridrange.ConvertGridRangeToExcelRange(spreadsheet.ActiveGrid);

spreadsheet.ActiveGrid.CoveredCells.Clear(gridrange);

spreadsheet.ActiveSheet.Range[excelrange].UnMerge();

spreadsheet.ActiveGrid.InvalidateCell(gridrange, true);

{% endhighlight %}
{% endtabs %}

