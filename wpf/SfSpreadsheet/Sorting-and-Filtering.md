---
layout: post
title:  Sorting and Filtering Operation in SfSpreadsheet
description: Sorting and Filtering Operation in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Sorting and Filtering

This section explains about filtering operations in the SfSpreadsheet

## Filtering

By default, Filtering support will be enabled in the SfSpreadsheet, but if you want to disable the Filtering in SfSpreadsheet, set the __**AllowFiltering**__ property to be **false** in the Spreadsheet Loaded event.  

{% tabs %}
{% highlight c# %}

void spreadsheet_Loaded(object sender, RoutedEventArgs e)
{
    spreadsheet.AllowFiltering = false;
}

{% endhighlight %}
{% endtabs %}


## Programmatic Sorting and Filtering feature

### Sorting 

Programmatic [sorting](https://help.syncfusion.com/file-formats/xlsio/worksheet-cells-manipulation#data-sorting "") can perform in spreadsheet based on cell values by using XlsIO’s **WorkbookLoaded** Event.

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

Programmatic Auto [Filtering](https://help.syncfusion.com/file-formats/xlsio/worksheet-cells-manipulation#data-filtering "") can able to perform in Spreadsheet by using XlsIO’s **WorkbookLoaded** Event.

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

## Unsupported Features

1. SfSpreadsheet does not have support for **Table** **Filtering**.
2. SfSpreadsheet does not have support for **Multi** **Column** **Sorting**.
3. SfSpreadsheet does not have support for **Advanced** **Filtering**.

## Limitations

### Sorting

1. Sort Ascending and Sort Descending label only displayed in the filter popup for the seamless performance while opening the filter popup in the spreadsheet.

2. Sort Ascending or Sort Descending is not determined in the filter popup from the imported excel sheet as Excel. Because XlsIO not maintained the sorted order of the column.

3. FilterToggleButton state not changed to Sort Ascending or Sort Descending when perform programmatic sorting using XlsIO.

### Filtering

    Auto filtered columns in the entire sheet has been cleared even if cleared the filter from any single column of the imported excel sheet. Because when import the sheet last Auto Filtered column could not maintained in the XlsIO. Hence, right most Auto Filtered column considered as last Auto filtered column in the spreadsheet.

