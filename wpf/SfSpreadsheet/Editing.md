---
layout: post
title:  Editing behavior in SfSpreadsheet
description: Editing behavior in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Editing

This section explains about the Editing behavior, Data Validation and Hyperlinks in SfSpreadsheet.

## Editing

The SfSpreadsheet control provides support for Editing, you can modify and commit the cell values in the workbook.

By default, Editing behavior will be enabled in `SfSpreadsheet`,but if you want to disable the Editing in SfSpreadsheet, then set the [AllowEditing](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~AllowEditing.html) Property to be false.

{% tabs %}
{% highlight c# %}

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    spreadsheet.ActiveGrid.AllowEditing = false;
}

{% endhighlight %}
{% endtabs %}

### Editing a cell programmatically
    
SfSpreadsheet provides support to edit a cell programmatically by using [BeginEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCurrentCell~BeginEdit.html) method.

{% tabs %}
{% highlight c# %}

    spreadsheet.ActiveGrid.CurrentCell.BeginEdit(true);

{% endhighlight %}
{% endtabs %}

### Locking or Unlocking a cell

By default, every cells are locked in the worksheet.If you lock a cell in protect mode of the worksheet, then you cannot edit or format data in the cell.
But while in protect mode, if you want to edit or format a cell, you can unlock the cells.

{% tabs %}
{% highlight c# %}

var worksheet = spreadsheet.ActiveSheet;

var excelStyle = worksheet.Range["A2"].CellStyle;

//To unlock a cell,           
excelStyle.Locked = false;

//To lock a cell, 
excelStyle.Locked = true; 

{% endhighlight %}
{% endtabs %}

### Properties, Methods and Events

The order of events when editing and committing a cell value in SfSpreadsheet,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
{{ '[CurrentCellBeginEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellBeginEdit_EV.html)' | markdownify }}</td><td>
Occurs when the current cell enters into edit mode. This event allows to cancel entering the edit mode.</td></tr>
<tr>
<td>
{{ '[CurrentCellValueChanged](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValueChanged_EV.html)' | markdownify }}</td><td>
Occurs when the current cell value is changed in edit mode</td></tr>
<tr>
<td>
{{ '[CurrentCellValidating](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValidating_EV.html)' | markdownify }}</td><td>
Occurs when the current cell value is going to be validated</td></tr>
<tr>
<td>
{{ '[CurrentCellValidated](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValidated_EV.html)' | markdownify }}</td><td>
Occurs after the current cell is validated</td></tr>
<tr>
<td>
{{ '[CurrentCellEndEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellEndEdit_EV.html)' | markdownify }}</td><td>
Occurs when the current cell leaves from edit mode</td></tr>
</table>

Below table list the properties associated with Editing

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[AllowEditing](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~AllowEditing.html)' | markdownify }}</td><td>
Gets or sets the value indicating whether to allow the editing operation or not.</td></tr>
<tr>
<td>
{{ '[EditorSelectionBehavior](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~EditorSelectionBehavior.html)' | markdownify }}</td><td>
Gets or sets a value indicating whether editor select all the value or move last position.</td></tr>
<tr>
<td>
{{ '[EditTrigger](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~EditTrigger.html)' | markdownify }}</td><td>
Gets or Sets a value indicating any of the trigger options will cause cells to enter Edit Mode.</td></tr>
<tr>
<td>
{{ '[IsEditing](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.GridCurrentCell~IsEditing.html)' | markdownify }}</td><td>
Gets  whether the current cell is in editing mode or not.</td></tr>
</table>

Below table list the methods associated with Editing

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
{{ '[BeginEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCurrentCell~BeginEdit.html)' | markdownify }}</td><td>
Begins the editing operation of the current cell and returns true if the current cell enters into edit mode.</td></tr>
<tr>
<td>
{{ '[EndEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCurrentCell~EndEdit.html)' | markdownify }}</td><td>
Commits and ends the edit operation of the current cell.</td></tr>
</table>

## Data Validation

Data Validation allows the user to enter the data based on the restricted rules of the cell.

### Applying Data Validation at runtime

SfSpreadsheet allows the user to apply the data validation rules at runtime for particular cell or range using `IDataValidation` interface.

{% tabs %}
{% highlight c# %}

//Number Validation

IDataValidation validation = spreadsheet.ActiveSheet.Range["A5"].DataValidation;

validation.AllowType = ExcelDataType.Integer;

validation.CompareOperator = ExcelDataValidationComparisonOperator.Between;

validation.FirstFormula = "4";

validation.SecondFormula = "15";

validation.ShowErrorBox = true;

validation.ErrorBoxText = "Accepts values only between 4 to 15";

//Date Validation

IDataValidation validation = spreadsheet.ActiveSheet.Range["B4"].DataValidation;

validation.AllowType = ExcelDataType.Date;

validation.CompareOperator = ExcelDataValidationComparisonOperator.Greater;

validation.FirstDateTime = new DateTime(2016,5,5);

validation.ShowErrorBox = true;

validation.ErrorBoxText = "Enter the date value which is greater than 05/05/2016";

//TextLength Validation

IDataValidation validation = spreadsheet.ActiveSheet.Range["A3:B3"].DataValidation;

validation.AllowType = ExcelDataType.TextLength;

validation.CompareOperator = ExcelDataValidationComparisonOperator.LessOrEqual;

validation.FirstFormula = "4";

validation.ShowErrorBox = true;

validation.ErrorBoxText = "Text length should be lesser than or equal 4 characters";

//List Validation

IDataValidation validation = spreadsheet.ActiveSheet.Range["D4"].DataValidation;

validation.ListOfValues = new string[] { "10", "20", "30" };

//Custom Validation

IDataValidation validation = spreadsheet.ActiveSheet.Range["D4"].DataValidation;

validation.AllowType = ExcelDataType.Formula;

validation.FirstFormula = "=A1+A2>0";

validation.ErrorBoxText = "Sum of the values in A1 and A2 should be greater than zero";

{% endhighlight %}
{% endtabs %}

For more reference, please go through the [XlsIO](http://help.syncfusion.com/file-formats/xlsio/working-with-data-validation) UG.

T> If you want to add ComboBox to a cell in SfSpreadsheet, you can apply List Validation to that cell.

## Hyperlink

The Hyperlink is a convenient way to navigate or browse data within a worksheet or other worksheets in a workbook. SfSpreadsheet provides support to add, edit and remove the Hyperlinks in the workbook.

### Add a Hyperlink to a cell

SfSpreadsheet provides support to add hyperlink to a cell and it can be added in the hyperlinks collection using `IHyperlinks` interface.

{% tabs %}
{% highlight c# %}

// Creating a Hyperlink for e-mail,

var range = spreadsheet.ActiveSheet.Range["A5"];

IHyperLink hyperlink1 = spreadsheet.ActiveSheet.HyperLinks.Add(range);

hyperlink1.Type = ExcelHyperLinkType.Url;

hyperlink1.Address = "mailto:Username@syncfusion.com";

hyperlink1.TextToDisplay="Send Mail";

spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5, 1));

// Creating a Hyperlink for Opening Files,

var range1 = spreadsheet.ActiveSheet.Range["D5"];

IHyperLink hyperlink2 = spreadsheet.ActiveSheet.HyperLinks.Add(range1);

hyperlink2.Type = ExcelHyperLinkType.File;

hyperlink2.Address = @"C:\Samples\Local";

hyperlink2.TextToDisplay = "File Location";

spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5, 4));

//Creating a Hyperlink to refer another  cell in the workbook,

var range2 = spreadsheet.ActiveSheet.Range["C13"];

IHyperLink hyperlink3 = spreadsheet.ActiveSheet.HyperLinks.Add(range);

hyperlink3.Type = ExcelHyperLinkType.Workbook;

hyperlink3.Address = "Sheet2!C23";

hyperlink3.TextToDisplay = "Sample";

spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(13, 3));

{% endhighlight %}
{% endtabs %}

### Edit or Remove a Hyperlink

SfSpreadsheet provides support to edit or remove the hyperlinks from the range by accessing Hyperlinks collection.

{% tabs %}
{% highlight c# %}

//To Edit a hyperlink in a cell,

var hyperlink = spreadsheet.ActiveSheet.Range["A5"].Hyperlinks[0];

hyperlink.TextToDisplay = "Sample";

hyperlink.Address = "http://help.syncfusion.com";

spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5,1));

//To remove a hyperlink in a cell,

var hyperlink = spreadsheet.ActiveSheet.Range["A5"].Hyperlinks.RemoveAt(0);

spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5,1));

{% endhighlight %}
{% endtabs %}
