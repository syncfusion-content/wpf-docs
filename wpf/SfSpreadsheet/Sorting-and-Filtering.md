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

By default, Filtering support will be enabled in the SfSpreadsheet, but if you want to disable the Filtering in SfSpreadsheet, set the `AllowFiltering` property to be false in the Spreadsheet Loaded event.  

{% tabs %}
{% highlight c# %}

void spreadsheet_Loaded(object sender, RoutedEventArgs e)
{
    spreadsheet.AllowFiltering = false;
}

{% endhighlight %}
{% endtabs %}


## Programmatic Sorting and Filtering

### Sorting 

Programmatic sorting can perform while importing and loading the workbook in to spreadsheet by using the spreadsheet’s `WorkbookLoaded` Event.

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

Programmatic Auto Filtering can perform while importing and loading the workbook in to spreadsheet by using the spreadsheet’s `WorkbookLoaded` Event.

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

* Sort Ascending and Sort Descending label only displayed in the spreadsheet filter popup instead of display the Sort Smallest to Largest, Sort Largest to Smallest label for numeric values, Sort A to Z, Sort Z to A label for string values, Sort Oldest to Newest, Sort Newest to Oldest label for date values. Because maintaining the seamless performance while opening the filter popup in the spreadsheet.
* Sort Ascending or Sort Descending order is not checked in the filter popup while importing the excel sheet as excel. Because XlsIO does not maintain the sorted order of the columns.

### Filtering

* Auto Filtered columns in the entire sheet has been cleared even if cleared the filter from any single column of the imported excel sheet. Because XlsIO does not maintain Auto Filter applied order.
* While importing the excel sheets, right most filtered column considered as a last Auto Filtered column. Hence checked and unchecked items only displayed for the column. Because XlsIO does not maintain the Auto Filter applied order.
