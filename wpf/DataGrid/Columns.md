---
layout: post
title: Columns in WPF DataGrid control | Syncfusion
description: Learn here all about Columns support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Columns in WPF DataGrid (SfDataGrid)

SfDataGrid allows you to add or remove columns using [SfDataGrid.Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) property. You can choose the columns to be added from built-in column types or you can create your own column and add to the `SfDataGrid.Columns`.

Below are the built-in column types supported in SfDataGrid. Each column has its own properties to handle different types of data.

<table>
<tr>
<th>
Column Type
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
{{'[GridTextColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridTextColumn.html)'| markdownify }}
</td>
<td>
Use to display the string data. 
</td>
</tr>
<tr>
<td>
{{'[GridNumericColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridNumericColumn.html)'| markdownify }}
</td>
<td>
Use to display the numeric data.
</td>
</tr>
<tr>
<td>
{{'[GridCurrencyColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCurrencyColumn.html)'| markdownify }}
</td>
<td>
Use to display the currency value.
</td>
</tr>
<tr>
<td>
{{'[GridPercentColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPercentColumn.html)'| markdownify }}
</td>
<td>
Use to display the percent value
</td>
</tr>
<tr>
<td>
{{'[GridMaskColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridMaskColumn.html)'| markdownify }}
</td>
<td>
Use to display the data to be masked.
</td>
</tr>
<tr>
<td>
{{'[GridTimeSpanColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridTimeSpanColumn.html)'| markdownify }}
</td>
<td>
Use to display the time span value
</td>
</tr>
<tr>
<td>
{{'[GridDateTimeColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridDateTimeColumn.html)'| markdownify }}
</td>
<td>
Use to display the date time value 
</td>
</tr>
<tr>
<td>
{{'[GridComboBoxColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridComboBoxColumn.html)'| markdownify }}
</td>
<td>
Use to display the IEnumerable data using ComboBox.
</td>
</tr>
<tr>
<td>
{{'[GridCheckBoxColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCheckBoxColumn.html)'| markdownify }}
</td>
<td>
Use to display the boolean type data
</td>
</tr>
<tr>
<td>
{{'[GridImageColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridImageColumn.html)'| markdownify }}
</td>
<td>
Use to display the image in each row.
</td>
</tr>
<tr>
<td>
{{'[GridHyperlinkColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridHyperlinkColumn.html)'| markdownify }}
</td>
<td>
Use to display the Uri data
</td>
</tr>
<tr>
<td>
{{'[GridTemplateColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridTemplateColumn.html)'| markdownify }}
</td>
<td>
Use to display the custom template-specified content.
</td>
</tr>
<tr>
<td>
{{'[GridUnboundColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html)'| markdownify }}
</td>
<td>
Use to display custom information of each record.
</td>
</tr>
<tr>
<td>
{{'[GridMultiColumnDropDownList](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridMultiColumnDropDownList.html)'| markdownify }}
</td>
<td>
Use to display the IEnumerable data using SfMultiColumnDropdownControl.
</td>
</tr>
</table>

## Defining columns

You can let the SfDataGrid to create columns or you can manually define columns to be displayed. Below sections explains both ways, 

1. Automatically generating columns
2. Manually define columns

### Automatically generating columns

The automatic column generation based on properties of data object can be enabled or disabled by setting [SfDataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumns). Default value is `true`.

Columns are generated based on type of property. For example, [GridNumericColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridNumericColumn.html) is added for `int` type property. Below are table shows data type and its column type. For remaining types, `GridTextColumn` will be added. 

<table>
<tr>
<th>
Data Type
</th>
<th>
Column
</th>
</tr>
<tr>
<td>
string, object, dynamic
</td>
<td>
GridTextColumn
</td>
</tr>
<tr>
<td>
int, float, double, decimal and also it’s nullable
</td>
<td>
GridNumericColumn
</td>
</tr>
<tr>
<td>
DateTime, DateTimeOffset and also it’s nullable
</td>
<td>
GridDateTimeColumn
</td>
</tr>
<tr>
<td>
Uri, Uri?
</td>
<td>
GridHyperLinkColumn
</td>
</tr>
<tr>
<td>
bool, bool?
</td>
<td>
GridCheckBoxColumn
</td>
</tr>
<tr>
<td>
TimeSpan, TimeSpan?
</td>
<td>
GridTimeSpanColumn
</td>
</tr>
</table>


N> The order of columns in the collection will determine the order of that they will appear in SfDataGrid.

#### AutoGenerateColumns with different modes

Column auto generation is controlled using [SfDataGrid.AutoGenerateColumnsMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumnsMode) property.

The `SfDataGrid.AutoGenerateColumnsMode` includes the following modes.

<table>
<tr>
<th>
Mode
</th>
<th>
Behavior
</th>
<th>
When ItemsSource changed
</th>
</tr>
<tr>
<td>
<code>Reset</code>
</td>
<td>
Generates the columns based on the properties defined in the underlying data object.
</td>
<td>
Keeps the columns added manually. 
Clears the columns which are auto generated before and creates new columns based on new ItemsSource.
</td>
</tr>
<tr>
<td>
<code>RetainOld</code>
</td>
<td>
Generates the columns based on the properties defined in the underlying data object if the columns are not defined explicitly. 
</td>
<td>
The same columns will be maintained when changing ItemsSource also. So filtering, sorting and grouping settings will be maintained.
</td>
</tr>
<tr>
<td>
<code>ResetAll</code>
</td>
<td>
Generates the columns based on the properties defined in the underlying data object.
</td>
<td>
Clear all the columns including the columns defined manually and creates new columns based on new ItemsSource.
</td>
</tr>
<tr>
<td>
<code>None</code>
</td>
<td>
Columns will not be generated.
</td>
<td>
Keeps old columns in DataGrid.Columns collection.
</td>
</tr>
</table>

#### Auto generating columns for complex type

Custom type (complex type) properties in data object can be auto-generated by setting [AutoGenerateColumnsForCustomType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumnsForCustomType) property as true. Default value is false.
Custom type properties will be auto-generated through [AutoGenerateColumnsModeForCustomType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGenerateColumnsModeForCustomType.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid ItemsSource="{Binding Source}" x:Name="dataGrid"
                        AutoGenerateColumnsForCustomType="True"
                        AutoGenerateColumnsModeForCustomType="Parent"
                        AllowEditing="True"
                        AllowFiltering="True" 
                        AllowSorting="True" 
                        ShowGroupDropArea="True"
                        ColumnSizer="Star" >
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoGenerateColumnsForCustomType = true;
this.dataGrid.AutoGenerateColumnsModeForCustomType = AutoGenerateColumnsModeForCustomType.Parent;             
{% endhighlight %}
{% endtabs %}

The `AutoGenerateColumnsModeForCustomType` includes the following modes.

<table>
<tr>
<th>
Mode
</th>
<th>
Behavior
</th>
</tr>
<tr>
<td>
<code>Both</code>
</td>
<td>
Specifies that the columns for both the custom type and its inner properties will be auto generated.
</td>
</tr>
<tr>
<td>
<code>Child</code>
</td>
<td>
Specifies that the columns for all inner properties of custom type column will be auto generated. 
</td>
</tr>
<tr>
<td>
<code>Parent</code>
</td>
<td>
Specifies that the column for only the custom type will be auto generated.
</td>
</tr>
</table>

You can download the sample demo [here](https://github.com/SyncfusionExamples/how-to-auto-generate-columns-for-custom-type-properties-in-uwp-and-wpf-datagrid) .

#### Customize auto-generated columns in DataGrid

You can customize or cancel the generated column by handling [AutoGeneratingColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event. `AutoGeneratingColumn` event occurs when the individual column is auto-generated for public and non-static property of underlying data object.

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
}
{% endhighlight %}
{% endtabs %}

[AutoGeneratingColumnArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html) provides the information about the auto-generated column to the `AutoGeneratingColumn` event. [AutoGeneratingColumnArgs.Column](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html#Syncfusion_UI_Xaml_Grid_AutoGeneratingColumnArgs_Column) property returns the newly created column.

##### Cancel column generation for particular property

You can cancel the specific column adding to the DataGrid by handling `AutoGeneratingColumn` event.

In the below code, column generation for `OrderID` property is canceled by setting `Cancel` property to `true`. 

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if (e.Column.MappingName == "OrderID")
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

##### Changing column type

You can change the type of column adding to SfDataGrid by setting the instance of column you want to add in `AutoGeneratingColumn` event. 

In the below code, column type for `UnitPrice` property is changed to `GridTextColumn` by setting instance of GridTextColumn to `Column` property. 

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
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

##### Changing property settings

You can change the column properties in `AutoGeneratingColumn` event handler. 

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if(e.Column.MappingName=="OrderID")
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

#### Setting template to auto-generated column

You can set [GridColumn.HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_HeaderTemplate) and [GridColumn.CellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellTemplate) properties for auto-generated column in `AutoGeneratingColumn` event handler. 

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <DataTemplate x:Key="headerTemplate">
        <TextBlock Text="The product has been purchased by the following OrderID" TextWrapping="Wrap" />
    </DataTemplate>
</Window.Resources>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if (e.Column.MappingName == "OrderID")
    {
        e.Column.HeaderTemplate = this.FindResource("headerTemplate") as DataTemplate;
    }
}
{% endhighlight %}
{% endtabs %}

Below screenshot shows the customized header template loaded on the header of OrderID column.

![WPF datagrid shows customized header template loaded on the header of OrderID column](Columns_images/Columns_img1.png)

#### Data Annotations with AutoGenerateColumns

SfDataGrid support to generate the columns based on built-in [Data Annotation Attributes](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations(v=vs.95).aspx). Data Annotations ignored, when the `AutoGenerateColumns` is set to False.

##### Exclude column

You can skip the column generation using `AutoGenerateField` property or set the `Bindable` attribute to false.

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateField = false, Description = "OrderID field is not generated in UI")]

public int OrderID
{
    get { return orderID; }
    set { orderID = value; }
}
{% endhighlight %}
{% endtabs %}

##### Filtering

You can enable filtering automatically for the field using `Display.AutoGenerateFilter` property

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateFilter = true, Description = "Filter enabled for CustomerID column")]

public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

##### Editing 

You can change the value of the property using `Editable` attribute.

{% tabs %}
{% highlight c# %}
[Editable(true)]

public string Country
{
    get { return country; }
    set { country = value; }
}
{% endhighlight %}
{% endtabs %}

##### Change the HeaderText of column

You can customize header text of column using `Display.Name` property.

{% tabs %}
{% highlight c# %}
[Display(Name="Name of the Customer",Description="CustomerName is necessary for identification ")]

public string CustomerName
{
    get { return customerName; }
    set { customerName = value; }
}
{% endhighlight %}
{% endtabs %}

##### Change the order of the columns

You can change the columns order using `DisplayAttribute.Order` property.

{% tabs %}
{% highlight c# %}
[Display(Order=0)]

public int OrderID
{
    get { return orderID; }
    set { orderID = value; }
}
[Display(Order=-1)]

public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

The OrderID and CustomerID column rearranged based on specified order.

![OrderID and CustomerID column rearranged in WPF datagrid ](Columns_images/Columns_img2.png)

##### DataGrid column formatting

You can customize the data format using `DataTypeAttribute.DataType` property.

{% tabs %}
{% highlight c# %}
[DataType(DataType.Currency)]        

public double  UnitPrice
{
    get { return unitPrice; }
    set { unitPrice = value; }
}
{% endhighlight %}
{% endtabs %}

##### DataGrid read-only column 

You can disable the editing for a column using `ReadOnly` attribute.

{% tabs %}
{% highlight c# %}
[ReadOnly(true)]

public string Country
{
    get { return country; }
    set { country = value; }
}
{% endhighlight %}
{% endtabs %}

##### Format datagrid columns using DisplayFormat attribute

The auto-generated columns will be formatted using the [DataFormatString](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc679306%28v%3dvs.95%29) property in the [DisplayFormat](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc679253%28v%3dvs.95%29) attribute when the `DisplayFormat` attribute is defined for the properties defined in the view model. If the `DisplayFormat` attribute is defined with the `DataFormatString` property, the DataGrid formats the column only based on `DataFormatString`, without considering other formatting property settings of columns.

{% tabs %}
{% highlight c# %}
[DisplayFormat(DataFormatString = "Country is {0}")]
public string Country
{
    get { return country; }
    set { country = value; }
}

[DisplayFormat(DataFormatString = "yyyy")]
public DateTime OrderDate
{
    get {  return _orderDate; }
    set {  orderDate = value; }
}
{% endhighlight %}
{% endtabs %}

N> The `DataFormatString` attribute will be considered only when the column is auto-generated.

![Columns formatted with DisplayFormatString in WPF datagrid](Columns_images/Columns_img13.png)

### Manually defining columns

SfDataGrid control allows you to define the columns manually by adding desired column to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) collection.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="False"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn HeaderText="Order ID" MappingName="OrderID" />
        <syncfusion:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />
        <syncfusion:GridTextColumn HeaderText="Customer Name" MappingName="CustomerName" />
        <syncfusion:GridTextColumn HeaderText="Country" MappingName="Country" />
        <syncfusion:GridNumericColumn HeaderText="Unit Price" MappingName="UnitPrice" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Order ID", MappingName = "OrderID" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Customer ID", MappingName = "CustomerID" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Customer Name", MappingName = "CustomerName" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Country", MappingName = "Country" });
this.dataGrid.Columns.Add(new GridNumericColumn() { HeaderText = "Unit Price", MappingName = "UnitPrice" });             
{% endhighlight %}
{% endtabs %}

You can refer more information about handling the column level operations for manually defined columns in Column types section.

## Column manipulation

You can get the columns (added or auto-generated) from [SfDataGrid.Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) property.

### Adding column to DataGrid

You can add column at runtime by adding instance of column to `SfDataGrid.Columns` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Order ID", MappingName = "OrderID" });
{% endhighlight %}
{% endtabs %}

### Accessing column

You can access the column through its column index or `GridColumn.MappingName` from the SfDataGrid.Columns collection.

{% tabs %}
{% highlight c# %}
GridColumn column = this.dataGrid.Columns[1];
//OR
GridColumn column = this.dataGrid.Columns["OrderID"];
{% endhighlight %}
{% endtabs %}

### Clearing or removing column in DataGrid

You can remove all the columns by clearing the `SfDataGrid.Columns` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.Columns.Clear();
{% endhighlight %}
{% endtabs %}

You can remove a column using Remove and RemoveAt methods.

{% tabs %}
{% highlight c# %}
dataGrid.Columns.Remove(column);
//OR
dataGrid.Columns.RemoveAt(1);
{% endhighlight %}
{% endtabs %}

You can also remove the column under one stacked column from StackedHeaderRow.

{% tabs %}
{% highlight c# %}
var childColumns = this.dataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns.Split(',');

foreach (var name in childColumns)
{
    var column = dataGrid.Columns[name];

    if (column == null)
        continue;
    dataGrid.Columns.Remove(column);
}
{% endhighlight %}
{% endtabs %}

## DataGrid column resizing 

SfDataGrid allows to resize the columns like in excel by resizing column header. This can be enabled or disabled by setting [SfDataGrid.AllowResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingColumns) or [GridColumn.AllowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property.

N> Resizing considers MinWidth and MaxWidth of column.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

You can change the column width by clicking and dragging the resizing cursor at the edge of column header. The resizing cursor appears when you hover the grid line exists between two columns. 

![Resizing cursor shown in between columns of WPF datagrid](Columns_images/Columns_img3.png)

### Hidden column resizing

SfDataGrid shows indication for hidden columns in column header and also allows end-users to resize the hidden columns when setting [SfDataGrid.AllowResizingHiddenColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingHiddenColumns) property to `true`.

![Hidden column resizing cursor shown on hidden column of WPF datagrid](Columns_images/Columns_img4.png)

### Disable resizing

You can cancel resizing of particular column by setting [GridColumn.AllowResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property to `false`. In another way, you can cancel the resizing by handling [SfDataGrid.ResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event. The `ResizingColumns` event occurs when you start dragging by resizing cursor on headers.
[ResizingColumnsEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html) of `ResizingColumns` provides information about the columns’s index and width. 

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

SfDataGrid allows you to identify the progress of the resizing of columns through [ResizingColumnsEventArgs.Reason](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Reason) property. You can get the width of the column after resizing completed by getting [ResizingColumnsEventArgs.Width](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Width) when `ResizingColumnsEventArgs.Reason` is [ColumnResizingReason.Resized](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ColumnResizingReason.html) in [ResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

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

## DataGrid column drag and drop

You can allow end-users to rearrange the columns by drag and drop the column headers by setting [SfDataGrid.AllowDraggingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowDraggingColumns) to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowDraggingColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

![WPF datagrid shows the drag window of columns](Columns_images/Columns_img5.png)

You can enable or disable dragging on particular column using [GridColumn.AllowDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowDragging) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn  AllowDragging="False"
                            HeaderText="Order ID"
                            MappingName="OrderID" />
{% endhighlight %}
{% endtabs %}

### Disable column reordering

You can cancel the particular column dragging by handling [SfDataGrid.QueryColumnDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html). `QueryColumnDragging` event occurs when you start dragging the column header. [QueryColumnDraggingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs.html) of `QueryColumnDragging` event provides information about the column triggered this event. 

`QueryColumnDraggingEventArgs.From` property returns the index of column triggered this event. `QueryColumnDraggingEventArgs.To` property returns the index where you try to drop the column. `QueryColumnDraggingEventArgs.Reason` returns column dragging details by [QueryColumnDraggingReason](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.QueryColumnDraggingReason.html).  

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryColumnDragging += dataGrid_QueryColumnDragging;

void dataGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    var column = dataGrid.Columns[e.From];

    if (column.MappingName == "CustomerName" && e.Reason == QueryColumnDraggingReason.Dropping)
    {
        e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

### Column drag and drop customization 

The drag-and-drop operations can be changed by overriding the virtual methods of [GridColumnDragDropController](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnDragDropController.html) class and assigning it to `SfDataGrid.GridColumnDragDropController`. 

{% tabs %}
{% highlight c# %}
this.dataGrid.GridColumnDragDropController = new CustomDragDropController(dataGrid);

public class CustomDragDropController:GridColumnDragDropController
{

    public CustomDragDropController(SfDataGrid dataGrid): base(dataGrid)
    {
    }        

    //Returns whether the popup showed its header or not.

    public override bool CanShowPopup(GridColumn column)
    {
        return base.CanShowPopup(column);
    }

    //Get the corresponding GridRegion at a given point.

    public override GridRegion PointToGridRegion(System.Windows.Point point)
    {
        return base.PointToGridRegion(point);
    }

    //Occurs when the GridColumn.Hidden property value changed.

    protected override void OnColumnHiddenChanged(GridColumn column)
    {
        base.OnColumnHiddenChanged(column);
    }

    //Occurs when the popup content is created.

    protected override System.Windows.UIElement CreatePopupContent(GridColumn column)
    {
        return base.CreatePopupContent(column);
    }

    //Occurs when the popup content is dropped on DataGrid.

    protected override void PopupContentDroppedOnGrid(System.Windows.Point point)
    {
        base.PopupContentDroppedOnGrid(point);
    }

    //Occurs when the popup content is dropped on header row.

    protected override void PopupContentDroppedOnHeaderRow(int oldIndex, int newColumnIndex)
    {
        base.PopupContentDroppedOnHeaderRow(oldIndex, newColumnIndex);
    }

    //Occurs when the popup content is dropped.

    protected override void OnPopupContentDropped(System.Windows.Point point, System.Windows.Point pointOverGrid)
    {
        base.OnPopupContentDropped(point, pointOverGrid);
    }

    //Occurs when the popup content is dropped on GroupDropArea

    protected override void PopupContentDroppedOnGroupDropArea(GridColumn column)
    {
        base.PopupContentDroppedOnGroupDropArea(column);
    }

    //Occurs when the popup content position changed.

    protected override void OnPopupContentPositionChanged(double HorizontalDelta, double VerticalDelta, System.Windows.Point mousePoint, System.Windows.Point mousePointOverGrid)
    {
        base.OnPopupContentPositionChanged(HorizontalDelta, VerticalDelta, mousePoint, mousePointOverGrid);
    }
}
{% endhighlight %}
{% endtabs %}

### Disabling drag & drop between frozen and non-frozen columns

By default, the columns re-ordering performed between any column regions of columns. You can cancel the dropping action between the frozen and non-frozen columns by handling [SfDataGrid.QueryColumnDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryColumnDragging += dataGrid_QueryColumnDragging;

void dataGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{    

    if (e.Reason == QueryColumnDraggingReason.Dropping)
    {
        var frozenColIndex = this.dataGrid.FrozenColumnCount + this.dataGrid.ResolveToStartColumnIndex();

        if (e.From < frozenColIndex && e.To > frozenColIndex - 1)
            e.Cancel = true;
       
        if (e.From > frozenColIndex && e.To < frozenColIndex ||(e.From == frozenColIndex && e.To < frozenColIndex))
            e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

N> `FrozenColumnCount` and `FooterColumnCount` should be lesser than the number of Columns that can be displayed in View.

## DataGrid freeze columns 

You can freeze the columns in view at the left and right side like in excel by setting [SfDataGrid.FrozenColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) and [SfDataGrid.FooterColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FooterColumnCount) properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="False"
                        FrozenColumnCount="2"
                        ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% endtabs %}

![WPF datagrid shown with frozen columns](Columns_images/Columns_img6.png)

### Limitations

1. SfDataGrid has support to freeze the number of columns from the left or right. There is no support to freeze a specific column.

## Binding column properties with ViewModel

SfDataGrid provides MVVM support for binding `GridColumn` properties with ViewModel properties
. 
{% tabs %}
{% highlight c# %}
public class ViewModel
{
    private bool _allowFiltering =true;

    public bool AllowFiltering
    {
        get { return _allowFiltering; }
        set { _allowFiltering = value; }
    }
}
{% endhighlight %}
{% endtabs %}

Below code, binds the `ViewModel.AllowFiltering` property to `GridColumn.AllowFiltering` property.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ItemsSource="{Binding Orders}"                                                                                       
                       AutoGenerateColumns="False">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn MappingName="OrderID" AllowFiltering="{Binding AllowFiltering}"/>
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid> 
{% endhighlight %}
{% endtabs %}

![WPF datagrid shows ViewModel.AllowFiltering property binded to GridColumns.AllowFiltering](Columns_images/Columns_img11.png)

