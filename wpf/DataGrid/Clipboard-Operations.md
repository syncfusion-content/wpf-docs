---
layout: post
title: Clipboard operations in WPF DataGrid control | Syncfusion
description: Learn about clipboard (cut, copy and paste) operations in Syncfusion WPF DataGrid (SfDataGrid) control and more details. 
platform: wpf
control: SfDataGrid
documentation: ug
---


# Clipboard Operations in WPF DataGrid (SfDataGrid)

SfDataGrid provide support for the clipboard operations such as cut, copy and paste the data within control and between other applications such as Notepad, Excel. Clipboard operations copy and paste is enabled by default. You can copy selected records/cells from SfDataGrid by pressing <kbd>Ctrl+C</kbd> and also can paste the content from [Clipboard](https://msdn.microsoft.com/en-us/library/system.windows.clipboard.aspx) to SfDataGrid by pressing <kbd>Ctrl+V</kbd>.

N> Clipboard operations is not supported for the summary rows, add new row and unbound rows.

 
## Copy to Clipboard in DataGrid

Copy operation works based on [GridCopyOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property. 

`GridCopyOption` provides the following options,

* [None](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Disables copy in SfDataGrid.

* [CopyData](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Enabled copy in SfDataGrid.

* [IncludeHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Column header also copied along with data.
 
* [IncludeFormat](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Copies the display text with format instead of actual value.
 
* [IncludeHiddenColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Hidden column also copied to clipboard.
 
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

![Displaying copy operation with GridCopyOption from WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img1.png)

N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is [Cell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

## Paste from Clipboard in DataGrid

Paste operation works based on [GridPasteOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridPasteOption) property. 

`GridPasteOption` provides the following options,

* [None](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – Disable paste in SfDataGrid.

* [PasteData](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – Enabled paste in SfDataGrid and when an incompatible value is pasted into a record/cell, the pasting operation is skipped for that particular record/cell.

* [ExcludeFirstLine](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridPasteOption.html) – This can be used when pasting data copied with [IncludeHeader](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) copy option.
 
* [IncludeHiddenColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridPasteOption.html)  – Paste the values in hidden columns also.

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

![Displaying paste operation with GridPasteOption in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img2.png)

## Cut to Clipboard in DataGrid

Cut operation works based on [GridCopyOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property. 

`GridCopyOption` provides the following options,

* [None](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Disables cut in SfDataGrid.

* [CutData](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Enabled cut in SfDataGrid.

* [IncludeHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Column header also copied along with data.
 
* [IncludeFormat](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Cut the display text with format instead of actual value.
 
* [IncludeHiddenColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyOption.html) – Hidden column also cut to clipboard.
 
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

![Displaying Cut operation with GridCopyOption in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img3.png)

N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is [Cell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

## Events

### GridCopyContent

[GridCopyContent](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyContent_EV.html) event occurs when copy/cut the cells in SfDataGrid. [GridCopyPasteEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridCopyContent` event. You can cancel copy operation by handling this event.

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

[GridPasteContent](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridPasteContent_EV.html) event occurs when paste the clipboard value into SfDataGrid. [GridCopyPasteEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridPasteContent` event. You can cancel paste operation by handling this event.

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

[CopyGridCellContent](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~CopyGridCellContent_EV.html) event occurs when cell being copy/cut. [GridCopyPasteCellEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `CopyGridCellContent` event, which has following members,

* [ClipBoardValue](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~ClipBoardValue.html) - Returns cell value.

* [Column](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~Column.html) – Returns corresponding GridColumn of a cell.

* [RowData](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~RowData.html) – Returns corresponding RowData of a cell.

* [OriginalSender](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridEventArgs~OriginalSender.html) – Returns the SfDataGrid.

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

![Displaying copy operation using CopyGridCellContent event based on cell value in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img4.png)

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

![Displaying copy operation using CopyGridCellContent event based on mapping name in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img5.png)

### PasteGridCellContent

[PasteGridCellContent](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~PasteGridCellContent_EV.html) event occurs when cell being paste. [GridCopyPasteCellEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `PasteGridCellContent` event, which has following members.

* [ClipBoardValue](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~ClipBoardValue.html) - Returns clipboard value of a particular cell.

* [Column](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~Column.html) – Returns corresponding GridColumn of a cell.

* [RowData](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs~RowData.html) – Returns corresponding RowData of a cell.

* [OriginalSender](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridEventArgs~OriginalSender.html) – Returns the SfDataGrid.

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

![Displaying paste operation using PasteGridCellContent event based on cell value in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img6.png)

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

![Displaying paste operation using PasteGridCellContent event based on mapping name in WPF SfDataGrid](Clipboard-Operations_images/Clipboard-Operations_img7.png)

## Handling Programmatically

### Programmatically Copy to Clipboard in WPF DataGrid

Copy the selected records/cells in SfDataGrid by using [Copy](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~Copy.html) method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy a record by selecting the record using [MoveCurrentCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridBaseSelectionController~MoveCurrentCell.html) method and `Copy` method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
RowColumnIndex rowColumnIndex = new RowColumnIndex();
rowColumnIndex.RowIndex = 2;
rowColumnIndex.ColumnIndex = 2;
this.dataGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple records by selecting group of records using [SelectRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridBaseSelectionController~SelectedRows.html) method and `Copy` method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectRows(1, 7);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple cells by selecting group of cells using [SelectCells](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~SelectCells.html) method and `Copy` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectCells(this.dataGrid.GetRowGenerator().Items[2].RowData, this.dataGrid.Columns[1], this.dataGrid.GetRowGenerator().Items[5].RowData, this.dataGrid.Columns[3]);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

### Copy rows without selecting in WPF DataGrid

You can copy the records without selection by using [CopyRowsToClipboard](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~CopyRowsToClipboard.html) method in `GridCopyPaste` of SfDataGrid.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.CopyRowsToClipboard(2, 4);
{% endhighlight %}
{% endtabs %}

### Programmatically Cut Data to Clipboard in WPF DataGrid

Cut the selected records/cells in SfDataGrid by using [Cut](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~Cut.html) method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire record in SfDataGrid by selecting whole SfDataGrid using [SelectAll](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~SelectAll.html) method and `Cut` method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectAll();
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire column in SfDataGrid by using [SelectCells](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~SelectCells.html) method and `Cut` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
var firstRowData = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetFirstRowIndex());
var lastRowData = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetLastRowIndex());
this.dataGrid.SelectCells(firstRowData, this.dataGrid.Columns[2], lastRowData, this.dataGrid.Columns[2]);
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

### Programmatically Paste in DataGrid   

Paste the clipboard value into SfDataGrid by using [Paste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~Paste.html) method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Paste();
{% endhighlight %}
{% endtabs %}

Paste the clipboard value into selected record by selecting the record using [MoveCurrentCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridBaseSelectionController~MoveCurrentCell.html) method and `Paste` method in [GridCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GridCopyPaste.html) of SfDataGrid.

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

SfDataGrid process the clipboard operations in [GridCutCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. You can customize the default copy paste behaviors by overriding `GridCutCopyPaste` class and set it to `SfDataGrid.GridCopyPaste`.

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

By default, you can copy one cell and paste it into another cell when Cell Selection is enabled in SfDataGrid. The below code shows how to copy one cell and paste it into all the selected cells by overriding [PasteToCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~PasteToCell.html) method in [GridCutCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

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

By default, you can able to copy one row and paste it into another row when Row Selection is enabled in SfDataGrid. The below code shows how to copy one row and paste it into all selected rows by overriding the [PasteToRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~PasteToRow.html) method in the [GridCutCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

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

By default after pasting the clipboard value to SfDataGrid selection is maintains in previously selected records as it is. The below code shows select the pasted records after the Paste operation, by overriding the [PasteToRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~PasteToRows.html) and [PasteToRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~PasteToRow.html) methods in [GridCutCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. This code is applicable when [SelectionUnit](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~SelectionUnit.html) is [Row](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSelectionUnit.html).

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

By default while paste the clipboard value to SfDataGrid, it changes the values of the already existing records. The below code example shows how to add the copied records as new rows in SfDataGrid by overriding the [PasteToRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste~PasteToRows.html) method in [GridCutCopyPaste](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.

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

[How to copy active cell value alone when SelectionUnit as Row](https://www.syncfusion.com/kb/9913)

[How to paste the copied row in AddNewRow?](https://www.syncfusion.com/kb/6865)

[How to paste the empty string while using Cell selection?](https://www.syncfusion.com/kb/6699)

[How to paste the data by custom column order instead of the first column in the SfDataGrid when SelectionUnit is a Row?](https://www.syncfusion.com/kb/5321)

[How to add the copied rows as new rows in the SfDataGrid while pasting?](https://www.syncfusion.com/kb/4812)

[How to copy one row and paste it into all the selected rows like Excel in the SfDataGrid?](https://www.syncfusion.com/kb/4710)

[How to copy one cell and paste it into all the selected cells in the SfDataGrid like the Excel?](https://www.syncfusion.com/kb/4678)

[How to copy the column and paste it as a new column by ContextMenu in SfDataGrid?](https://www.syncfusion.com/kb/3245)

