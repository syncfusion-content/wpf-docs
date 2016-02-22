---
layout: post
title: Outline 
description: How to group/ungroup the rows and columns in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Outline (Group)

SfSpreadsheet provides support for outlines like in excel which makes your data easier to view. You can group or ungroup the data’s either by rows or columns.

To [Group](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~Group.html) the rows/columns

{% tabs %}
{% highlight c# %}

//Group rows,

var gridrange = GridRangeInfo.Rows(4,8);
spreadsheet.Group(spreadsheet.ActiveSheet, gridrange, ExcelGroupBy.ByRows);

//Group columns,

var gridrange = GridRangeInfo.Cols(4,8);
spreadsheet.Group(spreadsheet.ActiveSheet, range, ExcelGroupBy.ByColumns);

{% endhighlight %}
{% endtabs %}

To [Ungroup](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~UnGroup.html) the rows/columns

{% tabs %}
{% highlight c# %}
//Ungroup rows,

var gridrange = GridRangeInfo.Rows(4,8);
spreadsheet.UnGroup(spreadsheet.ActiveSheet, gridrange, ExcelGroupBy.ByRows);

//Ungroup columns,

var gridrange = GridRangeInfo.Cols(4,8);
spreadsheet.UnGroup(spreadsheet.ActiveSheet, range, ExcelGroupBy.ByColumns);

{% endhighlight %}
{% endtabs %}

### Collapse or Expand Group

Groups can be Expanded by [ExpandGroup](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IRange~ExpandGroup.html) method  and Collapsed  by [CollapseGroup](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IRange~CollapseGroup.html) method of XlsIO.

{% tabs %}
{% highlight c# %}

//Expand Rows,

spreadsheet.ActiveSheet.Range["A4:A8"].ExpandGroup(ExcelGroupBy.ByRows);
spreadsheet.ActiveGrid.RowHeights.SetHidden(4, 8, false);
spreadsheet.RefreshOutlines(true,false);

//Expand Columns,

spreadsheet.ActiveSheet.Range["A3:F3"].ExpandGroup(ExcelGroupBy.ByColumns);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(1, 6, false);
spreadsheet.RefreshOutlines(false,true);

//Collapse Rows,

spreadsheet.ActiveSheet.Range["A4:A8"].CollapseGroup(ExcelGroupBy.ByRows);
spreadsheet.ActiveGrid.RowHeights.SetHidden(4, 8, true);
spreadsheet.RefreshOutlines(true,false);

//Collapse Columns,

spreadsheet.ActiveSheet.Range["A3:F3"].CollapseGroup(ExcelGroupBy.ByColumns);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(1, 6, true);
spreadsheet.RefreshOutlines(false,true);

{% endhighlight %}
{% endtabs %}

N> [RefreshOutlines](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~RefreshOutlines.html) method is invoked to refresh/update the Outlines of the Group in SfSpreadsheet.


