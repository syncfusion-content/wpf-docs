---
layout: post
title: Working With Spreadsheet in WPF Spreadsheet control | Syncfusion
description: Learn here all about Working With Spreadsheet support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
 documentation: ug
---

# Working With Spreadsheet in WPF Spreadsheet (SfSpreadsheet)
 This section explains about accessing the Worksheet, Grid and the events associated with it.

## Accessing the Worksheet

A __workbook__ is an excel document in the SfSpreadsheet. It is an object that exposes the [IWorkbook](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html) interface. Currently loaded workbook in the Spreadsheet can be accessed by using the [Workbook](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_Workbook) property of SfSpreadsheet.

A workbook consists of one or more worksheets stored within the worksheet collection. Accessing the worksheets in the collection, can be done by the following ways,

{% tabs %}
{% highlight c# %}
//By Specifying the index as,
spreadsheet.Workbook.Worksheets[0]

//By Specifying the sheet name as,
spreadsheet.Workbook.Worksheets["sheet1"]

//Access the Active worksheet as,
spreadsheet.ActiveSheet
{% endhighlight %}
{% endtabs %}

For more information regarding working with worksheets, you can refer the [XlsIO UG](http://help.syncfusion.com/file-formats/xlsio/overview) link

N> `ActiveGrid` and `ActiveSheet` property can be accessed only after the `WorkbookLoaded` Event of `SfSpreadsheet` is triggered

## Accessing the Grid

Each worksheet in the workbook is loaded into the view as [SpreadsheetGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html) in  `SfSpreadsheet`.

When the workbook is loaded in the SfSpreadsheet, the [WorkbookLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) Event is invoked and when the workbook is removed from SfSpreadsheet, the [WorkbookUnloaded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) Event is invoked. 

When the worksheet is added into the SfSpreadsheet, the [WorksheetAdded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) Event is invoked and when the worksheet is removed in the SfSpreadsheet, [WorksheetRemoved](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) Event is invoked.

Hence you can access the `ActiveGrid` either in the `WorkbookLoaded` or `WorksheetAdded` Event.

{% tabs %}
{% highlight c# %}
spreadsheet.WorksheetAdded += spreadsheet_WorksheetAdded;
spreadsheet.WorksheetRemoved += spreadsheet_WorksheetRemoved;

void spreadsheet_WorksheetAdded(object sender, WorksheetAddedEventArgs args)
{

   //Access the Active SpreadsheetGrid and hook the events associated with it.
    var grid = spreadsheet.ActiveGrid;
    grid.CurrentCellActivated += grid_CurrentCellActivated;
}

void spreadsheet_WorksheetRemoved(object sender, WorksheetRemovedEventArgs args)
{

   //Access the Active SpreadsheetGrid and unhook the events associated with it
    var grid = spreadsheet.ActiveGrid;
    grid.CurrentCellActivated -= grid_CurrentCellActivated;
}
{% endhighlight %}
{% endtabs %}

You can also access the each `SpreadsheetGrid` in the SfSpreadsheet either by passing the particular sheet name in the [GridCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_GridCollection) or by invoking `WorkbookLoaded` Event of SfSpreadsheet. 

### By using Sheet Name

For your reference, setting the row and column count dynamically for the second sheet in the Workbook

{% tabs %}
{% highlight c# %}
var sheet = spreadsheet.Workbook.Worksheets[1];
spreadsheet.GridCollection[sheet.Name].RowCount = 50;
spreadsheet.GridCollection[sheet.Name].ColumnCount = 12;
{% endhighlight %}
{% endtabs %} 

### By using Event

{% tabs %}
{% highlight c# %}
spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;
spreadsheet.WorkbookUnloaded += spreadsheet_WorkbookUnloaded;

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{

  //Hook the events here

   foreach (var grid in args.GridCollection)
   {
    grid.QueryRange += grid_QueryRange; 
   }      
}

void spreadsheet_WorkbookUnloaded(object sender, WorkbookUnloadedEventArgs args)
{

  //Unhook the events here

   foreach (var grid in args.GridCollection)
   {
    grid.QueryRange -= grid_QueryRange; 
   }
}
{% endhighlight %}
{% endtabs %}

N> SfSpreadsheet supports virtual mode, which lets you dynamically provide data to the grid by handling an event, [QueryRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html), for example. In virtual mode, data will be dynamically loaded into the SpreadsheetGrid on demand or when users need to view the data.

## Setting the ActiveSheet programmatically

SfSpreadsheet allows you to set the [ActiveSheet](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_ActiveSheet) programmatically by specifying the sheet name in the `SetActiveSheet` method of `SfSpreadsheet`.

{% tabs %}
{% highlight c# %}
spreadsheet.SetActiveSheet("Sheet5");
{% endhighlight %}
{% endtabs %}


## Accessing the cell or range of cells

SfSpreadsheet allows to access a single cell or range of cells in the workbook using `IRange` interface.

The following code shows the several ways of accessing a single cell or range of cells in the `Worksheet`,

{% tabs %}
{% highlight c# %}
// Access a cell by specifying cell address. 
var cell = spreadsheet.Workbook.Worksheets[0].Range["A3"];

// Access a cell by specifying cell row and column index. 
var cell1 = spreadsheet.Workbook.Worksheets[0].Range[3, 1];

// Access a cells by specifying user defined name.
var cell2 = spreadsheet.Workbook.Worksheets[0].Range["Namerange"];

// Accessing a range of cells by specifying cell's address.
var cell3 = spreadsheet.Workbook.Worksheets[0].Range["A5:C8"];

// Accessing a range of cells specifying cell row and column index.
var cell4 = spreadsheet.Workbook.Worksheets[0].Range[15, 1, 15, 3];
{% endhighlight %}
{% endtabs %}

For more reference regarding accessing the range, refer [XlsIO](http://help.syncfusion.com/file-formats/xlsio/worksheet-cells-manipulation#accessing-a-cell-or-a-range) UG.

N>  If the user has made any modifications with XlsIO range in SfSpreadsheet, then they should [refresh the view](http://help.syncfusion.com/wpf/sfspreadsheet/working-with-sfspreadsheet#refreshing-the-view) to update the modifications in `SpreadsheetGrid`.

## Accessing the value of a cell

SfSpreadsheet allows you to access the value of a cell by using [Value](https://help.syncfusion.com/cr/file-formats/Syncfusion.XlsIO.IRange.html#Syncfusion_XlsIO_IRange_Value) property of `IRange` and to get the value of the cell along with its format,  [DisplayText](https://help.syncfusion.com/cr/file-formats/Syncfusion.XlsIO.IRange.html#Syncfusion_XlsIO_IRange_DisplayText) property can be used.

{% tabs %}
{% highlight c# %}
// Access a cell value by using "Value" Property,
var cellValue = spreadsheet.Workbook.Worksheets[1].Range["A3"].Value

// Access a cell value by using "DisplayText" Property. 
var displayValue = spreadsheet.Workbook.Worksheets[1].Range[4, 1].DisplayText;
{% endhighlight %}
{% endtabs %}

## Setting the value or formula to a cell

In SfSpreadsheet, to update the cell value and formula programmatically, [SetCellValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SetCellValue_Syncfusion_XlsIO_IRange_System_String_) method of [SpreadsheetGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html) should be invoked and then invalidate that cell to update the view.

{% tabs %}
{% highlight c# %}
var range = spreadsheet.ActiveSheet.Range[2,2];
spreadsheet.ActiveGrid.SetCellValue(range, "cellValue");
spreadsheet.ActiveGrid.InvalidateCell(2,2);
{% endhighlight %}
{% endtabs %}

## Clearing the value or formatting from a cell

SfSpreadsheet allows you to delete the contents of a cell or delete the contents along with its formatting(comments,Conditional formats,..) also.

The following code illustrates the different way of deleting the value from a cell,

{% tabs %}
{% highlight c# %}
//To clear the contents in the range alone,
spreadsheet.Workbook.Worksheets[0].Range[3, 3].Clear();

//To clear the contents along with its formatting in the range,   
spreadsheet.Workbook.Worksheets[0].Range[3, 3].Clear(true);

//To clear the range with specified ExcelClearOptions,
spreadsheet.Workbook.Worksheets[0].Range[3, 3].Clear(ExcelClearOptions.ClearDataValidations);
{% endhighlight %}
{% endtabs %}

N> [ExcelClearOptions](http://help.syncfusion.com/cr/file-formats/Syncfusion.XlsIO.ExcelClearOptions.html) is an enum which specifies the possible directions to clear the cell formats, content, comments,conditional format,data validation or clear all of them.

## Refreshing the view

SfSpreadsheet allows you to invalidate or refresh the view either by specifying the specific range or full range.

The following code demonstrates the different ways of refreshing the view,

{% tabs %}
{% highlight c# %}
//Invalidates the mentioned cell in the grid,
spreadsheet.ActiveGrid.InvalidateCell(3, 3);

//Invalidates the range ,
var range = GridRangeInfo.Cells(5, 4, 6, 7);
spreadsheet.ActiveGrid.InvalidateCell(range);

//Invalidates all the cells in the grid,
spreadsheet.ActiveGrid.InvalidateCells();

//Invalidates the measurement state(layout) of grid,
spreadsheet.ActiveGrid.InvalidateVisual();

//Invalidates the cell borders in the range,
var range = GridRangeInfo.Cells(2, 4, 6, 4);
spreadsheet.ActiveGrid.InvalidateCellBorders(range);
{% endhighlight %}
{% endtabs %}

## Scrolling the Grid programmatically

SfSpreadsheet allows the user to scroll the grid into mentioned cell, by using [ScrollInView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_ScrollInView_Syncfusion_UI_Xaml_Grid_ScrollAxis_RowColumnIndex_) method of `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}
spreadsheet.ActiveGrid.ScrollInView(new RowColumnIndex(5, 5));
{% endhighlight %}
{% endtabs %}

## Formula Bar

The Formula Bar is located above the worksheet area of the SfSpreadsheet. The formula bar displays the data or formula stored in the active cell.
Users can set the visibility state of Formula Bar using [FormulaBarVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_FormulaBarVisibility) property of `SfSpreadsheet`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSpreadsheet x:Name="spreadsheet" FormulaBarVisibility="Collapsed"/>
{% endhighlight %}
{% highlight c# %}
spreadsheet.FormulaBarVisibility = System.Windows.Visibility.Collapsed;
{% endhighlight %}
{% endtabs %}

## Identify whether the workbook is modified or not

`IsCellModified` property of `WorkbookImpl` is used to identify whether any cell modified in a workbook or not after importing. Since it is an internal property, access it using Reflection.

{% tabs %}
{% highlight c# %}
var workbook = spreadsheet.Workbook as WorkbookImpl; 
BindingFlags bindFlags = BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic | BindingFlags.Static; 
var value = typeof(WorkbookImpl).GetProperty("IsCellModified", bindFlags).GetValue(workbook); 
{% endhighlight %}
{% endtabs %}

## Suppress message boxes in Spreadsheet

In Spreadsheet, warning messages, error alerts are displayed while performing some actions like Excel. If you want to avoid those alerts, then set the [DisplayAlerts](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_DisplayAlerts) property to `false`. 

{% tabs %}
{% highlight c# %}
//To Suppress message boxes in Spreadsheet
spreadsheet.DisplayAlerts = false;
{% endhighlight %}
{% endtabs %}

## Suspend and resume formula calculation

Spreadsheet provides support to suspend the formula calculation and resume it whenever needed using the [SuspendFormulaCalculation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_SuspendFormulaCalculation) and [ResumeFormulaCalculation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_ResumeFormulaCalculation) method.

Resuming formula calculation will recalculate all the formula cells in a workbook. This would be helpful to improve the performance when you are updating the value of more number of cells by skipping the dependent cells recalculation on each cell value changed.

{% tabs %}
{% highlight c# %}
//Resumes the automatic formula calculation
spreadsheet.ResumeFormulaCalculation();

//Suspends the automatic formula calculation
spreadsheet.SuspendFormulaCalculation();
{% endhighlight %}
{% endtabs %}

## Close the popup programmatically 	

In SfSpreadsheet, popup windows are used to display the options like copy paste option, fill series option, etc. which will be closed automatically on certain actions. However you can also able to close the popup programmatically by using the [ShowHidePopup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_ShowHidePopup_System_Boolean_) method of `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}
//To close the popup
spreadsheet.ActiveGrid.ShowHidePopup(false);

//To show the closed popup, if needed.
spreadsheet.ActiveGrid.ShowHidePopup(true);
{% endhighlight %}
{% endtabs %}

## Identify when the active sheet is changed

SfSpreadsheet provides support to identify when the active sheet is changed by using [PropertyChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) event of SfSpreadsheet like below.

{% tabs %}
{% highlight c# %}
Spreadsheet.PropertyChanged += Spreadsheet_PropertyChanged;

void Spreadsheet_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
{

    // when the worksheets in the workbook changed
	
    if(e.PropertyName == "ActiveSheet")
    {

        //Implement code
    }
}
{% endhighlight %}
{% endtabs %}
