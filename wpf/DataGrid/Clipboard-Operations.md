---
layout: post
title: Clipboard Operations in WPF DataGrid control | Syncfusion®
description: Learn here all about Clipboard Operations support in Syncfusion® WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---


# Clipboard Operations in WPF DataGrid (SfDataGrid)

[WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) (SfDataGrid) provide support for the clipboard operations such as cut, copy and paste the data within control and between other applications such as Notepad, Excel. Clipboard operations copy and paste is enabled by default. You can copy selected records/cells from SfDataGrid by pressing <kbd>Ctrl+C</kbd> and also can paste the content from [Clipboard](https://learn.microsoft.com/en-us/dotnet/api/system.windows.clipboard?view=windowsdesktop-7.0&viewFallbackFrom=net-5.0) to SfDataGrid by pressing <kbd>Ctrl+V</kbd>.

N> Clipboard operations is not supported for the summary rows, add new row and unbound rows.

 
## Copy to Clipboard in DataGrid

Copy operation works based on [GridCopyOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property. 

`GridCopyOption` provides the following options,

* [None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Disables copy in SfDataGrid.

* [CopyData](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Enabled copy in SfDataGrid.

* [IncludeHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Column header also copied along with data.
 
* [IncludeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Copies the display text with format instead of actual value.
 
* [IncludeHiddenColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Hidden column also copied to clipboard.
 
You have to use `IncludeHeaders`, `IncludeFormat`, `IncludeHiddenColumn` options along with `CopyData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridCopyOption="CopyData,IncludeHeaders" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridCopyOption = GridCopyOption.CopyData | GridCopyOption.IncludeHeaders;
{% endhighlight %}
{% endtabs %}

![Copy to Clipboard in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-copy-to-clipboard.png)

N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is [Cell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

## Paste from Clipboard in DataGrid

Paste operation works based on [GridPasteOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridPasteOption) property. 

`GridPasteOption` provides the following options,

* [None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – Disable paste in SfDataGrid.

* [PasteData](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – Enabled paste in SfDataGrid and when an incompatible value is pasted into a record/cell, the pasting operation is skipped for that particular record/cell.

* [ExcludeFirstLine](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – This can be used when pasting data copied with [IncludeHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) copy option.
 
* [IncludeHiddenColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPasteOption.html)  – Paste the values in hidden columns also.

You have to use `ExcludeFirstLine`, `IncludeHiddenColumn` options along with `PasteData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridPasteOption="PasteData,ExcludeFirstLine" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridPasteOption = GridPasteOption.PasteData | GridPasteOption.ExcludeFirstLine;
{% endhighlight %}
{% endtabs %}

![Paste Clipboard Content in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-paste-clipboard.png)

## Cut to Clipboard in DataGrid

Cut operation works based on [GridCopyOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property. 

`GridCopyOption` provides the following options,

* [None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Disables cut in SfDataGrid.

* [CutData](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Enabled cut in SfDataGrid.

* [IncludeHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Column header also copied along with data.
 
* [IncludeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Cut the display text with format instead of actual value.
 
* [IncludeHiddenColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Hidden column also cut to clipboard.
 
You have to use `IncludeHeaders`, `IncludeFormat`, `IncludeHiddenColumn` options along with `CutData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridCopyOption="CutData,IncludeHeaders" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridCopyOption = GridCopyOption.CutData | GridCopyOption.IncludeHeaders;
{% endhighlight %}
{% endtabs %}

![Cut to Clipboard in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-cut-to-clipboard.png)

N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is [Cell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

## Events

### GridCopyContent

[GridCopyContent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when copy/cut the cells in SfDataGrid. [GridCopyPasteEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridCopyContent` event. You can cancel copy operation by handling this event.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyContent += dataGrid_GridCopyContent;

void dataGrid_GridCopyContent(object sender, GridCopyPasteEventArgs e)
{

    if (((e.OriginalSender as SfDataGrid).SelectedItem as OrderInfo).OrderID == 1004)
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

### GridPasteContent

[GridPasteContent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when paste the clipboard value into SfDataGrid. [GridCopyPasteEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridPasteContent` event. You can cancel paste operation by handling this event.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridPasteContent+=dataGrid_GridPasteContent;

void dataGrid_GridPasteContent(object sender, GridCopyPasteEventArgs e)
{

    if (((e.OriginalSender as SfDataGrid).SelectedItem as OrderInfo).OrderID == 1010)
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

### CopyGridCellContent

[CopyGridCellContent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when cell being copy/cut. [GridCopyPasteCellEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `CopyGridCellContent` event, which has following members,

* [ClipBoardValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_ClipBoardValue) - Returns cell value.

* [Column](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_Column) – Returns corresponding GridColumn of a cell.

* [RowData](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_RowData) – Returns corresponding RowData of a cell.

* [OriginalSender](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridEventArgs.html#Syncfusion_UI_Xaml_Grid_GridEventArgs_OriginalSender) – Returns the SfDataGrid.

You can change the text copied to clipboard by changing the `ClipBoardValue`.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.CopyGridCellContent += dataGrid_CopyGridCellContent;

void dataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

The below code example change the clipboard value as 100 instead of cell value 1003 in SfDataGrid.

{% tabs %}
{% highlight c# %}
void dataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "OrderID" && (e.RowData as OrderInfo).OrderID == 1003)
        e.ClipBoardValue = 100;
}
{% endhighlight %}
{% endtabs %}

![Copy to Clipboard based on Cell Value in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-copy-cell-value.png)

The below code example handled the copy operation when `MappingName` of a Column is Country.

{% tabs %}
{% highlight c# %}
void dataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "Country")
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

![Copy to Clipboard based on Mapping Name in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-copy-mapping-name.png)

N> When [GridCopyOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) with [IncludeHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyOption.html) (CopyData, IncludeHeaders / CutData, IncludeHeaders), the `CopyGridCellContent` event also fires for header rows, causing e.RowData to be `null`.
With CopyData or CutData (without headers), the event fires only for data rows, and RowData is populated correctly.

### PasteGridCellContent

[PasteGridCellContent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when cell being paste. [GridCopyPasteCellEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `PasteGridCellContent` event, which has following members.

* [ClipBoardValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_ClipBoardValue) - Returns clipboard value of a particular cell.

* [Column](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_Column) – Returns corresponding GridColumn of a cell.

* [RowData](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_RowData) – Returns corresponding RowData of a cell.

* [OriginalSender](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridEventArgs.html#Syncfusion_UI_Xaml_Grid_GridEventArgs_OriginalSender) – Returns the SfDataGrid.

You can change the text paste to SfDataGrid by changing the `ClipBoardValue`.

{% tabs %}
{% highlight c# %}
this.dataGrid.PasteGridCellContent += dataGrid_PasteGridCellContent;

void dataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}


The below code example change the clipboard value as Test instead of clipboard value BOLID.

{% tabs %}
{% highlight c# %}
void dataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "CustomerID" && (e.RowData as OrderInfo).CustomerID == "BERGS")
        e.ClipBoardValue = "Test";
}
{% endhighlight %}
{% endtabs %}

![Paste Clipboard Content based on Cell Value in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-paste-cell-value.png)

The below code example handled the paste operation when `MappingName` of Column is OrderID

{% tabs %}
{% highlight c# %}
void dataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "OrderID")
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

![Paste Clipboard Content based on Mapping Name in WPF DataGrid](Clipboard-Operations_images/wpf-datagrid-paste-mapping-name.png)

## Handling Programmatically

### Programmatically Copy to Clipboard in WPF DataGrid

Copy the selected records/cells in SfDataGrid by using [Copy](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Copy) method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy a record by selecting the record using [MoveCurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridBaseSelectionController.html#Syncfusion_UI_Xaml_Grid_GridBaseSelectionController_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method and `Copy` method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
RowColumnIndex rowColumnIndex = new RowColumnIndex();
rowColumnIndex.RowIndex = 2;
rowColumnIndex.ColumnIndex = 2;
this.dataGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple records by selecting group of records using [SelectRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridBaseSelectionController.html#Syncfusion_UI_Xaml_Grid_GridBaseSelectionController_SelectedRows) method and `Copy` method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectRows(1, 7);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple cells by selecting group of cells using [SelectCells](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectCells_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) method and `Copy` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectCells(this.dataGrid.GetRowGenerator().Items[2].RowData, this.dataGrid.Columns[1], this.dataGrid.GetRowGenerator().Items[5].RowData, this.dataGrid.Columns[3]);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

### Copy rows without selecting in WPF DataGrid

You can copy the records without selection by using [CopyRowsToClipboard](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_CopyRowsToClipboard_System_Int32_System_Int32_) method in `GridCopyPaste` of SfDataGrid.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.CopyRowsToClipboard(2, 4);
{% endhighlight %}
{% endtabs %}

### Programmatically Cut Data to Clipboard in WPF DataGrid

Cut the selected records/cells in SfDataGrid by using [Cut](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Cut) method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire record in SfDataGrid by selecting whole SfDataGrid using [SelectAll](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectAll_System_Boolean_) method and `Cut` method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectAll();
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire column in SfDataGrid by using [SelectCells](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectCells_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) method and `Cut` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
var firstRowData = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetFirstRowIndex());
var lastRowData = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetLastRowIndex());
this.dataGrid.SelectCells(firstRowData, this.dataGrid.Columns[2], lastRowData, this.dataGrid.Columns[2]);
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

### Programmatically Paste in DataGrid   

Paste the clipboard value into SfDataGrid by using [Paste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Paste) method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Paste();
{% endhighlight %}
{% endtabs %}

Paste the clipboard value into selected record by selecting the record using [MoveCurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridBaseSelectionController.html#Syncfusion_UI_Xaml_Grid_GridBaseSelectionController_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method and `Paste` method in [GridCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
RowColumnIndex rowColumnIndex = new RowColumnIndex();
rowColumnIndex.RowIndex = 1;
rowColumnIndex.ColumnIndex = 1;
this.dataGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
this.dataGrid.GridCopyPaste.Paste();
{% endhighlight %}
{% endtabs %}

## Customizing Copy Paste Behavior in WPF DataGrid

WPF DataGrid (SfDataGrid) process the clipboard operations in [GridCutCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. You can customize the default copy paste behaviors by overriding `GridCutCopyPaste` class and set it to `SfDataGrid.GridCopyPaste`.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid sfGrid) : base(sfGrid)
    {        
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
public MainWindow()
{
    InitializeComponent();
    this.dataGrid.GridCopyPaste = new CustomCopyPaste(this.dataGrid);
}
{% endhighlight %}
{% endtabs %}

### Paste a cell into many cells in WPF DataGrid

By default, you can copy one cell and paste it into another cell when Cell Selection is enabled in SfDataGrid. The below code shows how to copy one cell and paste it into all the selected cells by overriding [PasteToCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToCell_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_) method in [GridCutCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    protected override void PasteToCell(object record, GridColumn column, object value)
    {
        var text = Clipboard.GetText();
        
        string[] clipBoardText = Regex.Split(text, @"\r\n");
        
        clipBoardText = Regex.Split(clipBoardText[0], @"\t");

        //Get the clipBoardText and check if the clipBoardText is more than one cell

        //means call the base.

        if (clipBoardText.Count() > 1)
        {
            base.PasteToCell(record, column, value);
        }
        
        //Get the selectedCells for paste the copied cell 
        var selectedCells = this.dataGrid.GetSelectedCells();
        int selectedCellsCount = selectedCells.Count;
        
        for (int i = 0; i < selectedCellsCount; i++)
        {
            record = selectedCells[i].RowData;
            
            column = selectedCells[i].Column;
            
            //Call PasteToCell method with particular record of selectedCells,

            //Column of selected records and rowData

            if (record != null && column != null)
                base.PasteToCell(record, column, value);
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Paste a record into many rows in WPF DataGrid

By default, you can able to copy one row and paste it into another row when Row Selection is enabled in SfDataGrid. The below code shows how to copy one row and paste it into all selected rows by overriding the [PasteToRow](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRow_System_Object_System_Object_) method in the [GridCutCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    protected override void PasteToRow(object clipBoardContent, object selectedRecords)
    {
        var text = Clipboard.GetText();
        string[] clipBoardText = Regex.Split(text, @"\r\n");

        //Get the clipBoardText and check if the clipBoardText is more than one row

        //means call the base.

        if (clipBoardText.Count() > 1)
        {
            base.PasteToRow(clipBoardContent, selectedRecords);
            return;
        }

        var selectedRecord = this.dataGrid.SelectedItems;
        
        for (int i = 0; i < selectedRecord.Count; i++)
        {
            //Get the selected records for paste the copied row.
            selectedRecords = selectedRecord[i];
            
            //Call the PasteToRow method with clipBoardContent and selectedRecords
            base.PasteToRow(clipBoardContent, selectedRecords);
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Select pasted records in WPF DataGrid

By default after pasting the clipboard value to SfDataGrid selection is maintains in previously selected records as it is. The below code shows select the pasted records after the Paste operation, by overriding the [PasteToRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRows_System_Object_) and [PasteToRow](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRow_System_Object_System_Object_) methods in [GridCutCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. This code is applicable when [SelectionUnit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionUnit) is [Row](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    //Creating the new list for add the selected records
    public List<object> selectedItem = new List<object>();

    protected override void PasteToRows(object clipBoardRows)
    {
        base.PasteToRows(clipBoardRows);
        
        //Using the SelectionController apply the selection for Pasted records
        this.dataGrid.SelectionController.HandleGridOperations(new GridOperationsHandlerArgs(GridOperation.Paste, selectedItem));
    }

    protected override void PasteToRow(object clipBoardContent, object selectedRecords)
    {

        //Added the selected record to list
        selectedItem.Add(selectedRecords);
        
        base.PasteToRow(clipBoardContent, selectedRecords);
    }
}
{% endhighlight %}
{% endtabs %}

### Create new records while pasting in WPF DataGrid

By default while paste the clipboard value to SfDataGrid, it changes the values of the already existing records. The below code example shows how to add the copied records as new rows in SfDataGrid by overriding the [PasteToRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRows_System_Object_) method in [GridCutCopyPaste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid)
        : base(dataGrid)
    {
    }
        
    protected override void PasteToRows(object clipBoardRows)
    {
        var copiedRecord = (string[])clipBoardRows;
        int copiedRecordsCount = copiedRecord.Count();

        //Based on the clipboard count added the new record for paste
 
        if (copiedRecordsCount > 0)
        {
            //Get the viewModel for adding the record
            var record = this.dataGrid.DataContext as ViewModel;
            
            for (int i = 0; i < copiedRecordsCount; i++)
            {
                //Create the new instance for Model, for adding the new record
                OrderInfo entity = new OrderInfo();
                
                for (int j = 0; j < this.dataGrid.Columns.Count; j++)
                {
                    string[] values = Regex.Split(copiedRecord[i], @"\t");

                    //Adding the new record by using PasteToCell method by passing the 
 
                    //created data, particular column, and clipboard value
                    this.PasteToCell(entity, this.dataGrid.Columns[j], values[j]);
                }
 
                //Added the pasted record in collection
                record.Orders.Add(entity);
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

## See Also

[How to copy active cell value alone when SelectionUnit as Row](https://support.syncfusion.com/kb/article/8778/how-to-copy-active-cell-value-alone-when-row-selection-in-wpf-datagrid-sfdatagrid)

[How to paste the copied row in AddNewRow?](https://support.syncfusion.com/kb/article/6325/how-to-paste-the-copied-row-in-addnewrow-in-wpf-datagrid-sfdatagrid)

[How to paste the empty string while using Cell selection?](https://support.syncfusion.com/kb/article/6095/how-to-paste-the-empty-string-while-using-cell-selection-in-wpf-datagrid-sfdatagrid)

[How to paste the data by custom column order instead of the first column in the SfDataGrid when SelectionUnit is a Row?](https://support.syncfusion.com/kb/article/5159/how-to-paste-the-data-by-custom-column-order-instead-of-the-first-column-in-the-sfdatagrid)

[How to add the copied rows as new rows in the SfDataGrid while pasting?](https://support.syncfusion.com/kb/article/4640/how-to-add-the-copied-rows-as-new-rows-in-wpf-datagrid-while-pasting)

[How to copy one row and paste it into all the selected rows like Excel in the SfDataGrid?](https://support.syncfusion.com/kb/article/4500/how-to-copy-one-row-and-paste-it-into-all-the-selected-rows-like-excel-in-the-wpf-sfdatagrid)

[How to copy one cell and paste it into all the selected cells in the SfDataGrid like the Excel?](https://support.syncfusion.com/kb/article/4484/how-to-copy-one-cell-and-paste-it-into-all-the-selected-cells-in-the-sfdatagrid-like-the-excel-in-wpf-)

[How to copy the column and paste it as a new column by ContextMenu in SfDataGrid?](https://support.syncfusion.com/kb/article/3439/how-to-copy-the-column-and-paste-it-as-a-new-column-by-contextmenu-in-sfdatagrid)

