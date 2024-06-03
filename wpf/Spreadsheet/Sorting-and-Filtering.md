---
layout: post
title: Sorting and Filtering in WPF Spreadsheet control | Syncfusion
description: Learn here all about Sorting and Filtering support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Sorting and Filtering in WPF Spreadsheet (SfSpreadsheet)

This section explains about sorting and filtering functionalities in the SfSpreadsheet.

## Filtering

By default, Filtering support will be enabled in the SfSpreadsheet, but if you want to disable the Filtering in SfSpreadsheet, set the `AllowFiltering` property of the `SfSpreadsheet` to be false.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSpreadsheet x:Name="spreadsheet" AllowFiltering="False"/>
{% endhighlight %}
{% highlight c# %}
spreadsheet.AllowFiltering = false;
{% endhighlight %}
{% endtabs %}

## Programmatic Sorting

Programmatically sort the data while importing the workbook by using XlsIO in the `WorkbookLoaded` event of SfSpreadsheet.

{% tabs %}
{% highlight c# %}
spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    IRange filterRange = spreadsheet.Workbook.ActiveSheet.Range["A1:D9"];
    spreadsheet.Workbook.ActiveSheet.AutoFilters.FilterRange = filterRange;
    IDataSort sorter = spreadsheet.Workbook.CreateDataSorter();
    sorter.SortRange = spreadsheet.ActiveSheet.Range["A1:D9"];
    ISortField sortField = sorter.SortFields.Add(1, SortOn.Values, OrderBy.Ascending);
    sorter.Sort();
}
{% endhighlight %}
{% endtabs %}

## Unsupported Features

Currently SfSpreadsheet does not have support for following features.

* Table filtering
* Multi-column sorting

## Limitations

### Sorting

* In Microsoft Excel, sorting label should be varied in filter popup based on the type of values in a column (For e.g, "Sort Smallest to Largest" for numeric values, "Sort A to Z" for string values, etc.). But in Spreadsheet, sort label should not be varied based on values due to improve the loading performance of filter popup.
* Sort Ascending or Sort Descending label is not checked in the filter popup, if the column is sorted in Microsoft Excel. Because currently XlsIO do not have support to fetch the sorted order while importing the workbook.

### Filtering

* If the filter applied in Microsoft Excel, then the filter will be cleared from all columns while clearing the filter from any one column Because unable to fetch the filtering order.
* While importing the workbook, checked and unchecked items are only displayed in the right most filtered column. Because unable to fetch the filtering order.


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.
