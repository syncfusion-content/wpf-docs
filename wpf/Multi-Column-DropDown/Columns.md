---
layout: post
title: Defining columns of Multi-Column Dropdown |  | Syncfusion
description: Learn about columns and its auto generate supports in Syncfusion WPF SfMultiColumnDropDownControl (Multicolumn ComboBox) control and more details.
platform: wpf
control: SfMultiColumnDropDownControl
documentation: ug
---

# Columns in SfMultiColumnDropDownControl

SfMultiColumnDropDownControl enables you to define the columns as like in SfDataGrid. You can let the `SfMultiColumnDropDownControl` to create columns or you can manually defined columns to de displayed. Below sections explains both ways,
 
    1. Automatically generating columns
    2. Manually define columns
    
## Automatically generating columns

The automatic column generation based on properties of data object can be enabled or disabled by setting [SfMultiColumnDropDownControl.AutoGenerateColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_AutoGenerateColumns). 
You can [refer here](http://help.syncfusion.com/wpf/sfdatagrid/columns#defining-columns) to know more about the automatic column generation in SfMultiColumnDropDownControl.

## Manually defining columns

SfMultiColumnDropDownControl control allows you to define the columns manually by adding desired column to the [SfMultiColumnDropDownControl.Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_Columns) collection.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfMultiColumn"
                                         Width="175"
                                         Height="30"
                                         AutoGenerateColumns="false"
                                         DisplayMember="OrderID"
                                         ItemsSource="{Binding Orders}"
                                         SelectedIndex="0"
                                         ValueMember="OrderID">
    <syncfusion:SfMultiColumnDropDownControl.Columns>
        <syncfusion:GridCurrencyColumn MappingName="OrderID" />
        <syncfusion:GridTextColumn MappingName="CustomerID" />
        <syncfusion:GridTextColumn MappingName="Country" />
    </syncfusion:SfMultiColumnDropDownControl.Columns>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% highlight c# %}
SfMultiColumnDropDownControl sfMultiColumn = new SfMultiColumnDropDownControl();
sfMultiColumn.AutoGenerateColumns = false;
sfMultiColumn.Columns.Add(new GridCurrencyColumn() { MappingName = “OrderID” });
sfMultiColumn.Columns.Add(new GridTextColumn() { MappingName = “CustomerID” });
sfMultiColumn.Columns.Add(new GridTextColumn() { MappingName = “Country” });
{% endhighlight %}
{% endtabs %}

![Manually generated the columns in WPF SfMultiColumnDropDown](Columns_images/Columns_img1.png)

### Customize auto-generated columns

You can customize or cancel the generated column by handling [AutoGeneratingColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_AutoGeneratingColumn) event. `AutoGeneratingColumn` event occurs when the individual column is auto-generated for public and non-static property of underlying data object.

{% tabs %}
{% highlight c# %}
this.SfMultiColumn.AutoGeneratingColumn += SfMultiColumn_AutoGeneratingColumn;

private void SfMultiColumn_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
		
}
{% endhighlight %}
{% endtabs %}

[AutoGeneratingColumnArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html) provides the information about the auto-generated column to the `AutoGeneratingColumn` event. [AutoGeneratingColumnArgs.Column](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html#Syncfusion_UI_Xaml_Grid_AutoGeneratingColumnArgs_Column) property returns the newly created column.

### Cancel column generation for particular property

You can cancel the auto generation of specific column by handling `AutoGeneratingColumn` event.

In the below code, column generation for `OrderID` property is canceled by setting `Cancel` property to `true`. 

{% tabs %}
{% highlight c# %}
this.SfMultiColumn.AutoGeneratingColumn += SfMultiColumn_AutoGeneratingColumn;

private void SfMultiColumn_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
	if (e.Column.MappingName == "OrderID")
	{
		e.Cancel = true;
    }		
}
{% endhighlight %}
{% endtabs %}

### Changing column type

You can change the column type while auto generation by setting the instance of column with type you want to add in `AutoGeneratingColumn` event.

In the below code, column type for `UnitPrice` property is changed to `GridTextColumn` by setting instance of GridTextColumn to `Column` property. 

{% tabs %}
{% highlight c# %}
this.SfMultiColumn.AutoGeneratingColumn += SfMultiColumn_AutoGeneratingColumn;

private void SfMultiColumn_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
	if (e.Column.MappingName == "UnitPrice")
	{
		if (e.Column is GridNumericColumn)
        {
            e.Column = new GridTextColumn() { MappingName = "UnitPrice", HeaderText = "Unit Price" };
        }       
    }
}     
{% endhighlight %}
{% endtabs %}

### Changing property settings

You can change the column properties in `AutoGeneratingColumn` event handler. 

{% tabs %}
{% highlight c# %}
this.SfMultiColumn.AutoGeneratingColumn += SfMultiColumn_AutoGeneratingColumn;

private void SfMultiColumn_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
	if (e.Column.MappingName=="OrderID")
	{
		e.Column.AllowEditing = false;
		e.Column.AllowSorting = true;
		e.Column.AllowFiltering = true;
		e.Column.AllowGrouping = false;
		e.Column.AllowFocus = true;
		e.Column.AllowResizing = false;
		e.Column.ColumnSizer = GridLengthUnitType.Auto;
		e.Column.AllowDragging = true;        
	}	
}
{% endhighlight %}
{% endtabs %}

### Setting template to auto-generated column

You can set [GridColumn.HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_HeaderTemplate) and [GridColumn.CellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellTemplate) properties for auto-generated column in `AutoGeneratingColumn` event handler. 

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <DataTemplate x:Key="headerTemplate">
        <TextBlock Text="{Binding}" TextWrapping="Wrap" Foreground="Red"/>
    </DataTemplate>
</Window.Resources>
{% endhighlight %}
{% highlight c# %}
this.SfMultiColumn.AutoGeneratingColumn += SfMultiColumn_AutoGeneratingColumn;

private void SfMultiColumn_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
	if (e.Column.MappingName == "Country")
	{
		e.Column.HeaderTemplate = this.FindResource("headerTemplate") as DataTemplate;
	}
}
{% endhighlight %}
{% endtabs %}

Below screenshot shows the customized header template loaded on the header of Country column.

![WPF datagrid shows customized header template loaded on the header of Country column](Columns_images/Columns_img3.png)


## Column sizing

You can also set the column width based on certain logic by setting [SfMultiColumnDropDownControl.GridColumnSizer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfMultiColumnDropDownControl.html#Syncfusion_UI_Xaml_Grid_SfMultiColumnDropDownControl_GridColumnSizer). You can refer here to know more about the [GridColumn.ColumnSizer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_ColumnSizer).
In the below code, `GridLengthUnitType.Star` is sets as `GridColumnSizer` for equally sets the column widths.

You can [refer here](http://help.syncfusion.com/wpf/sfdatagrid/columns#column-sizing) to know more about the column sizing.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMultiColumnDropDownControl x:Name="sfMultiColumn"
                                         Width="175"
                                         Height="25"                                            
                                         AutoGenerateColumns="False"
                                         DisplayMember="Title"
                                         GridColumnSizer="Star"
                                         ItemsSource="{Binding MoviesLists}"
                                         SelectedIndex="2"
                                         ValueMember="Title">
    <syncfusion:SfMultiColumnDropDownControl.Columns>
        <syncfusion:GridTextColumn MappingName="Title" />
        <syncfusion:GridTextColumn MappingName="Cast" />
        <syncfusion:GridTextColumn MappingName="Director" />
        <syncfusion:GridTextColumn MappingName="Rating" />
    </syncfusion:SfMultiColumnDropDownControl.Columns>
</syncfusion:SfMultiColumnDropDownControl>
{% endhighlight %}
{% endtabs %}

![Change column size in WPF SfMuliColumnDropDown](Columns_images/Columns_img2.png)

