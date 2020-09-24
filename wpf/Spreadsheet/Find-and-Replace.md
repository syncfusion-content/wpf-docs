---
layout: post
title:  Find and Replace Operation in SfSpreadsheet | Syncfusion
description: This section explains that how to find a text in SfSpreadsheet and replace it with different string for Syncfusion Essential WPF.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Find and Replace

This section explains about Find and Replace operations in SfSpreadsheet. 

## Find 

Searches for specific data such as particular number or text according to specified options and returns an IRange representing the cell or null if no cell is found. The various options in Find operation are

* [FindAll](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindAll_Syncfusion_XlsIO_IWorkbook_System_String_Syncfusion_UI_Xaml_Spreadsheet_SearchBy_Syncfusion_XlsIO_ExcelFindType_System_Boolean_System_Boolean_)
* [FindNext](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindNext_Syncfusion_XlsIO_IWorkbook_System_String_Syncfusion_UI_Xaml_Spreadsheet_SearchBy_Syncfusion_XlsIO_ExcelFindType_System_Boolean_System_Boolean_)
* [FindConditionalFormatting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindConditionalFormatting_Syncfusion_XlsIO_IWorksheet_)
* [FindConstants](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindConstants_Syncfusion_XlsIO_IWorksheet_)
* [FindFormulas](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindFormulas_Syncfusion_XlsIO_IWorksheet_)
* [FindDataValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_FindDataValidation_Syncfusion_XlsIO_IWorksheet_)

The common parameters to be passed in Find functions are,

* The option to specify whether the search can be done within the Workbook([IWorkbook](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html)) or Worksheet([IWorksheet](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html)).
* The text to be searched.
* The option to specify the direction whether the search can be done either by row wise or column wise using [SearchBy](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchBy.html) enum.
* The type to specify whether the search can be done either in formulas or values using [ExcelFindType](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.ExcelFindType.html) enum.
* For a case sensitive search, pass the parameter as true otherwise you can pass the parameter as false.
* For matching the entire cell content with the search text, pass the parameter as true otherwise you can pass the parameter as false.

### Find All

Searches every occurrence of specific data based on the criteria that you are searching for and returns an `IRange` list representing the cells in `SfSpreadsheet`

{% tabs %}
{% highlight c# %}

//Search the entire workbook
var list = spreadsheet.SearchManager.FindAll(spreadsheet.Workbook, "sample", SearchBy.ByRows, ExcelFindType.Text, false, true);

// To select the matched cell content ranges,

foreach (var cell in list)
{  
  spreadsheet. ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

//Search the particular worksheet
var list = spreadsheet.SearchManager.FindAll(spreadsheet.Workbook.Worksheets[0], "sample", SearchBy.ByRows, ExcelFindType.Text, false, true);

// To select the matched cell content ranges,

foreach (var cell in list)
{
  spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}
{% endhighlight %}
{% endtabs %}

### Find Next

Searches the first occurrence of specific data which matches the conditions and returns the matched `IRange` from the current range that represents the cell.

{% tabs %}
{% highlight c# %}
//Search the text in entire workbook in column wise,
var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook, "sample", SearchBy.ByColumns, ExcelFindType.Text, false, true);

// To move the current cell to matched cell content range,
spreadsheet.ActiveGrid.CurrentCell.MoveCurrentCell(cell.Row,cell.Column);          

//Search the formula in particular worksheet in row wise,
var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook.Worksheets[0], "sum", SearchBy.ByRows, ExcelFindType.Text, false, false);

// To move the current cell to matched cell content range,
spreadsheet.ActiveGrid.CurrentCell.MoveCurrentCell(cell.Row,cell.Column);          
{% endhighlight %}
{% endtabs %}

### Find Conditional Formatting

Searches and returns the `IRange` list which have conditional formatting within the specified worksheet.

{% tabs %}
{% highlight c# %}

//Searches the conditional formatting within the worksheet,
var list = spreadsheet.SearchManager.FindConditionalFormatting(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
  spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}
{% endhighlight %}
{% endtabs %}

### Find Constants

Searches and returns the `IRange` list which have constants within the specified worksheet.

{% tabs %}
{% highlight c# %}
//Searches the constants within the worksheet,
var list = spreadsheet.SearchManager.FindConstants(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));         
}

{% endhighlight %}
{% endtabs %}

### Find Formulas

Searches and returns the `IRange` list which have formulas within the specified worksheet.

{% tabs %}
{% highlight c# %}
//Searches the formulas within the worksheet,
var list = spreadsheet.SearchManager.FindFormulas(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

{% endhighlight %}
{% endtabs %}


### Find Data Validation

Searches and returns the `IRange` list which have data validation within the specified worksheet.

{% tabs %}
{% highlight c# %}
//Searches the data validation within the worksheet,
var list = spreadsheet.SearchManager.FindDataValidation(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));        
}

{% endhighlight %}
{% endtabs %}

## Replace All

Searches and replaces all the texts either in the workbook or worksheet based on the given option.

The parameters to be passed in [ReplaceAll](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SearchManager.html#Syncfusion_UI_Xaml_Spreadsheet_SearchManager_ReplaceAll_Syncfusion_XlsIO_IWorkbook_System_String_System_String_System_Boolean_System_Boolean_) function is,

* The option to specify whether the search can be done within the Workbook([IWorkbook](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html)) or Worksheet([IWorksheet](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html)) in SfSpreadsheet.
* The text to be searched.
* The text to be replaced.
* For a case sensitive search, pass the parameter as true otherwise you can pass the parameter as false.
* For matching the entire cell content with the search text, pass the parameter as true otherwise you can pass the parameter as false.

{% tabs %}
{% highlight c# %}

//Replaces the text in the entire workbook
spreadsheet.SearchManager.ReplaceAll(spreadsheet.Workbook, "sample","Sync", false, false);

//Replaces the text in the particular worksheet
spreadsheet.SearchManager.ReplaceAll(spreadsheet.Workbook.Worksheets[0], "sample", "sync", false, true);

{% endhighlight %}
{% endtabs %}

## Replace

Searches for the text or numbers that you want to change using `FindNext` method and once the immediate matched cell has been found, use [SetCellValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SetCellValue_Syncfusion_XlsIO_IRange_System_String_) method to replace it with specified text or numbers in SfSpreadsheet.

{% tabs %}
{% highlight c# %}
//Searches the given text and replaces it with specified text
var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook, "sample", SearchBy.ByColumns, ExcelFindType.Text, false, true);
spreadsheet.ActiveGrid.SetCellValue(cell, "sync");
{% endhighlight %}
{% endtabs %}
