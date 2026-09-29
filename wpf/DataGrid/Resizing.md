---
layout: post
title: Resizing in WPF Data Grid | Syncfusion®
description: Resizing in Data Grid supports column and row resizing, resizing of hidden columns and rows, and disabling resizing for specific columns and rows.
platform: wpf
control: Data Grid
documentation: ug
appliesto: UI Component Suite, Grid SDK
---

# Resizing in WPF Data Grid

[WPF SfDataGrid](https://www.syncfusion.com/wpf-controls/datagrid) supports resizing both the columns and rows. You can resize the column width by dragging the column header grid line, and you can resize the row height by dragging the bottom edge of the supported rows. The hidden columns and rows can also be resized and restored through the resize indicator when the corresponding hidden resizing option is enabled.

## DataGrid column resizing 

SfDataGrid allows to resize the columns like in excel by resizing column header. This can be enabled or disabled by setting [SfDataGrid.AllowResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingColumns) or [GridColumn.AllowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

You can change the column width by clicking and dragging the resizing cursor at the edge of column header. The resizing cursor appears when you hover the grid line exists between two columns. 

![Column Resizing](columns_images/wpf-datagrid-resize-column.png)

N> Resizing considers MinWidth and MaxWidth of column.

### Hidden column resizing

SfDataGrid shows indication for hidden columns in column header and also allows end-users to resize the hidden columns when setting [SfDataGrid.AllowResizingHiddenColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingHiddenColumns) property to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingColumns="True"
                        AllowResizingHiddenColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

![Resizing Hidden Column](columns_images/wpf-datagrid-resize-hidden-column.png)

### Disable column resizing

You can cancel resizing of particular column by setting [GridColumn.AllowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property to `false`. In another way, you can cancel the resizing by handling [SfDataGrid.ResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ResizingColumns) event. The `ResizingColumns` event occurs when you start dragging by resizing cursor on headers.
[ResizingColumnsEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html) of `ResizingColumns` provides information about the columns’s index and width. 

{% tabs %}
{% highlight c# %}
this.dataGrid.ResizingColumns += dataGrid_ResizingColumns;

void dataGrid_ResizingColumns(object sender, ResizingColumnsEventArgs e)
{    

    if(e.ColumnIndex == 1)            
        e.Cancel = true;         
}
{% endhighlight %}
{% endtabs %}

### Identify resizing of the column gets completed

SfDataGrid allows you to identify the progress of the resizing of columns through [ResizingColumnsEventArgs.Reason](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Reason) property. You can get the width of the column after resizing completed by getting [ResizingColumnsEventArgs.Width](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Width) when `ResizingColumnsEventArgs.Reason` is [ColumnResizingReason.Resized](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ColumnResizingReason.html#Syncfusion_UI_Xaml_Grid_ColumnResizingReason_Resized) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.ResizingColumns += OnResizingColumns;

void OnResizingColumns(object sender, ResizingColumnsEventArgs e)
{
    if (e.Reason == Syncfusion.UI.Xaml.Grid.ColumnResizingReason.Resized)
    {
        var resizedWidth = e.Width;
    }
}
{% endhighlight %}
{% endtabs %}

## DataGrid row resizing

SfDataGrid allows to resize the rows by dragging the bottom edge of supported rows. This can be enabled or disabled by setting [SfDataGrid.AllowResizingRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowResizingRows) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingRows="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

You can change the row height by clicking and dragging the resizing cursor at the bottom edge of the row. The resizing cursor appears when you hover the bottom edge of a supported row. 

![Row Resizing](resize_images/wpf-datagrid-resize-row.png)

N> Header rows and stacked header rows cannot be resized.

### Hidden row resizing

SfDataGrid shows indication for hidden rows and also allows end-users to resize and restore the hidden rows when setting [SfDataGrid.AllowResizingHiddenRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowResizingHiddenRows) property to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"                        
                        AllowResizingRows="True"
                        AllowResizingHiddenRows="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

![Resizing Hidden Row](resize_images/wpf-datagrid-resize-hidden-row.png)

### Disable row resizing

You can cancel the resizing of a particular row by handling [SfDataGrid.RowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_RowResizing) event. The `RowResizing` event occurs when you start dragging by resizing cursor at the bottom edge of the row.
[RowResizingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.RowResizingEventArgs.html) of `RowResizing` provides information about the row’s index, data, and height. 

{% tabs %}
{% highlight c# %}
this.dataGrid.RowResizing += dataGrid_RowResizing;

void dataGrid_RowResizing(object sender, Syncfusion.UI.Xaml.Grid.RowResizingEventArgs e)
{    

    if(e.RowIndex == 1)            
        e.Cancel = true;         
}
{% endhighlight %}
{% endtabs %}

### Identify resizing of the row gets completed

SfDataGrid allows you to identify the progress of the resizing of rows through [RowResizingEventArgs.Reason](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.RowResizingEventArgs.html#Syncfusion_UI_Xaml_Grid_RowResizingEventArgs_Reason) property. You can get the height of the row after resizing completed by getting [RowResizingEventArgs.Height](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.RowResizingEventArgs.html#Syncfusion_UI_Xaml_Grid_RowResizingEventArgs_Height) when `RowResizingEventArgs.Reason` is [RowResizingReason.Resized](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.RowResizingReason.html#Syncfusion_UI_Xaml_Grid_RowResizingReason_Resized) in [RowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_RowResizing) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.RowResizing += OnRowResizing;

void OnRowResizing(object sender, Syncfusion.UI.Xaml.Grid.RowResizingEventArgs e)
{
    if (e.Reason == Syncfusion.UI.Xaml.Grid.RowResizingReason.Resized)
    {
        var resizedHeight = e.Height;
    }
}
{% endhighlight %}
{% endtabs %}