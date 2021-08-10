---
layout: post
title: Rows and Columns in WPF Spreadsheet control | Syncfusion
description: Learn here all about Rows and Columns support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Rows and Columns in WPF Spreadsheet (SfSpreadsheet)
This section explains about the operations related with rows and columns in SfSpreadsheet

## Insert Rows and Columns

SfSpreadsheet provides support for dynamically inserting rows and columns into a worksheet. 

{% tabs %}
{% highlight c# %}
//For Inserting Rows
spreadsheet.ActiveSheet.InsertRow(2, 3);
spreadsheet.ActiveGrid.Model.InsertRows(2, 3);

//For Inserting Cols
spreadsheet.ActiveSheet.InsertColumn(3, 2);
spreadsheet.ActiveGrid.Model.InsertColumns(3, 2);
{% endhighlight %}
{% endtabs %}

###Events

Below events of [SpreadsheetGridModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html) are triggered while inserting the rows and columns. 

* [RowsInserted](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html)
* [ColumnsInserted](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html)

{% tabs %}
{% highlight c# %}
//To notify when rows are inserted
spreadsheet.ActiveGrid.Model.RowsInserted += Model_RowsInserted;

void Model_RowsInserted(object sender, GridRangeInsertedEventArgs e)
{
}

//To notify when Columns are inserted
spreadsheet.ActiveGrid.Model.ColumnsInserted += Model_ColumnsInserted;

void Model_ColumnsInserted(object sender, GridRangeInsertedEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

## Delete Rows and Columns

SfSpreadsheet provides support for deleting rows and columns from a worksheet. 

{% tabs %}
{% highlight c# %}
//For Deleting Rows
spreadsheet.ActiveSheet.DeleteRow(5, 2);
spreadsheet.ActiveGrid.Model.RemoveRows(5, 2);

//For Deleting Cols
spreadsheet.ActiveSheet.DeleteColumn(3, 2);
spreadsheet.ActiveGrid.Model.RemoveColumns(3, 2);
{% endhighlight %}
{% endtabs %}

###Events

Below events of [SpreadsheetGridModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html) are triggered while deleting the rows and columns. 

* [RowsRemoved](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html)
* [ColumnsRemoved](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGridModel.html)

{% tabs %}
{% highlight c# %}
//To notify when rows are deleted
spreadsheet.ActiveGrid.Model.RowsRemoved += Model_RowsRemoved;

void Model_RowsRemoved(object sender, GridRangeRemovedEventArgs e)
{
}

//To notify when columns are deleted
spreadsheet.ActiveGrid.Model.ColumnsRemoved += Model_ColumnsRemoved;

void Model_ColumnsInserted(object sender, GridRangeInsertedEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

## Hide Rows and Columns

SfSpreadsheet provides support to hide rows/columns and this can be done by [HideRow](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html#Syncfusion_XlsIO_IWorksheet_HideRow_System_Int32_) and [HideColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html#Syncfusion_XlsIO_IWorksheet_HideColumn_System_Int32_) method

{% tabs %}
{% highlight c# %}
//For Hiding Rows,
spreadsheet.ActiveSheet.HideRow(5);
spreadsheet.ActiveGrid.RowHeights.SetHidden(5, 5, true);

//For Hiding Cols,
spreadsheet.ActiveSheet.HideColumn(4);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(4, 4, true);
{% endhighlight %}
{% endtabs %}

## Unhide Rows and Columns

Unhide the rows/columns in SfSpreadsheet can be done by [ShowRow](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html#Syncfusion_XlsIO_IWorksheet_ShowRow_System_Int32_System_Boolean_) and [ShowColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorksheet.html#Syncfusion_XlsIO_IWorksheet_ShowColumn_System_Int32_System_Boolean_) methods.

{% tabs %}
{% highlight c# %}
//For Unhiding Rows,
spreadsheet.ActiveSheet.ShowRow(5, true);
spreadsheet.ActiveGrid.RowHeights.SetHidden(5, 5, false);

//For Unhiding Cols,
spreadsheet.ActiveSheet.ShowColumn(4,true);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(4, 4, false);
{% endhighlight %}
{% endtabs %}

## Row Height and Column Width

SfSpreadsheet provides support to adjust the row height and column width. And also can import the adjusted row height and column width from Excel. SfSpreadsheet provides support to fit the row and column based on its contents.

{% tabs %}
{% highlight c# %}
//For setting RowHeight for 4th Row
spreadsheet.ActiveGrid.SetRowHeight(4, 4, 30);
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Row(4), true);

//For setting ColumnWidth for 5th Column
spreadsheet.ActiveGrid.SetColumnWidth(5, 5, 22);
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Col(5), true);
{% endhighlight %}
{% endtabs %}

N> In case if you insert/delete and hide/unhide the rows/columns inside the Grouping, [RefreshOutlines](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_RefreshOutlines_System_Boolean_System_Boolean_) method must be invoked to refresh/update the Outlines of the Group.	

## Freeze Rows and Columns

SfSpreadsheet provides support for Freeze panes to keep an area of a worksheet visible while you scroll to another area of the worksheet.

{% tabs %}
{% highlight c# %}
//Freeze panes

//To Freeze 4 rows and 4 columns
spreadsheet.Workbook.ActiveSheet.Range[4, 4].FreezePanes();
spreadsheet.ActiveGrid.FrozenRows = 5;
spreadsheet.ActiveGrid.FrozenColumns = 5;
{% endhighlight %}
{% endtabs %}

## Unfreeze Rows and Columns

SfSpreadsheet provides support to unfreeze the freeze panes in the worksheet of SfSpreadsheet.

{% tabs %}
{% highlight c# %}
//Unfreeze panes

//To Unfreeze 4 rows and 4 columns
spreadsheet.Workbook.ActiveSheet.RemovePanes();
spreadsheet.ActiveGrid.FrozenRows = 1;
spreadsheet.ActiveGrid.FrozenColumns = 1;
{% endhighlight %}
{% endtabs %}

## Auto Fit Rows and Columns

SfSpreadsheet provides support to fit the rows or columns based on its content at run time.

You can fit the rows/columns by calling [AutoFitRows](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IRange.html#Syncfusion_XlsIO_IRange_AutofitRows) and  [AutoFitColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IRange.html#Syncfusion_XlsIO_IRange_AutofitColumns) methods of XlsIO’s `IRange`. Also set the adjusted row height and column width into the grid by using [SetRowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SetRowHeight_System_Int32_System_Int32_System_Double_) and [SetColumnWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SetColumnWidth_System_Int32_System_Int32_System_Double_) methods of `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}
//To AutoFit a single column,
spreadsheet.ActiveSheet.AutofitColumn(2);
spreadsheet.ActiveGrid.SetColumnWidth(2,2,spreadsheet.ActiveSheet.GetColumnWidthInPixels(2)); 

//To AutoFit multiple columns,
spreadsheet.ActiveSheet["A1:D100"].AutofitColumns();

for(int i = 1; i <= 4 ; i++)
{
   spreadsheet.ActiveGrid.SetColumnWidth(i,i,spreadsheet.ActiveSheet.GetColumnWidthInPixels(i));
}

//To AutoFit a single row,
spreadsheet.ActiveSheet.AutofitRow(3);
spreadsheet.ActiveGrid.SetRowHeight(3,3,spreadsheet.ActiveSheet.GetRowHeightInPixels(3)); 

//To AutoFit multiple rows,
spreadsheet.ActiveSheet["B1:B5"].AutofitRows();

for(int i = 1; i <= 5 ; i++)
{
   spreadsheet.ActiveGrid.SetRowHeight(i,i,spreadsheet.ActiveSheet.GetRowHeightInPixels(i));
}
{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.