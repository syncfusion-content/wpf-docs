---
layout: post
title:  Sorting and Filtering Operation in SfSpreadsheet
description: Sorting and Filtering Operation in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Sorting and Filtering

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

## Programmatic Sorting and Filtering

### Sorting 

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
    SortField sortField = sorter.SortFields.Add(1, SortOn.Values, OrderBy.Ascending);
    sorter.Sort();
}

{% endhighlight %}
{% endtabs %}

### Filtering 

Programmatically filter the data while importing the workbook by using XlsIO in the `WorkbookLoaded` event of SfSpreadsheet.

{% tabs %}
{% highlight c# %}

spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    IRange filterRange = spreadsheet.Workbook.ActiveSheet.Range["A1:D9"];
    spreadsheet.Workbook.ActiveSheet.AutoFilters.FilterRange = filterRange;
    IAutoFilter filter = spreadsheetControl.Workbook.ActiveSheet.AutoFilters[0];
    filter.AddTextFilter("1");
} 

{% endhighlight %}
{% endtabs %}

For more reference, please go through the [XlsIO](https://help.syncfusion.com/file-formats/xlsio/worksheet-cells-manipulation#data-sorting "") UG documentation.

## Unsupported Features

Currently SfSpreadsheet does not have support for following features.

* Advanced filtering
* Table filtering
* Multi-column sorting

## Limitations

### Sorting

* In Microsoft Excel, sorting label should be varied in filter popup based on the type of values in a column (For e.g, "Sort Smallest to Largest" for numeric values, "Sort A to Z" for string values, etc.). But in Spreadsheet, sort label should not be varied based on values due to improve the loading performance of filter popup.
* Sort Ascending or Sort Descending label is not checked in the filter popup, if the column is sorted in Microsoft Excel. Because currently XlsIO do not have support to fetch the sorted order while importing the workbook.

### Filtering

* If the filter applied in Microsoft Excel, then the filter will be cleared from all columns while clearing the filter from any one column Because unable to fetch the filtering order.
* While importing the workbook, checked and unchecked items are only displayed in the right most filtered column. Because unable to fetch the filtering order.
