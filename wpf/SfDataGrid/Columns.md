---
layout: post
title: Columns
description: columns
platform: wpf
control: SfDataGrid
documentation: ug
---

# Columns

This section explains you how to add Columns, ways to create Column, different types of Column, and Column’s features like Column Sizer, Hiding, Freezing, Resizing Columns, and Drag and Drop support.

## Add Columns

The DataGrid control allows you to add Columns in two ways:

* Automatically generate the Columns based on the underlying collection.
* Manually define the columns in XAML or C#.

## Automatically Generate Columns

The following is a list of properties associated with generating columns.

SfDataGrid.AutoGenerateColumns: This dependency property decides Columns generation for a Grid based on AutoGenerateColumnsMode property. 

SfDataGrid.AutoGenerateColumnsMode: It decides a way to create columns when AutoGenerateColumns is set to’ true’. This enum type has the following four options. 

* Reset: Creates columns for all fields in a Data Source and retains the columns defined explicitly in application level.
* RetainOld: Creates columns for all fields in a Data Source when the Grid does not have any explicit definition for columns. When columns are defined explicitly, then new columns are not created.
* ResetAll: When changing ItemsSource, the columns for previous data are cleared and it creates new columns. Else when you define columns explicitly it does not take defined columns, it takes from underlying collection.
* None: Stores the columns that are defined in DataGrid.Columns.

The DataGrid control by default creates columns for every public property automatically based on the underlying collection that bounds to the DataGrid using ItemsSource property. In this case, AutoGenerateColumns property value is set to ‘true’ and AutoGenerateColumnsMode property value is AutoGenerateColumnsMode.Reset.

N> When you change items source for SfDataGrid during run time, then the columns are generated on the basis of option set for AutoGenerateColumns Mode.

The following is the event that is associated with AutoGeneratingColumns.

## AutoGeneratingColumn Event

This event rises when the AutoGenerateColumns property values is set to ‘true’. This event receives two arguments namely sender that handles SfDataGrid and AutoGeneratingColumnArgs as objects.

The AutoGeneratingColumnArgs object contains the following property:

* Column: This property returns created column when AutoGenerateColumns is set to ‘true’. By using this property, you can manipulate columns.
* Cancel: This property cancels the columns to be created. 

You can use this event where you want to manipulate columns (apply filtering, sorting, grouping, editing, header text) when AutoGenerateColumns is set to ‘true’.

## DataAnnotation with AutoGenerateColumns

SfDataGrid supports DataAnnotations for customizing columns, when AutoGenerateColumns set to ‘true’. When [DisplayAttribute](http://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.displayattribute(v=vs.110).aspx), [DataTypeAttribute](http://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.datatypeattribute(v=vs.110).aspx), [EditableAttribute](http://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx) and [BindableAttribute](http://msdn.microsoft.com/en-us/library/system.componentmodel.bindableattribute.aspx) are specified in model class, columns are generated based on the mentioned attributes that supports DataAnnotation of SfDataGrid.

N> When AutoGenerateColumns property value is set to ‘false’, you can ignore mentioned DataAnnotaions attributes. 

The following example illustrates this scenario. For data collection use OrderInfoRepositiory.cs, file.


{% highlight xml %}



<syncfusion:SfDataGrid x:Name="sfdatagrid"

                       AutoGenerateColumns="True"

                       ColumnSizer="Star"

                       ItemsSource="{Binding OrderInfoCollection,

                       Source={StaticResource data}}" />


{% endhighlight %}


In the following code example Display keyword mentions different attributes to customize columns.


{% highlight C# %}




public class OrderInfo

{

    int orderID;

    string customerId;

    string country;

    string customerName;

    string shippingCity;



    [Display(AutoGenerateField= false,Description="This filed is not created")]

    [DataType(DataType.Currency)]

    public int OrderID

    {

        get { return orderID; }

        set { orderID = value; }

    }



    [Display(Order = -1, Description ="This field is hidden")]        

    public string CustomerID

    {

        get { return customerId; }

        set { customerId = value; }

    }

    [Bindable(false)]                        

    public string CustomerName

    {

        get { return customerName; }

        set { customerName = value; }

    }



    [Display(AutoGenerateFilter = true)]   

    [Editable(true)]

    public string Country

    {

        get { return country; }

        set { country = value; }

    }



    [Display(Order = -2)]

    public string ShipCity

    {

        get { return shippingCity; }

        set { shippingCity = value; }

    }

    public OrderInfo(int orderId, string customerName, string country, string

    customerId, string shipCity)

    {

        this.OrderID = orderId;

        this.CustomerName = customerName;

        this.Country = country;

        this.CustomerID = customerId;

        this.ShipCity = shipCity;

    }

}

{% endhighlight %}

The following screenshot renders you the output.



![](Features_images/Features_img40.png)


_DataGrid with Filter in Country column_

You can see that in Country column it has Filtering enabled in its header.Since AutoGenerateFilter is set to ‘true’, ShipCity have order -2 that displays before CustomerID. When AutoGenerateField is set to ‘false’, OrderID column is not displayed.

## Manually Generate Columns

As mentioned in the second case, the DataGrid control enables you to define columns you want to display in the Grid. You can define the columns by adding a column to the SfDataGrid.Columns collection. The case where you want only the columns manually defined in view, you can set AutoGenerateColumns property value to ‘false’. There are different GridColumns available in SfDataGrid. You can select any column as follows – GridTextColumn, GridNumericColumn, GridCurrencyColumn, GridPercentColumn, GridMaskColumn, GridTimeSpanColumn, etc.  Each column has its own property to show its uniqueness in view and edit mode.

The following code example defines manually to create columns using XAML.


{% highlight xml %}





<syncfusion:SfDataGrid x:Name="sfdatagrid"

                       AutoGenerateColumns="False"

                       ColumnSizer="Auto"

                       ItemsSource="{Binding OrderInfoCollection}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn HeaderText="Order ID" MappingName="OrderID" />

        <syncfusion:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />

        <syncfusion:GridTextColumn HeaderText="Name of Customer" MappingName="CustomerName" />

        <syncfusion:GridTextColumn HeaderText="Ship Country" MappingName="ShipCountry" />

        <syncfusion:GridTextColumn HeaderText="Ship City" MappingName="ShipCity" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}




The following code example defines manually create columns through C#.


{% highlight C# %}





void sfdatagrid_Loaded(object sender, RoutedEventArgs e)

{

    sfdatagrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });

    sfdatagrid.Columns.Add(new GridTextColumn() { MappingName= "CustomerID"});

    sfdatagrid.Columns.Add(new GridTextColumn() { MappingName = "CustomerName" });

    sfdatagrid.Columns.Add(new GridTextColumn() { MappingName = "Country" });

    sfdatagrid.Columns.Add(new GridTextColumn() { MappingName = "ShipCity" });

}
{% endhighlight %}




N> The case where you want to display column in both ways: you can use SfDataGrid.AutoGenerateColumnsMode. to define columns collection and remaining from items Source.

## Column Properties

GridColumn is the base column type of all the columns in the DataGrid. The most important GridColumn properties are listed in the following table:

 _GridColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
GridColumn.ActualWidth</td><td>
Double</td><td>
Gets the actual width of the Grid column.</td><td>
Double.NaN</td></tr>
<tr>
<td>
GridColumn.AllowBlankFilters</td><td>
Boolean</td><td>
Gets or sets whether blank filters are allowed in Excel-like filter drop-down list or not.</td><td>
True</td></tr>
<tr>
<td>
GridColumn.AllowDragging</td><td>
Boolean</td><td>
Get or sets whether the columns are allowed to drag in the DataGrid or not.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.AllowEditing</td><td>
Boolean</td><td>
Gets or sets whether the column is editable or not.</td><td>
True</td></tr>
<tr>
<td>
GridColumn.AllowFiltering</td><td>
Boolean</td><td>
Gets or sets whether particular column can be filtered or not.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.AllowFocus</td><td>
Boolean</td><td>
Gets or sets whether focus is allowed to a particular column or not.</td><td>
True</td></tr>
<tr>
<td>
GridColumn.AllowGrouping</td><td>
Boolean</td><td>
Gets or sets whether columns are allowed to group in the DataGrid or not.</td><td>
True</td></tr>
<tr>
<td>
GridColumn.AllowResizing</td><td>
Boolean</td><td>
Gets or sets whether the columns are allowed to be resized or not.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.AllowSorting</td><td>
Boolean</td><td>
Gets or sets  whether sorting is allowed in a Grid Column or not.</td><td>
True</td></tr>
<tr>
<td>
GridColumn.CellStyle</td><td>
Style</td><td>
Customizes the style for cells in the Grid Column.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.ColumnSizer</td><td>
Enum</td><td>
Specifies the auto column width calculation options for GridColumn</td><td>
None</td></tr>
<tr>
<td>
GridColumn.DisplayBinding</td><td>
Binding</td><td>
Denotes the binding to DateModel in non-edit mode which gives flexibility to format display. </td><td>
Null</td></tr>
<tr>
<td>
GridColumn.FilterPopupStyle</td><td>
Style</td><td>
The property that customizes the style for Filter Pop-up. </td><td>
Null</td></tr>
<tr>
<td>
GridColumn.FilterPopupTemplate</td><td>
DataTemplate</td><td>
The property that  gets or sets and customizes the structure of the Filter Pop-up.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.HeaderStyle</td><td>
Style</td><td>
The property that  gets or sets and customizes the style for the header cell.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.HeaderTemplate</td><td>
DataTemplate</td><td>
The property that gets or sets and customizes the structure of the Header cell.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.HeaderText</td><td>
String</td><td>
The string value that is bounded to the Header text is displayed in Column header.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.HeaderToolTipTemplate</td><td>
DataTemplate</td><td>
The property that customizes the structure of tooltip for header cell.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.HorizontalHeaderContentAlignment</td><td>
HorizontalAlignment</td><td>
Sets horizontal alignment for the column header text.</td><td>
HorizontalAlignment.Left</td></tr>
<tr>
<td>
GridColumn.ImmediateUpdateColumnFilter</td><td>
Boolean</td><td>
Specfies whether the filters are applied immediately when the checkbox is toggled in the filter pop-up list.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.IsHidden</td><td>
Boolean</td><td>
The property that allows the column to be hiden.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.MappingName</td><td>
String</td><td>
Property name from DataModel that need to bound to the GridColumn</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.MaximumWidth</td><td>
Double</td><td>
Specifies the maximum width of the Grid Column.</td><td>
Double.NaN</td></tr>
<tr>
<td>
GridColumn.MinimumWidth</td><td>
Double</td><td>
Specifies the minimum width of the Grid Column.</td><td>
Double.NaN</td></tr>
<tr>
<td>
GridColumn.Padding</td><td>
Thickness</td><td>
Specifies the padding thickness for the column’s cell.</td><td>
(5,1,5,1)</td></tr>
<tr>
<td>
GridColumn.ToolTipTemplate</td><td>
DataTemplate</td><td>
The property that customizes the tooltip.</td><td>
Null</td></tr>
<tr>
<td>
GridColumn.UseBindingValue</td><td>
Boolean</td><td>
When set to true then Sorting, Grouping, Filtering and etc will use ValueBinding to access underlying DataModel property value instead of reflection.</td><td>
False</td></tr>
<tr>
<td>
GridColumn.GridValidationMode</td><td>
GridValidationMode</td><td>
Specifies the validation mode for GridColumn.</td><td>
None</td></tr>
<tr>
<td>
GridColumn.ValueBinding</td><td>
Binding</td><td>
Specifies the binding for GridColumns when the gridcell is in edit mode. </td><td>
Null</td></tr>
<tr>
<td>
GridColumn.Width</td><td>
Double</td><td>
Gets or sets the width for Grid Column.</td><td>
Double.NaN</td></tr>
</table>


N> GridTextColumnBase is the abstract class that is derived from GridColumn. GridTextColumn, GridMaskColumn and GridTimeSpanColumn are derived from GridTextColumnBase. GridEditorColumn is another abstract column that is derived from GridColumn. GridNumericColumn, GridCurrencyColumn, GridDateTimeColumn and GridPercentColumn are derived from GridEditorColumn.

The following provides the list of properties that supports the columns having GridTextColumnBase as Base Class.

_GridTextColumnBase property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
GridTextColumnBase.TextTrimming</td><td>
TextTrimming</td><td>
The property trims the value in each cell of the column that has more length than column width in view.</td><td>
TextTrimming.None</td></tr>
<tr>
<td>
GridTextColumnBase.TextWrapping</td><td>
TextWrapping</td><td>
The property trims the value in each cell of the column that has more length than column width in edit.</td><td>
TextWrapping. NoWrap </td></tr>
<tr>
<td>
GridTextColumnBase.TextDecorations</td><td>
TextDecorations</td><td>
The property that customizes the text.</td><td>
new TextDecorationCollection()</td></tr>
</table>

## CellTemplate

CellTemplate support is used to customize columns in display mode that present cells with DataTemplate. You can load standard controls or customized control in display mode to all columns like template column. In edit mode GridColumn loads it default editor.

Properties

_CellTemplate Properties_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Default Value</th></tr>
<tr>
<td>
CellTemplate</td><td>
The dependency property that gets or sets the data template of cell in display mode.</td><td>
DataTemplate</td><td>
Null</td></tr>
<tr>
<td>
CellTemplateSelector</td><td>
The dependency property that gets or sets the DataTemplateSelector and apply the defined template to cell in display.</td><td>
DataTemplateSelector</td><td>
Null</td></tr>
<tr>
<td>
SetCellBoundValue</td><td>
The DataContext for DataTemplate is set based on this property that sets the Record as DataContext. When setting this to true, it sets DataContextHelper as DataContext. DataContextHelper has Value and Record properties where the Value is set based on MappingName of the column.</td><td>
bool</td><td>
False</td></tr>
</table>


The following code example illustrates that how to set CellTemplate in Numeric Column.


{% highlight xml %}





<syncfusion:GridNumericColumn HeaderText="Quantity"

                              MappingName="UnitPrice"

                              NumberDecimalDigits="0">

    <syncfusion:GridNumericColumn.CellTemplate>

        <DataTemplate>

            <Grid>

                <ProgressBar x:Name="progressBar" Background="Transparent"  

                             Visibility="Visible" Minimum="0" Maximum="200"   

                             BorderThickness="0" Value="{Binding Path= UnitPrice}" />

                <TextBlock  Text="{Binding Path= UnitPrice}" HorizontalAlignment="Right"

                            VerticalAlignment="Center" TextAlignment="Center"/>

            </Grid>

        </DataTemplate>

    </syncfusion:GridNumericColumn.CellTemplate>

</syncfusion:GridNumericColumn>
{% endhighlight %}



The above XAML code renders the following output.



![](Features_images/Features_img41.png)


_Cell Template_

When you use CellTemplate for all columns, you can define DataTemplate at once and can bind to different columns with the underlying data to the DataTemplate regardless of MappingName. The property that allows to reuse the DataTemplate to any number of columns with DataTemplate key is SetCellBoundValue. When you enable SetCellBoundValue, it sets the DataContextHelper as DataContext to CellTemplate. DataContextHelper contains the following properties,

* Value – denotes the value from data based on MappingName property.
* Record – denotes the underlying data.

Now you can make use of Value property that provides value based on MappingName property and you can use the same template for any number of Columns that binds the value based on MappingName. 

The following code example illustrates on how to use the above property.



{% highlight xml %}





<!-- Need to add this code snippet in Resources

     Define the DataTemplate with Key.-->



<DataTemplate x:Key="DefaultTemplate">

    <TextBlock Text="{Binding Path=Value}" Margin="5" FontWeight="Bold" FontStyle="Italic"/>            

</DataTemplate>



<!-- Define Grid Columns,

     Use the key to column’s CellTemplate property via binding in a                   

     StaticResource and enable SetCellBoundValue. -->



<syncfusion:GridTextColumn MappingName="Quantity" 

                           TextAlignment="Center"                                             

                           SetCellBoundValue="True"

                           CellTemplate="{StaticResource DefaultTemplate}"/>

<syncfusion:GridDateTimeColumn HeaderText="Order Date"              

                               MappingName="OrderDate"    

                               SetCellBoundValue="True"  

                               CellTemplate="{StaticResource DefaultTemplate}"/>

<syncfusion:GridTimeSpanColumn HeaderText="Delivery Time" 

                               MappingName="DeliveryDelay" 

                               SetCellBoundValue="True" 

                               CellTemplate="{StaticResource DefaultTemplate}" />


{% endhighlight %}


The above XAML code renders the following output.



![](Features_images/Features_img42.png)



 _MappingName property_

CellTemplateSelector provides a way to select DataTemplate based on the data object and the data-bound element. The following code example explains you on how to use TemplateSelector.

Create required templates with static keys. 



{% highlight xml %}





<!-- Need to add this code snippet in Resources-->



<DataTemplate x:Key="DefaultTemplate">

    <TextBlock Text="{Binding Path=Value}" Foreground="Red" TextAlignment="Center" Background="Transparent" />

</DataTemplate>



<DataTemplate x:Key="AlternateTemplate">

    <TextBlock Text="{Binding Path=Value}" Foreground="Green" TextAlignment="Center" Background="Transparent"/>

</DataTemplate>        
{% endhighlight %}


Define the templates based on values to be applied in TemplateSelector. The following code example illustrate that how the different Data Templates applied to grid cells.

{% highlight C# %}






public class TemplateSelector : DataTemplateSelector

{

    private DataTemplate _defaultTemplate;

    /// <summary>

    /// Gets or sets DefaultTemplate

    /// </summary>

    public DataTemplate DefaultTemplate

    {

        get { return _defaultTemplate; }

        set { _defaultTemplate = value; }

    }



    private DataTemplate _alternateTemplate;

    /// <summary>

    /// Gets or Sets AlternateTemplate

    /// </summary>

    public DataTemplate AlternateTemplate

    {

        get { return _alternateTemplate; }

        set { _alternateTemplate = value; }

    }



    private string _propertyToEvaluate;

    /// <summary>

    /// Gets or sets property to evaluate

    /// </summary>

    public string PropertyToEvaluate

    {

        get { return _propertyToEvaluate; }

        set { _propertyToEvaluate = value; }

    }



    public override DataTemplate SelectTemplate(object item, System.Windows.DependencyObject container)

    {

        //The item that comes from CellTemplate is DataContextHelper. When set SetCellBoundValue to true, it sets DataContextHelper as DataContext to DataTemplate. Refer property section of CellTemplate

        OrderInfo dataUnit = (item as DataContextHelper).Record as OrderInfo;



        if (dataUnit == null) return this.DefaultTemplate;



        //use reflection to retrieve property

        Type type = dataUnit.GetType();

        PropertyInfo property = type.GetProperty(this.PropertyToEvaluate);



        //let’s see what template we need to select according to the specified property value

        if (Convert.ToInt16(property.GetValue(dataUnit, null)) < 25)

            return this.AlternateTemplate;

        else

            return this.DefaultTemplate;

    }

}

{% endhighlight %}

DataContextHelper is the helper class that contains Record and value property to get row data and the value that bound to respective column. The following code example explains you on how to apply CellTemplateSelector.

{% highlight xml %}







<!--In your column you have to defined like this -->



<syncfusion:GridCurrencyColumn CurrencyDecimalDigits="0"

                               HeaderText="UnitPrice"

                               SetCellBoundValue="True"

                               MappingName="Quantity">       

    <syncfusion:GridCurrencyColumn.CellTemplateSelector>

        <local:TemplateSelector DefaultTemplate="{StaticResource DefaultTemplate}"

                                AlternateTemplate="{StaticResource AlternateTemplate}"

                                PropertyToEvaluate="Quantity"/>                                

    </syncfusion:GridCurrencyColumn.CellTemplateSelector>

</syncfusion:GridCurrencyColumn>

{% endhighlight %}

The above code renders the following output.

![](Features_images/Features_img43.png)



 _CellTemplateSelector_

### Limitation

1. When you load Editor directly to CellTemplate (Textbox – MS, DoubleTextBox, PercentTextBox, and CurrencyTextBox - Syncfusion) in Template Column without Edit Template the grid cell cannot change to edit mode. You can just edit a value with loaded editor. 
2. GridImageColumn, GridCheckBoxColumn and GridHyperLinkColumn does not contain CellTemplate support. You can check [here](http://help.syncfusion.com/ug/wpf/default.htm) for more reference.

## Column types

Each column has its own functionalities as the columns name implies. You can use any column based on your requirements. The following statements describes you the purpose column.

_List of Columns table_

<table>
<tr>
<td>
GridTextColumn</td><td>
When you have string type in underlying collection you can use this column.</td></tr>
<tr>
<td>
GridNumericColumn</td><td>
When you have double type in underlying collection you can use this column.</td></tr>
<tr>
<td>
GridCurrencyColumn</td><td>
When you want your data to be in currency manner, you can use this column.</td></tr>
<tr>
<td>
GridPercentColumn</td><td>
When you want your data to be in percent manner, you can use this column.</td></tr>
<tr>
<td>
GridMaskColumn</td><td>
When you want your data to be masked, you can use this column.</td></tr>
<tr>
<td>
GridTimeSpanColumn</td><td>
When you have TimeSpan type in underlying collection you can use this column.</td></tr>
<tr>
<td>
GridDateTimeColumn</td><td>
When you have DateTime type in underlying collection you can use this column.</td></tr>
<tr>
<td>
GridComboBoxColumn</td><td>
When you need a Combobox in each row, you can use this column.</td></tr>
<tr>
<td>
GridCheckBoxColumn</td><td>
When you need a Check Box in each row, you can use this column.</td></tr>
<tr>
<td>
GridImageColumn</td><td>
When you want to show image in each row, you can use this column.</td></tr>
<tr>
<td>
GridHyperlinkColumn</td><td>
When you want hyperlink button in each row to navigate, you can use this column.</td></tr>
<tr>
<td>
GridTemplateColumn</td><td>
When you want to customize your column, you can use this column.</td></tr>
<tr>
<td>
GridUnboundColumn</td><td>
When you need an additional column that is not from underlying source, you can use this column.</td></tr>
<tr>
<td>
GridMultiColumnDropdownList</td><td>
When you want load multi columns within a drop down you can use this column.</td></tr>
</table>

### GridTextColumn

GridTextColumn is derived from GridTextColumnBase that is derived from GridColumn and hence it inherits all the properties of GridColumn.  GridTextColumn displays and allows editing of text data.  Each of the cells in GridTextColumn displays text according to the Mapping Name it is binded. 

The following provides the list of all properties that supports GridTextColumn:

* TextAlignment: The property that gets and sets and specifies TextAlignment used to align the text in the column cells. 

The following code example creates GridTextColumn.


{% highlight xml %}





<syncfusion:GridTextColumn MappingName="OrderID" TextAlignment="Right" />
{% endhighlight %}



{% highlight C# %}





sfdatagrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
{% endhighlight %}




### Data Formatting in GridTextColumn

To format the value displayed in the GridColumn, you can use StringFormat Property in the DisplayBinding when you want the value to be formatted in View Mode and you can use ValueBinding to set the Edit mode binding.

The following code example shows you how to declare a GridTextColumn in XAML.


{% highlight xml %}



<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTextColumn MappingName="OrderID" TextAlignment="Right" />

    <syncfusion:GridTextColumn DisplayBinding="{Binding Path=UnitPrice,

                                                        StringFormat='{}{0:C}'}"

                               MappingName="UnitPrice"

                               TextAlignment="Right"

                               ValueBinding="{Binding Path=UnitPrice}" />

    <syncfusion:GridTextColumn MappingName="Discount" />

    <syncfusion:GridTextColumn MappingName="Quantity" TextAlignment="Right" />

</syncfusion:SfDataGrid.Columns>

{% endhighlight %}

The above XAML code has resulted in the following Output. 



![](Features_images/Features_img44.png)



_DataGrid with GridTextColumn_



You can use different [StringFormats](http://msdn.microsoft.com/en-us/library/fbxft59x(v=vs.90).aspx) to customize your value in binding.


{% highlight xml %}





StringFormat='{} {0:dddd}'}"  <!--  To Format Date  -->

StringFormat='{}{0:C}'}"      <!--  To Format as Currency  -->

StringFormat='{}{0:P}'}"      <!--  To Format as Percent  -->

{% endhighlight %}

### GridNumericColumn

GridNumericColumn is derived from GridEditorColumn that is derived from GridTextColumn, inheriting its properties and has few additional properties. GridNumericColumn loads DoubleTextBox for editing. In addition to the GridColumn’s properties, GridNumericColumn supports the following list of properties:

 _GridNumericColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
AllowScrollingOnCircle</td><td>
Boolean</td><td>
Specifies whether to change value on MouseWheel or UP ARROW or DOWN ARROW key or not.</td><td>
True</td></tr>
<tr>
<td>
AllowNullValue</td><td>
Boolean</td><td>
Specifies whether the editor accepts NULL value or not.</td><td>
False</td></tr>
<tr>
<td>
MinValue</td><td>
Decimal</td><td>
MinValue is the Dependency Property that restricts the input below the bounded MinValue. </td><td>
Decimal.MinValue</td></tr>
<tr>
<td>
MaxValue</td><td>
Decimal</td><td>
MaxValue is the Dependency Property that restricts the input above the bounded MaxValue.</td><td>
Deciaml.MaxValue</td></tr>
<tr>
<td>
MaxValidation</td><td>
MaxValidation</td><td>
MaxValidation is the Dependency Property that specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MaxValue when you want to perform MaxValidation on editor. </td><td>
MaxValidation.OnKeyPress</td></tr>
<tr>
<td>
MinValidation</td><td>
MinValidation</td><td>
MinValidation specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MinValue when you want to perform MinValidation on editor.</td><td>
MinValidation.OnKeyPress</td></tr>
<tr>
<td>
NumerDeciamlDigits</td><td>
Integer</td><td>
NumerDeciamlDigits is the dependency property that specifies the number of decimal places to use numeric value in editor. (Specifies that the number of fractional digits is there).</td><td>
NumberFormatInfo.CurrentInfo.NumberDecimalDigits</td></tr>
<tr>
<td>
NumberDecimalSeparator</td><td>
string</td><td>
NumberDecimalSeparator is the dependency property that separates integral from fractional digits.</td><td>
NumberFormatInfo.CurrentInfo.NumberDecimalSeparator</td></tr>
<tr>
<td>
NumberGroupSeparator</td><td>
string</td><td>
NumberGroupSeparator is the dependency property that specifies the string that separates groups of digits to the left of the decimal in numeric values.</td><td>
NumberFormatInfo.CurrentInfo.NumberGroupSeparator</td></tr>
<tr>
<td>
NumberGroupSizes</td><td>
Int32Collection</td><td>
NumberGroupSizes is the Dependency Property that specifies the Int32Collection or single digit number. Specifies the number of digits in each group to the left of the decimal in numeric values.</td><td>
new Int32Collection {0}</td></tr>
<tr>
<td>
NumberNegativePattern</td><td>
integer</td><td>
NumberNegativePattern is the dependency property that defines the format of negative numeric values. </td><td>
NumberFormatInfo.CurrentInfo.NumberNegativePattern</td></tr>
</table>


The following code example illustrates how to use GridNumericColumn.

{% highlight xml %}




<syncfusion:GridNumericColumn AllowScrollingOnCircle="False"

                              HeaderText="Quantity"

                              MappingName="Quantity"

                              NumberDecimalDigits="2"

                              NumberDecimalSeparator="."                       

                              NumberGroupSeparator="," />

{% endhighlight %}


{% highlight C#%}



sfdatagrid.Columns.Add(new GridNumericColumn() { 

                   MappingName = "Quantity", 

                   HeaderText = "Quantity", 

                   AllowScrollingOnCircle = False, 

                   NumberGroupSeparator = ",", 

                   NumberDecimalSeparator = ".", 

                   NumberDecimalDigits = 2 }); 

{% endhighlight %}



The following screenshot illustrates the output.



![](Features_images/Features_img45.png)



_DataGrid with GridNumericColumn_

### GridCurrencyColumn

GridCurrencyColumn is derived from GridEditorColumn that is derived from GridTextColumn, inheriting its properties and has few additional properties. GridCurrencyColumn loads CurrencyTextBox for editing. In addition to the GridColumn’s properties, GridCurrencyColumn supports the following list of properties:

 _GridCurrencyColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
AllowScrollingOnCircle</td><td>
Boolean</td><td>
Specifies whether to change value on MouseWheel or UP ARROW or DOWN ARROW key.</td><td>
True</td></tr>
<tr>
<td>
AllowNullValue</td><td>
Boolean</td><td>
Specifies whether the editor accepts NULL value.</td><td>
False</td></tr>
<tr>
<td>
CurrencyDecimalDigits</td><td>
Integer</td><td>
CurrencyDecimalDigits is the dependency property that specifies the number of decimal places to use currency value in editor. (Specifies that the number of fractional digits is there).</td><td>
NumberFormatInfo.CurrentInfo.CurrencyDecimalDigits</td></tr>
<tr>
<td>
CurrencyGroupSeparator</td><td>
String</td><td>
CurrencyGroupSeparator is the dependency property that specifies the string and separates groups of digits to the left of the decimal in currency values.</td><td>
NumberFormatInfo.CurrentInfo.CurrencyGroupSeparator</td></tr>
<tr>
<td>
CurrencySymbol</td><td>
String</td><td>
The string that is used as currency symbol.</td><td>
NumberFormatInfo.CurrentInfo.CurrencySymbol</td></tr>
<tr>
<td>
CurrencyDecimalSeparator</td><td>
String</td><td>
CurrencyDecimalSeparator is the dependency property that separates integral from fractional digits.</td><td>
NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator</td></tr>
<tr>
<td>
CurrencyGroupSizes</td><td>
Int32Collection</td><td>
CurrencyGroupSizes is the Dependency property that specifies the Int32Collection or single digit number. Specifies the number of digits in each group to the left of the decimal in currency values.</td><td>
new Int32Collection {0}</td></tr>
<tr>
<td>
CurrencyPositivePattern</td><td>
Integer</td><td>
CurrencyPositivePattern is the dependency property that defines the format of positive currency values.</td><td>
NumberFormatInfo.CurrentInfo.CurrencyPositivePattern</td></tr>
<tr>
<td>
CurrencyNegativePattern</td><td>
Integer</td><td>
CurrencyNegativePattern is the dependency property that defines the format of negative currency values.</td><td>
NumberFormatInfo.CurrentInfo.CurrencyNegativePattern</td></tr>
<tr>
<td>
MinValue</td><td>
Decimal</td><td>
MinValue is the Dependency property that restricts the input below the bounded MinValue.</td><td>
Decimal.MinValue</td></tr>
<tr>
<td>
MaxValue</td><td>
Decimal</td><td>
MaxValue is the Dependency property that restricts the input above the bounded MaxValue. </td><td>
Decimal.MaxValue</td></tr>
<tr>
<td>
MaxValidation</td><td>
MaxValidation</td><td>
MaxValidation is the Dependency property that specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MaxValue when you want to perform MaxValidation on editor. </td><td>
MaxValidation.OnKeyPress</td></tr>
<tr>
<td>
MinValidation</td><td>
MinValidation</td><td>
MinValidation specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MinValue when you want to perform MinValidation on editor. </td><td>
MinValidation.OnKeyPress</td></tr>
</table>


The following code example illustrates how to use GridCurrencyColumn.


{% highlight xml %}




<syncfusion:GridCurrencyColumn AllowScrollingOnCircle="False"

                               CurrencyDecimalDigits="2"

                               CurrencyPositivePattern="2"

                               CurrencySymbol="$"

                               HeaderText="UnitPrice"

                               MappingName="UnitPrice" />
{% endhighlight %}


{% highlight C# %}




sfdatagrid.Columns.Add(new GridCurrencyColumn(){

                   MappingName= "UnitPrice", 

                   CurrencyDecimalDigits=2, 

                   CurrencyPositivePattern=2, 

                   CurrencySymbol="$", 

                   HeaderText="UnitPrice"});

{% endhighlight %}

The following screenshot illustrates the output.



![](Features_images/Features_img46.png)



_DataGrid with GridCurrencyColumn_

### GridPercentColumn

GridPercentColumn is derived from GridEditorColumn that is derived from GridTextColumn, inheriting its properties and has few additional properties. GridPercentColumn loads PercentTextBox for editing. In addition to the GridColumn’s properties, GridPercentColumn supports the following list of properties:

_GridPercentColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
AllowScrollingOnCircle</td><td>
Boolean</td><td>
Specifies whether to change value on MouseWheel or UP ARROW or DOWN ARROW key.</td><td>
True</td></tr>
<tr>
<td>
AllowNullValue</td><td>
Boolean</td><td>
Specifies whether the editor accepts NULL value or not.</td><td>
False</td></tr>
<tr>
<td>
MinValue</td><td>
Decimal</td><td>
MinValue is the Dependency property that restricts the input below the bounded MinValue.</td><td>
Decimal.MinValue</td></tr>
<tr>
<td>
MaxValue</td><td>
Decimal</td><td>
MaxValue is the Dependency property  that restricts the input above the bounded MaxValue.</td><td>
Decimal.MaxValue</td></tr>
<tr>
<td>
MaxValidation</td><td>
MaxValidation</td><td>
MaxValidation is the Dependency Property that specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MaxValue when you want to perform MaxValidation on editor.</td><td>
MaxValidation.OnKeyPress</td></tr>
<tr>
<td>
MinValidation</td><td>
MinValidation</td><td>
MinValidation specifies when to perform validation during Key press or focus lost on editor. It is mandatory to have MinValue when you want to perform MinValidation on editor.</td><td>
MinValidation.OnKeyPress.</td></tr>
<tr>
<td>
PercentDecimalDigits</td><td>
Integer</td><td>
PercentDecimalDigits is the dependency property that specifies the number of decimal places to use percent value in editor. (Specifies that the number of fractional digits is there).</td><td>
NumberFormatInfo.CurrentInfo.PercentDecimalDigits</td></tr>
<tr>
<td>
PercentDecimalSeparator</td><td>
String</td><td>
PercentDecimalSeparator is the dependency property that separates integral from fractional digits.</td><td>
NumberFormatInfo.CurrentInfo.PercentDecimalSeparator</td></tr>
<tr>
<td>
PercentGroupSeparator</td><td>
String</td><td>
PercentGroupSeparator is the dependency property that specifies the string and separates groups of digits to the left of the decimal in percent values.</td><td>
NumberFormatInfo.CurrentInfo.PercentGroupSeparator</td></tr>
<tr>
<td>
PercentGroupSizes</td><td>
Int32Collection</td><td>
PercentGroupSizes is the Dependency Property that specifies the Int32Collection or single digit number. Specifies the number of digits in each group to the left of the decimal in currency values.</td><td>
new Int32Collection{0}</td></tr>
<tr>
<td>
PercentNegativePattern</td><td>
Integer</td><td>
PercentNegativePattern is the dependency property that defines the format of negative percent values.</td><td>
NumberFormatInfo.CurrentInfo.PercentNegativePattern</td></tr>
<tr>
<td>
PercentPositivePattern</td><td>
Integer</td><td>
PercentPositivePattern is the dependency property that defines the format of positive percent values.</td><td>
NumberFormatInfo.CurrentInfo.PercentPositivePattern</td></tr>
<tr>
<td>
PercentSymbol</td><td>
String</td><td>
The string that is used as percent symbol.</td><td>
NumberFormatInfo.CurrentInfo.PercentSymbol</td></tr>
<tr>
<td>
PercentEditMode</td><td>
PercentEditMode</td><td>
Indicates the way of editing in percent editor. Possible values are PercentMode, DoubleMode.</td><td>
PercentEditMode.DoubleMode</td></tr>
</table>


The following code example illustrates how to use GridPercentColumn.



{% highlight xml %}



<syncfusion:GridPercentColumn HeaderText="Discount"

                              MappingName="Discount"

                              PercentDecimalDigits="2"

                              PercentGroupSeparator=","

                              PercentPositivePattern="1"

                              PercentSymbol="%" />
{% endhighlight %}

{% highlight C#%}




sfdatagrid.Columns.Add(new GridPercentColumn(){

                   HeaderText="Discount",   

                   MappingName="Discount",

                   PercentDecimalDigits=2 ,

                   PercentGroupSeparator=",", 

                   PercentPositivePattern=1, 

                   PercentSymbol="%" });
{% endhighlight %}


The following screenshot illustrates the output.



![](Features_images/Features_img47.png)


_DataGrid with GridPercentColumn_

### GridMaskColumn

GridMaskColumn is derived from GridTextColumnBase that is derived from GridColumn, inheriting its properties and has some additional properties. GridMaskColumn uses MaskTextBox for editing. GridMaskColumn supports the following list of properties:

  _GridMaskColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
SelectTextOnFocus</td><td>
Boolean</td><td>
Specifies whether the value in the editor is selected or not when the editor receives focus.</td><td>
False</td></tr>
<tr>
<td>
IsNumeric</td><td>
Boolean</td><td>
Specifies whether the value is Numeric or not.</td><td>
False</td></tr>
<tr>
<td>
Mask</td><td>
String</td><td>
Mask is the dependency property that specifies input logic without writing any custom validation logic.</td><td>
String.Empty</td></tr>
<tr>
<td>
MaskFormat</td><td>
MaskFormat</td><td>
Specifies the display format when mask value is used. It determines whether the literals and prompt characters are included in the formatted string. To know more about MaskFormat {{ '[Click Here](http://help.syncfusion.com/wpf/tools)' | markdownify }}</td><td>
MaskFormat.ExcludePromptAndLiterals</td></tr>
<tr>
<td>
DateSeparator</td><td>
String</td><td>
DateSeparator is the dependency property that separates Month, Date and Year when DateTime type value is bounded to editor.</td><td>
String.Empty</td></tr>
<tr>
<td>
DecimalSeparator</td><td>
String</td><td>
DecimalSeparator is the dependency property that separates integral from fractional digits.</td><td>
String.Empty</td></tr>
<tr>
<td>
PromptChar</td><td>
String</td><td>
PromptChar is the dependency property that represents absence of user input. </td><td>
‘_’</td></tr>
<tr>
<td>
TimeSeparator</td><td>
String</td><td>
TimeSeparator is the dependency property that separates hours, minutes and seconds.</td><td>
String.Empty</td></tr>
</table>


N> Mask definition is mandatory to use Date separator, Time Separator, Prompt Char and Decimal Separator.

The following code example illustrates how to use GridMaskColumn.


{% highlight xml %}




<syncfusion:GridMaskColumn HeaderText="Contact Number"

                           IsNumeric="True"

                           MappingName="ContactNumber"

                           Mask="(99)-9999"

                           MaskFormat="IncludePrompt" />

{% endhighlight %}


{% highlight C#%}



sfdatagrid.Columns.Add(new GridMaskColumn(){

                   HeaderText="Contact Number",

                   IsNumeric=true,

                   MappingName="ContactNumber", 

                   Mask="(99)-9999",MaskFormat= MaskFormat.IncludePrompt});

{% endhighlight %}

The following screenshot illustrates the output.



![](Features_images/Features_img48.png)



_DataGrid with GridMaskColumn_

### GridTimeSpanColumn

GridTimeSpanColumn is derived from GridTextColumnBase that is derived from GridColumn, inheriting its properties and has some additional properties. GridTimeSpanColumn uses TimeSpanEdit for editing. GridTimeSpanColumn supports the following list of properties:

 _GridTimeSpanColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
AllowNull</td><td>
Boolean</td><td>
Specifies whether an editor can accept Null Value or not.</td><td>
False</td></tr>
<tr>
<td>
AllowScrollingOnCircle</td><td>
Boolean</td><td>
Specifies whether to change value on MouseWheel or UP ARROW or DOWN ARROW key or not.</td><td>
True</td></tr>
<tr>
<td>
NullText</td><td>
String</td><td>
NullText is the dependency property that specifies the editor value when the user input is null.</td><td>
String.Empty</td></tr>
<tr>
<td>
ShowArrowButtons</td><td>
Boolean</td><td>
Specifies whether arrow buttons are visible or not.</td><td>
True</td></tr>
<tr>
<td>
MaxValue</td><td>
TimeSpan</td><td>
MaxValue is the Dependency property that restricts the input above the bounded MaxValue.</td><td>
System.TimeSpan.MaxValue</td></tr>
<tr>
<td>
MinValue</td><td>
TimeSpan</td><td>
MinValue is the Dependency property that restricts the input below the bounded MinValue.</td><td>
System.TimeSpan.MinValue</td></tr>
</table>


The following code example illustrates how to use GridTimeSpanColumn.


{% highlight xml %}




<syncfusion:GridTimeSpanColumn AllowNull="True"

                               AllowScrollingOnCircle="True"

                               HeaderText="Delivery Time"

                               MappingName="DeliveryDelay" />
{% endhighlight %}



{% highlight C#%}



sfdatagrid.Columns.Add(new GridTimeSpanColumn() { 

                   AllowNull = true, 

                   AllowScrollingOnCircle = true, 

                   HeaderText = "Delivery Time", 

                   MappingName = "DeliveryDelay" });
{% endhighlight %}


The following screenshot illustrates the output.



![](Features_images/Features_img49.png)



_DataGrid with GridTimeSpanColumn_

### GridDateTimeColumn

GridDateTimeColumn derives from GridTextColumnBase that derives from GridColumn inheriting its properties and includes other properties as follows. GridDateTimeColumn uses DateTimeEdit for editing. GridDateTimeColumn supports the following list of properties:

 _GridDateTimeColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
AllowScrollingOnCircle</td><td>
Boolean</td><td>
Specifies whether to change value on MouseWheel or UP ARROW or DOWN ARROW key.</td><td>
True</td></tr>
<tr>
<td>
AllowNullValue</td><td>
Boolean</td><td>
Specifies whether the editor accepts NULL value or not.</td><td>
False</td></tr>
<tr>
<td>
EnableClassicStyle</td><td>
Boolean</td><td>
Specifies whether to enable classic style for the DateTime dropdown or not.</td><td>
False</td></tr>
<tr>
<td>
DisableDateSelection</td><td>
Boolean</td><td>
Specifies whether to disable date selection in the DateTime dropdown or not.</td><td>
False</td></tr>
<tr>
<td>
ShowRepeatButton</td><td>
Boolean</td><td>
Specifies whether to show repeat button in the editor or not.</td><td>
False</td></tr>
<tr>
<td>
Pattern</td><td>
DateTimePattern</td><td>
Specifies the pattern to display bounded value. Like ShortDate or LongDate</td><td>
DateTimePattern.ShortDate</td></tr>
<tr>
<td>
DateTimeFormat</td><td>
DateTimeFormatInfo</td><td>
Defines the format to display the date in editor</td><td>
DateTimeFormatInfo.CurrentInfo</td></tr>
<tr>
<td>
NullValue</td><td>
DateTime?</td><td>
NullValue is the dependency property that specifies the value in editor when User Input is Null </td><td>
null</td></tr>
<tr>
<td>
NullText</td><td>
String</td><td>
NullText is the dependency property that specifies the string in editor when User Input is Null</td><td>
String.Empty</td></tr>
<tr>
<td>
MinDateTime</td><td>
DateTime</td><td>
MinDateTime is the Dependency property that restricts the input below the bounded MinDateTime.</td><td>
System.DateTime.MinValue</td></tr>
<tr>
<td>
MaxDateTime</td><td>
DateTime</td><td>
MaxDateTime is the Dependency property that restricts the input above the bounded MaxDateTime.</td><td>
System.DateTime.MaxValue</td></tr>
<tr>
<td>
CustomPattern</td><td>
String</td><td>
CustomPattern is the dependency property that specifies the customized pattern to display DateTime like other Pattern. </td><td>
String.Empty</td></tr>
<tr>
<td>
CanEdit</td><td>
Boolean</td><td>
Specifies whether editor is edited or not.</td><td>
False</td></tr>
<tr>
<td>
EnableBackspaceKey</td><td>
Boolean</td><td>
Specifies whether Backspace Key is enabled or not.</td><td>
False</td></tr>
<tr>
<td>
EnableDeleteKey</td><td>
Boolean</td><td>
Specifies whether Delete Key is enabled or not.</td><td>
False</td></tr>
</table>


N> NullValue is displayed when AllowNullValue is set to ‘true’. NullValue takes higher priority than NullText.

The following code example illustrates how to use GridDateTimeColumn.


{% highlight xml %}



<syncfusion:GridDateTimeColumn AllowScrollingOnCircle="True"

                               DisableDateSelection="False"

                               HeaderText="Order Date"

                               MappingName="OrderDate"

                               Pattern="ShortDate"

                               ShowRepeatButton="True" />
{% endhighlight %}

{% highlight C#%}



sfdatagrid.Columns.Add(new GridDateTimeColumn() { 

                   AllowScrollingOnCircle = true, 

                   DisableDateSelection = false, 

                   HeaderText = "Order Date", 

                   MappingName = "OrderDate",

                   Pattern = DateTimePattern.ShortDate, 

                   ShowRepeatButton = true });
{% endhighlight %}


The following screenshot illustrates the output.



![](Features_images/Features_img50.png)



_DataGrid with GridDateTimeColumn_

### GridComboBoxColumnn

GridComboBoxColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn. GridComboBoxColumn provides combobox for editing cell values and it displays a set of predefined values that is set to ItemSource in dropdown list.

To use GridComboBoxColumn, you can refer the following:

 _GridComboBoxColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
SelectedValuePath</td><td>
String</td><td>
Gets or sets the path that is used to get SelectedValue and SelectedItem.</td><td>
Null</td></tr>
<tr>
<td>
ItemSource</td><td>
IEnumerable</td><td>
Gets or sets the collection used to generate content for the dropdown list in the Column.</td><td>
Null</td></tr>
<tr>
<td>
DisplayMemberPath</td><td>
String</td><td>
Gets or sets a path to a value on the source object to serve as the visual representation of the object.</td><td>
String.Empty</td></tr>
<tr>
<td>
StaysOpenOnEdit</td><td>
Boolean</td><td>
Specifies whether a combobox  is opened and displays a drop-down control that remains open when you click the text box.</td><td>
False</td></tr>
<tr>
<td>
IsEditable</td><td>
Boolean</td><td>
Specifies a value whether editing of the text in text box of the combobox is enabled or not.</td><td>
False</td></tr>
<tr>
<td>
ItemTemplate</td><td>
DataTemplate</td><td>
ItemTemplate is the dependency property that specifies the DataTemplate displays each item or not.</td><td>
Null</td></tr>
</table>


The following code example displays how to use GridComboBoxColumn.


{% highlight xml %}

 

<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTextColumn MappingName="OrderID" TextAlignment="Right" />

    <syncfusion:GridComboBoxColumn ItemsSource="{Binding Path=ComboItems, Source={StaticResource viewmodel}}" MappingName="ProductName" />

    <syncfusion:GridTextColumn MappingName="UnitPrice" />

    <syncfusion:GridTextColumn MappingName="Discount" />

    <syncfusion:GridTextColumn MappingName="Quantity" TextAlignment="Right" />

</syncfusion:SfDataGrid.Columns>

{% endhighlight %}





{% highlight C#%}



sfdatagrid.Columns.Add(new GridComboBoxColumn() { 

                   ItemsSource = viewmodel.ComboItems,

                   MappingName = "ProductName" });

{% endhighlight %}

The above XAML Code has resulted in the following output:



![](Features_images/Features_img51.png)



_DataGrid with GridComboBoxColumn_

The following code example shows how to use ItemTemplate in GridComboBoxcolumn.



{% highlight xml %}






<syncfusion:GridComboBoxColumn ItemsSource="{Binding Path=ComboBoxItemsSource, Source={StaticResource viewmodel}}" MappingName="ProductName">

    <syncfusion:GridComboBoxColumn.ItemTemplate>

        <DataTemplate>

            <Grid>

                <TextBlock Text="{Binding}" />

            </Grid>

        </DataTemplate>

    </syncfusion:GridComboBoxColumn.ItemTemplate>

</syncfusion:GridComboBoxColumn>

{% endhighlight %}

The above XAML code has resulted in the following output:



![](Features_images/Features_img52.png)



_GridComboBoxColumn with Item Template_

The event associated with this column is CurrentCellDropDownSelectionChanged Event

This event occurs whenever a selected item is changed in Drop Down column such as GridComboBoxColumn. The event handler receives two arguments namely sender that handles SfDataGrid and CurrentCellDropDownSelectionChangedEventArgs as objects.

The CurrentCellDropDownSelectionChangedEventArgs object contains the following properties:

* RowColumnIndex: Gets the value of the current RowColumnIndex.
* SelectedIndex: Gets the selected index from the Drop Down control.
* SelectedItem: Gets the selected item from the Drop Down control.

### GridCheckBoxColumn


GridCheckBoxColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn too.  GridCheckBoxColumn does not load Display element and Edit element individually. It just loads Checkbox in that column to make value changes in it. You can change the underlying data source that toggles the values shown in checkbox.

The following provides the list of all properties that supports GridCheckBoxColumn:

 _GridCheckBoxColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
IsThreeState</td><td>
Boolean</td><td>
Specifies whether the Checkbox supports two or three states.(Checked, Unchecked and Intermediate)</td><td>
False</td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
HorizontalAlignments</td><td>
Determines the HorizontalAlignment of the Checkbox in regard with the GridCell.</td><td>
HorizontalAlignment.Center</td></tr>
<tr>
<td>
VerticalAlignment</td><td>
VerticalAlignment</td><td>
Determines the VerticalAlignment of the Checkbox in regard with the GridCell.</td><td>
VerticalAlignment.Center</td></tr>
</table>


The following code example shows how to use GridCheckBoxColumn.



{% highlight xml %}




<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTextColumn MappingName="OrderID" TextAlignment="Right" />

    <syncfusion:GridTextColumn MappingName="UnitPrice" TextAlignment="Right" />

    <syncfusion:GridTextColumn MappingName="Discount" TextAlignment="Right" />

    <syncfusion:GridCheckBoxColumn MappingName="IsClosed" />

    <syncfusion:GridTextColumn MappingName="Quantity" TextAlignment="Right" />

</syncfusion:SfDataGrid.Columns>


{% endhighlight %}


{% highlight C#%}





sfdatagrid.Columns.Add(new GridCheckBoxColumn() { MappingName = "IsClosed" });
{% endhighlight %}




The above XAML Code has resulted in following Output:



![](Features_images/Features_img53.png)



_DataGrid with GridCheckBoxColumn_

N> Due to its behavior (Directly loading CheckBox), it does not fire events of CurrentCellValidating and CurrentCellValidated. You can use CurrentCellValueChanged Event.

 

### GridImageColumn

GridImageColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn too. GridImageColumn displays read-only images for the columns.

The following provides the list of all properties that supports GridImageColumn:

_GridImageColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
Stretch</td><td>
Stretch</td><td>
Determines a value that describes how an image is stretched to fill in the GridCell.</td><td>
Stretch.Uniform</td></tr>
<tr>
<td>
StretchDirection</td><td>
StretchDirection</td><td>
Defines a value that indicates how the image is scaled.</td><td>
StretchDirection.Both</td></tr>
<tr>
<td>
ImageWidth</td><td>
Double</td><td>
Defines the Width for the Image.</td><td>
Double.PositiveInfinity</td></tr>
<tr>
<td>
ImageHeight</td><td>
Double</td><td>
Defines the Height for the Image.</td><td>
Double.PositiveInfinity</td></tr>
</table>


The following code example shows how to use GridImageColumn.


{% highlight xml %}




<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTextColumn MappingName="ProductID" />

    <syncfusion:GridTextColumn HeaderText="Brand" MappingName="ProductModel" />

    <syncfusion:GridImageColumn HeaderText="Image"

                                MappingName="ProductType"

                                Stretch="Uniform" />

    <syncfusion:GridTextColumn HeaderText="Brand" MappingName="Product" />

</syncfusion:SfDataGrid.Columns>

{% endhighlight %}



The above XAML Code has resulted in the following output:



![](Features_images/Features_img54.png)



_DataGrid with GridImageColumn_

### GridHyperlinkColumn

GridHyperlinkColumn is derived from GridColumn, inheriting its properties and its content represented by using the Hyperlink Button. The bound value is represented as a Hyperlink and automatically displayed as a link.

 The following provides the list of all properties that supports GridHyperlinkColumn:

 _GridHyperlinkColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
HorizontalAlignment</td><td>
HorizontalAlignment</td><td>
Determines the horizontal alignment for Hyperlink button in regard with the GridCell</td><td>
HorizontalAlignment.Stretch</td></tr>
<tr>
<td>
VerticalAlignment</td><td>
VerticalAlignment</td><td>
Determines the vertical alignment for Hyperlink button in regard with the GridCell.</td><td>
VerticalAlignment.Stretch</td></tr>
</table>


The following code example illustrates how to use GridHyperlinkColumn.


{% highlight xml %}






<syncfusion:GridHyperlinkColumn DisplayBinding="{Binding Path=ProductName}"

                                HeaderText="Official Product Link"

                                MappingName="ProductName"

                                ValueBinding="{Binding Path=ProductURI}" />


{% endhighlight %}

{% highlight C#%}





sfdatagrid.Columns.Add(new GridHyperlinkColumn() { 

                   HeaderText = "Official Product Link", 

                   MappingName = "ProductName" });

{% endhighlight %}



The following screenshot illustrates the output.



![](Features_images/Features_img55.png)



_DataGrid with GridHyperlinkColumn_

GridHyperlinkcolumn also hosts the CurrentCellRequestNavigate event to facilitate the navigation for the Hyperlink Column. The event rose whenever you try to navigate the Hyperlink. The event handler receives two arguments namely sender that handles SfDataGrid and CurrentCellRequestNavigateEventArgs as objects.

The CurrentCellRequestNavigateEventArgs object contains the following properties:

* RowColumnIndex: Gets the value for CurrentRowColumnIndex.
* NavigateText: Gets the bounded value from ValueMember or Mapping Name for the Hyperlink Button in the GridColumn.
* Handled: Specifies whether the navigation is controlled by the handler or column.
* RowData: Gets the data context by the click on Hyperlink button that is currently selected record.



N> The value that is bounded to the DisplayBinding property displays the value. The value that is bounded to the ValueBinding property is the NavigateText. When ValueBinding value that bounds to the MappingName is not specified, it becomes the NavigateText.

### GridTemplateColumn

DataGrid supports vast number of celltypes.When you require to extend the functionality of GridColumns with your own editor; it is achieved by creating CellTemplate and EditTemplate of GridTemplateColumn.

The following provides the list of all properties that supports GridTemplateColumn.

 _GridTemplateColumn property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
EditTemplate</td><td>
DataTemplate</td><td>
Specifies the data template of cell in edit mode.</td><td>
Null</td></tr>
<tr>
<td>
CellTemplate</td><td>
DataTemplate</td><td>
Specifies the data template of cell in view mode.</td><td>
Null</td></tr>
<tr>
<td>
CellTemplateSelector</td><td>
DataTemplateSelector</td><td>
Gets DataTemplateSelector and apply the template to cell in view.</td><td>
Null</td></tr>
<tr>
<td>
EditTemplateSelector</td><td>
DataTemplateSelector</td><td>
Gets DataTemplateSelector and apply the template to the cell in edit mode.</td><td>
Null</td></tr>
</table>


N> By default, Silverlight does not support TemplateSelectors hence DataGrid too.

The following code example shows templating for GridTemplateColumn. Underlying record will be the DataContext for the CellTemplate and EditTemplate.



{% highlight xml %}




<syncfusion:GridTemplateColumn MappingName="CustomerID">

    <syncfusion:GridTemplateColumn.CellTemplate>

        <DataTemplate>

            <TextBlock FontStyle="Italic"

                       FontWeight="SemiBold"

                       Padding="2,0"

                       Text="{Binding CustomerID}" />

        </DataTemplate>

    </syncfusion:GridTemplateColumn.CellTemplate>

    <syncfusion:GridTemplateColumn.EditTemplate>

        <DataTemplate>

            <Grid HorizontalAlignment="Stretch" VerticalAlignment="Stretch">

                <TextBox FontStyle="Italic"

                         FontWeight="SemiBold"

                         Padding="2,0"

                         Text="{Binding CustomerID,

                                        Mode=TwoWay}" />

            </Grid>

        </DataTemplate>

    </syncfusion:GridTemplateColumn.EditTemplate>

</syncfusion:GridTemplateColumn>

{% endhighlight %}



The above XAML code has resulted in the following output.



![](Features_images/Features_img56.png)


_DataGrid with GridTemplateColumn_

CellTemplateSelector and EditTemplateSelector provide a way to select DataTemplate based on the data object and the data-bound element. The following code example displays how to use TemplateSelector.



{% highlight xml %}




<DataTemplate x:Key="cellTemplate">

    <CheckBox HorizontalAlignment="Center" IsChecked="{Binding Path=EmployeeStatus, Mode=TwoWay}" />

</DataTemplate>

<!-- CELL TEMPLATE -->

<DataTemplate x:Key="maleCellTemplate">

    <TextBlock Foreground="DeepSkyBlue" Text="{Binding EmployeeGender}" />

</DataTemplate>

<DataTemplate x:Key="femaleCellTemplate">

    <TextBlock Foreground="DeepPink" Text="{Binding EmployeeGender}" />

</DataTemplate>

<!-- EDIT TEMPLATE -->

<DataTemplate x:Key="maleEditTemplate">

    <TextBox Foreground="DeepSkyBlue" Text="{Binding EmployeeGender}" />

</DataTemplate>

<DataTemplate x:Key="femaleEditTemplate">

    <TextBox Foreground="DeepPink" Text="{Binding EmployeeGender}" />

</DataTemplate>

{% endhighlight %}


{% highlight C# %}





// TEMPLATE SELECTOR

public class CellTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate (object item, 

DependencyObject container)

{

var dataItem = item as BusinessObjects;

if (dataItem.EmployeeGender == "Male")

return Application.Current.Resources["maleCellTemplate"] as DataTemplate;

else

return Application.Current.Resources["femaleCellTemplate"] as DataTemplate;

}

}

public class EditTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate (object item,

DependencyObject container)

{

var dataItem = item as BusinessObjects;

if (dataItem.EmployeeGender == "Male")

return Application.Current.Resources["maleEditTemplate"] as DataTemplate;

else

return Application.Current.Resources["femaleEditTemplate"] as DataTemplate;

}

}
{% endhighlight %}

{% highlight xml %}




// APPLYING CELLTEMPLATESELECTOR AND EDITTEMPLATESELECTOR

<syncfusion:SfDataGrid x:Name="datagrid"

                       AutoGenerateColumns="False"

                       ColumnSizer="Star"

                       ItemsSource="{Binding GDCSource}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn MappingName="EmployeeName" />

        <syncfusion:GridTextColumn MappingName="EmployeeDesignation" />

        <syncfusion:GridTextColumn MappingName="EmployeeAge" />

        <syncfusion:GridTemplateColumn CellTemplateSelector="{StaticResource cellTemplateSelector}"

                                       EditTemplateSelector="{StaticResource editTemplateSelector}"

                                       MappingName="EmployeeGender" />

        <syncfusion:GridTemplateColumn CellTemplate="{StaticResource cellTemplate}" MappingName="EmployeeStatus" />

        <syncfusion:GridTextColumn MappingName="EmployeeArea" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>

{% endhighlight %}

The following screenshot shows the output for the above code.



![](Features_images/Features_img57.png)



_DataGrid with TemplateSelector_

GridTemplateColumn provides the list of [attached property](http://msdn.microsoft.com/en-IN/library/ms749011(v=vs.110).aspx)  to handle key navigation, mouse interaction, focusing for loaded controls within DataTemplate. You can get below attached properties in Syncfusion.UI.Xaml.Grid namespace.

* FocusManagerHelper.WantsKeyInput
* VisualContainer.WantsMouseInput
* FocusManagerHelper.FocusedElement

### WantsKeyInput

The attached property allows the controls loaded in CellTemplate to handle key navigation within it or by Grid.

The following code example explains you about WantsKeyInput.


{% highlight xml %}



<syncfusion:GridTemplateColumn HeaderText="ProductName"

                               MappingName="ProductName"                               syncfusion:FocusManagerHelper.WantsKeyInput="True">

    <syncfusion:GridTemplateColumn.CellTemplate>

        <DataTemplate>

            <Grid>

                <TextBox x:Name="text" Text="{Binding ProductName}" />

            </Grid>

        </DataTemplate>

    </syncfusion:GridTemplateColumn.CellTemplate>

</syncfusion:GridTemplateColumn>

{% endhighlight %}



N> Enter and Tab keys are always handled by Grid only. When you set it to’ false’, you cannot navigate using keys within a loaded control.

### WantsMouseInput

The attached property allows the controls loaded in CellTemplate to handle mouse interaction within it or by Grid.

The following code example explains you about WantsMouseInput.


{% highlight xml %}



<syncfusion:GridTemplateColumn HeaderText="ProductName" MappingName="ProductName">

    <syncfusion:GridTemplateColumn.CellTemplate>

        <DataTemplate>

            <Grid>

                <ComboBox ItemsSource="{Binding ComboItems, Source={StaticResource viewmodel}}" syncfusion:VisualContainer.WantsMouseInput="True" />

            </Grid>

        </DataTemplate>

    </syncfusion:GridTemplateColumn.CellTemplate>

</syncfusion:GridTemplateColumn>
{% endhighlight %}




#### FocusedElement

The attached property FocusedElement gives the Focus to particular element inside DataTemplate. 

The following code example shows, how to set the FocusedElement inside DataTemplate


{% highlight xml %}



<syncfusion:GridTemplateColumn HeaderText="Order ID" MappingName="OrderID">

    <syncfusion:GridTemplateColumn.CellTemplate>

        <DataTemplate>

            <TextBlock Text="{Binding OrderID}" />

        </DataTemplate>

    </syncfusion:GridTemplateColumn.CellTemplate>

    <syncfusion:GridTemplateColumn.EditTemplate>

        <DataTemplate>

            <Grid>

                <TextBox x:Name="textBox"

                         FontStyle="Italic"

                         FontWeight="SemiBold"

                         Padding="2,0"

                         Text="{Binding OrderID,

                                        Mode=TwoWay}"

                         syncfusion:FocusManagerHelper.FocusedElement="True" />

            </Grid>

        </DataTemplate>

    </syncfusion:GridTemplateColumn.EditTemplate>

</syncfusion:GridTemplateColumn>

{% endhighlight %}



N> Other than the above attached properties supported, you can set focused element by using FocuseManager.FocusedElement attached property which comes in WPF frameowkr itself. This can be used only for EditTemplate and can’t be used inside CellTemplate.

The following XAML code example displays you how to set focus directly to editor.


{% highlight xml %}





<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTemplateColumn HeaderText="Customer ID" MappingName="CustomerID">

        <syncfusion:GridTemplateColumn.CellTemplate>

            <DataTemplate>

                <TextBlock Text="{Binding CustomerID}" />

            </DataTemplate>

        </syncfusion:GridTemplateColumn.CellTemplate>

        <syncfusion:GridTemplateColumn.EditTemplate>

            <DataTemplate>

                <Grid FocusManager.FocusedElement="{Binding ElementName=textBox}">

                    <TextBox x:Name="textBox"

                             FontStyle="Italic"

                             FontWeight="SemiBold"

                             Padding="2,0"

                             Text="{Binding CustomerID,

                                            Mode=TwoWay}" />

                </Grid>

            </DataTemplate>

        </syncfusion:GridTemplateColumn.EditTemplate>

    </syncfusion:GridTemplateColumn>

</syncfusion:SfDataGrid.Columns>

{% endhighlight %}



#### Creating template columns based on MappingName

When you use template column, you can define template for each column and set binding to the underlying data in template regardless of MappingName. In some use cases, you may need to bind template columns based on MappingName and also use same data template for all template columns.This is achieved by changing the Renderer for Template columns as as displayed in the following code example.

The following code example explains you how to remove from Renderer collectionin MainWindow.cs


{% highlight C# %}





sfdatagrid.CellRenderers.Remove("Template");

sfdatagrid.CellRenderers.Add("Template", new GridCellDataTemplateRenderer());

{% endhighlight %}



By default Template column uses GridCellTemplateRenderer that sets Record as DataContext to CellTemplate and EditTemplate. GridCellDataTemplateRenderer is derived from GridCellTemplateRenderer that sets the DataContextHelper as DataContext to CellTemplate and EditTemplate. 

DataContextHelper has the following properties,

* Value – denotes the value from data based on MappingName property
* Record – denotes the underlying data.

Now you can make use of Value property that provides value based on MappingName property. You can use the same template for any number of Columns which will bind the value based on MappingName.

Then your XAML code is as follows. 


{% highlight xml %}





<syncfusion:GridTemplateColumn HeaderText="Order ID" MappingName="OrderID">

    <syncfusion:GridTemplateColumn.CellTemplate>

        <DataTemplate>

            <TextBlock Text="{Binding Value}" />

        </DataTemplate>

    </syncfusion:GridTemplateColumn.CellTemplate>

</syncfusion:GridTemplateColumn>
{% endhighlight %}


### Unbound Columns

SfDataGrid supports the addition of extra columns to the Data Source columns. These additional columns are called as unbound columns, as they do not belong to the Data Source. These unbound fields are used when you want to add additional or custom information to each record.

An unbound column is sorted, grouped, and filtered like other GridColumns. The value of an unbound column updates automatically, when a concerned property on the data item changes. It includes two important properties as follows; Format and Expression that are set. Unbound column also includes another property CaseSensitivity that specifies whether the given expression is case sensitive or not.

* Expression property denotes any valid Arithmatic or logical expression with columns for the UnBoundColumn to compute.
* Format property denotes an expression with a formatting string holding valid columns from the Data Source.

The supported arithmetic operations are as follows: You can use arithmetic operators within two column names such as Expression= “Quantity + UnitPrice.”

_List of Arithmetic operators_

<table>
<tr>
<th>
Operations</th><th>
Operators</th></tr>
<tr>
<td>
Add</td><td>
+</td></tr>
<tr>
<td>
Subtract</td><td>
-</td></tr>
<tr>
<td>
Multiply</td><td>
*</td></tr>
<tr>
<td>
Divide</td><td>
/</td></tr>
<tr>
<td>
Power</td><td>
^</td></tr>
<tr>
<td>
Mod</td><td>
%</td></tr>
<tr>
<td>
Greater Than</td><td>
></td></tr>
<tr>
<td>
Lesser Than</td><td>
<</td></tr>
<tr>
<td>
Equal</td><td>
=</td></tr>
<tr>
<td>
GreaterThanOrEqual</td><td>
>=</td></tr>
</table>


The supported logical operations are as follows. You have to use logical operation like Expression = “Quantity > UnitPrice” + (char) 135 + “Quantity! = UnitPice” from code behind.

_List of Logical operators_

<table>
<tr>
<th>
Operations</th><th>
Operators</th></tr>
<tr>
<td>
AND</td><td>
(char)135</td></tr>
<tr>
<td>
OR</td><td>
(char)136</td></tr>
<tr>
<td>
NOT</td><td>
(char)137</td></tr>
</table>


N> It is mandatory to specify the GridColumn.MappingName to the UnBoundColumn, but it should not match with any existing fields in the data source.

The following code example shows how to use unboundcolumns in the DataGrid control.


{% highlight xml %}





<syncfusion:SfDataGrid AllowEditing="True"

                       ColumnSizer="Auto"

                       ItemsSource="{Binding SalesInfo}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn MappingName="Product" />

        <syncfusion:GridTextColumn MappingName="Quantity" TextAlignment="Right" />

        <syncfusion:GridTextColumn DisplayBinding="{Binding Path=Amount,

                                                            StringFormat='{}{0:C}'}"

                                   MappingName="Amount"

                                   TextAlignment="Right" />

        <!--  UnBoundColumn with Expressions  -->

        <syncfusion:GridUnBoundColumn AllowEditing="False"

                                      Expression="Quantity*Amount"

                                      HeaderText="Grand Total"

                                      MappingName="GrandTotal"

                                      TextAlignment="Right" />

        <!--  UnBoundColumn with Format  -->

        <syncfusion:GridUnBoundColumn Width="180"

                                      AllowEditing="False"

                                      Format="'{Amount} for {Product}'"

                                      MappingName="Amount for Product" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>

{% endhighlight %}

The following screenshot shows the output.



![](Features_images/Features_img58.png)

 _DataGrid with Unbound columns_

### Events

An unboundcolumn provides the QueryUnboundColumnValue event that is raised when the UnboundColumn is initialized and updated. The event includes two arguments, namely sender that handles SfDataGrid and GridUnBoundColumnEventArgs as Objects.

GridUnBoundColumnEventArgs object contains the following properties:

* Column: Gets the GridColumn for the UnBoundColumn.
* Record: Gets the current record where the values are computed for the unbound cell.
* UnBoundAction: Gets the action for the event, i.e., whether the event is Querying the data or Committing the data.
* Value: Gets or sets the value for the UnBoundColumn.

GridUnBoundColumn provides a special property that bounds a value when given Expression columns names are not equal case. The following code example illustrates that.


{% highlight xml %}





<syncfusion:GridUnBoundColumn AllowEditing="True"

                              AllowFiltering="True"

                              AllowGrouping="True"

                              AllowSorting="True"

                              CaseSensitive="False"

                              Format="'{ProductName}-{quantity}'"

                              MappingName="Total" />

{% endhighlight %}



The following screenshot displays you the output.



![UnboundColumn1](Features_images/Features_img59.png)



_DataGrid with GridUnBoundColumn_



In above case, when you set CaseSenstive property value to ‘true’, then you can not get quantity column value after that hyphen. 

N> UnBound Column’s Expression does not work with DataTable, since DataTable itself provides support for Expression.

### GridMultiColumnDropDownList

GridMultiColumnDropDownList is derived from GridColumn, inheriting its properties and has few additional properties. GridMultiColumnDropDownList loads SfMultiColumnDropDownControl for editing. In addition to the GridColumn’s properties, GridMultiColumnDropDownList supports the following list of properties:

_GridMultiColumnDropDownList property table_

<table>
<tr>
<th>
Property Name</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
DisplayMember</td><td>
String</td><td>
Determines the field in the data bound source, whose value is displayed in the Editor.</td><td>
String.Empty</td></tr>
<tr>
<td>
ValueMember</td><td>
String</td><td>
Determines the field in the data bound source that computes the SelectedValue.</td><td>
String.Empty</td></tr>
<tr>
<td>
ShowResizeThumb</td><td>
Visibility</td><td>
Specifies whether resizing thumb is visible or not.</td><td>
Visibility.Visible</td></tr>
<tr>
<td>
PopUpHeight</td><td>
Double</td><td>
Defines the height of the Pop-up.</td><td>
0.0d</td></tr>
<tr>
<td>
PopUpWidth</td><td>
Double</td><td>
Defines the width of the Pop-up.</td><td>
0.0d</td></tr>
<tr>
<td>
ItemsSource</td><td>
Object</td><td>
Determines the data source (IEnumerable) used to generate the content for the SfDataGrid present inside the DropDownPopup. The Data Source is of any type ranging from ObservableCollection&lt;T&gt; to DynamicObjects.</td><td>
Null</td></tr>
<tr>
<td>
AllowAutoComplete</td><td>
Boolean</td><td>
This propertyis Boolean properties that represent the behavior of the Editor, and specifies whether to enable or disable suggestion text for auto completion of text. </td><td>
True</td></tr>
<tr>
<td>
AllowNullInput</td><td>
Boolean</td><td>
Specifies whether the editor accepts null value or not.</td><td>
False</td></tr>
<tr>
<td>
AutoGenerateColumns</td><td>
Boolean</td><td>
Specifies a value whether the columns are auto generated by the DataGrid in the Dropdowngrid, or generated based on the AutoGenerateColumnsMode.</td><td>
true</td></tr>
<tr>
<td>
AutoGenerateColumnsMode</td><td>
AutoGenerateColumnsMode</td><td>
Specifies whether columns are created automatically for all the fields in the underlying Data Source</td><td>
Reset</td></tr>
<tr>
<td>
Columns</td><td>
Columns</td><td>
This is a collection of GridColumns that helps to generate columns based on the given GridColumns (For information about GridColumns, see {{ '[Columns](http://help.syncfusion.com/ug/wpf/sfdatagrid/default.htm)' | markdownify }}).</td><td>
new Columns()</td></tr>
<tr>
<td>
GridColumnSizer</td><td>
GridLengthUnitType</td><td>
Specifies the columnsizer mode for a dropdowngrid in GridMultiColumnDropDownList column.</td><td>
GridLengthUnitType.None</td></tr>
<tr>
<td>
IsAutoPopupSize</td><td>
Bool</td><td>
Specifies a value that agrees whether the size of the Pop-up is based on the actual size of the Grid.</td><td>
False</td></tr>
</table>


The following code example illustrates how to use GridMultiColumnDropDownList.


{% highlight xml %}



<syncfusion:GridMultiColumnDropDownList AutoGenerateColumns="False"

                                        DisplayMember="CustomerID"

                                        GridColumnSizer="Auto"

                                        IsAutoPopupSize="False"

                                        ItemsSource="{Binding OrderList}"

                                        MappingName="CustomerID "

                                        ValueMember="CustomerID ">

    <syncfusion:GridMultiColumnDropDownList.Columns>

        <syncfusion:Columns>

            <syncfusion:GridTextColumn MappingName=" CustomerID " />

            <syncfusion:GridTextColumn MappingName="OrderID" />

        </syncfusion:Columns>

    </syncfusion:GridMultiColumnDropDownList.Columns>

</syncfusion:GridMultiColumnDropDownList>


{% endhighlight %}


The above XAML code has resulted in the following output.



![](Features_images/Features_img60.png)



_DataGrid with GridMultiColumnDropDownList_

The event associated with this column is CurrentCellDropDownSelectionChanged Event

This event occurs whenever a selected item is changed in DropDown column such as GridMultiColumnDrpDownList. The event handler receives two arguments namely sender that handles SfDataGrid and CurrentCellDropDownSelectionChangedEventArgs as objects.

N> To set null value in view, the underlying type needs to be Nullable. Only then it accepts Null value.



The CurrentCellDropDownSelectionChangedEventArgs object contains the following properties:

### Column Sizing

ColumnSizer property allows you to specify the column width based on the data present in the cell. You can set the ColumnsSizer property like SfDataGrid.ColumnSizer. This section explains you different options to set width of each Column and how to customize the GridColumnSizer. Following are the lists of options available to set width of the Columns.

* RowColumnIndex: Gets the value of the current RowColumnIndex.
* SelectedIndex: Gets the selected index from the DropDown control.
* SelectedItem: Gets the selected item from the DropDown control.



N> To set null value in view, the underlying type needs to be Nullable. Only then it accepts Null value.




* Auto
* AutoWithLastColumnFill
* SizeToCells
* SizeToHeader
* Star
* None


#### GridLengthUnitType.Auto

In Auto type, column’s width of the DataGrid control is adjusted with respect to the cell and header content, i.e., each column's header length and cell content length are considered.

#### GridLengthUnitType.AutoWithLastColumnFill

In AutoWithLastColumnFill type, the column width of the DataGrid control is adjusted with respect to cell and header content. The last column's width fills the unoccupied space in the parent framework element.

#### GridLengthUnitType.SizeToCells

In SizeToCells type, the column width in the DataGrid control is adjusted with respect to cell content.

#### GridLengthUnitType.SizeToHeader

In SizeToHeader type, column’s width of the DataGrid control is adjusted with respect to header content.

#### GridLengthUnitType.Star

In Star type, the control content occupies total space in the parent, and column’s width is divided equally based on the total space. It’s not required to specify the width for every Grid Column. 

#### GridLengthUnitType.None

No Column sizing is applied when the SfDataGrid.ColumnSizer is set to ‘None’. Columns are arranged in the default Column width.

#### Properties

SfDataGrid.ColumnSizer: This property applies the Column sizing for all the columns in the DataGrid control. By default the SfDataGrid.ColumnSizer is set to GridControlLengthUnitType_._None.

The DataGrid control also allows you to set the column sizing for a particular column. Grid Column contains following properties for Column sizing:

* GridColumn.ColumnSizer: You can set the ColumnSizer for particular columns by using this property. When you declare the ColumnSizer property in DataGrid control as well as in Column, Grid resizes the column based on the ColumnSizer value in the column.
* GridColumn.MinimumWidth: Sets the Minimum Width of the column.
* GridColumn.MaximumWidth: Sets the Maximum Width of the column.
* GridColumn.Width: Sets the Width of the column.




N> DataGrid control applies column sizing based on Width, MinimumWidth and MaximumWidth properties.



* The Grid resizes the column based on the GridColumn.ColumnSizer property instead of the SfDataGrid.ColumnSizer property when you set the GridColumn.ColumnSizer property explicitly. 
* For example, when you set SfDataGrid.ColumnSizer property to ‘Auto’, and for a particular column you have set GridColumn.ColumnSizer property to ‘Star’, DataGrid applies ‘Star’ column sizing for that particular column and ‘Auto’ column sizing for all other columns.
* When you set both the GridColumn.ColumnSizer and GridColumn.Width properties, the Grid resizes the column based on the GridColumn.Width value.
* When you set both the GridColumn.MaximumWidth and GridColumn.Width properties, the Grid resizes the column in the following ways:
* When the GridColumn.Width value is lesser than GridColumn.MaximumWidth, DataGrid resizes the column to the GridColumn.Width value.
* Else, DataGrid resizes the column to GridColumn.MaximumWidth value.
* When you set GridColumn.MinimumWidth, GridColumn.MaximumWidth and GridColumn.Width properties, Grid resizes the column in the following ways:
* When the GridColumn.Width value is lesser than the GridColumn.MaximumWidth and greater than GridColumn.MinimumWidth, DataGrid resizes the column to the GridColumn.Width value.
* Else, DataGrid resizes the column with the maximum GridColumn.MinimumWidth and GridColumn.MaximumWidth values.




N> When you resize the columns and the Columns sizer is in ‘Star’ or ‘AutoWithLastFill’ mode, it remains its behavior.

The following code example illustrates you how to set the ColumnSizing option for DataGrid control.


{% highlight xml %}





<syncfusion:SfDataGrid x:Name="datagrid"

                        ColumnSizer="Star"

                        ItemsSource="{Binding OrdersDetails}" />
{% endhighlight %}


{% highlight C# %}






sfdatagrid.ColumnSizer = GridLengthUnitType.Star;

{% endhighlight %}



The following screenshot illustrates the output.



![](Features_images/Features_img61.png)



_DataGrid with Column Sizing_

### Customize column sizer using GridColumnSizer

GridColumnSizer is the public class that handles the operations to set grid column's width based on column sizer and column width. Following are the list of properties and methods to be considered when you calculate column width.

_GridColumnSizer methods table_

<table>
<tr>
<th>
Method </th><th>
Description</th></tr>
<tr>
<td>
internal protected virtual double CalculateAutoFitWidth(GridColumn column, bool isAuto = false)</td><td>
Called to calculate column width based on “Auto” column sizer</td></tr>
<tr>
<td>
protected virtual double CalculateCellWidth(GridColumn column, bool setWidth = true)</td><td>
Called to calculate column width based on “SizeToCells” column sizer</td></tr>
<tr>
<td>
protected virtual double CalculateHeaderWidth(GridColumn column, bool setWidth = true)</td><td>
Called to calculate column width based on “SizeToHeader” column sizer</td></tr>
<tr>
<td>
protected virtual double GetAutoWidth(GridColumn column)</td><td>
Method used to get column width when column sizer is SizeToCells or Auto</td></tr>
<tr>
<td>
protected virtual ContentControl GetContentControl(GridColumn column, object record)</td><td>
Called to get content control to measure the template  when column sizer is SizeToCells</td></tr>
<tr>
<td>
protected virtual string GetDisplayText(GridColumn column, object record)</td><td>
Called to get display value for calculating column width based on cell value</td></tr>
<tr>
<td>
protected virtual TextBlock GetTextBlock(GridColumn column, object record)</td><td>
Called to get TextBlock to measure the text when column sizer is SizeToCells or Auto</td></tr>
<tr>
<td>
protected virtual Size MeasureTemplate(object record, GridColumn column)</td><td>
Called to measure template when column sizer is SizeToCells or Auto</td></tr>
<tr>
<td>
protected virtual Size MeasureText(Size rectangle, string displayText, GridColumn column, object record)</td><td>
Called to measure text when column sizer is SizeToCells or Auto</td></tr>
<tr>
<td>
protected virtual void OnColumnPropertyChanged(GridColumn column, string property)</td><td>
Invoked to refresh the column widths when ColumnSizer,Width, AllowSorting and other column properties changed for GridColumn</td></tr>
<tr>
<td>
public void Refresh()</td><td>
Refreshes column widths when column sizer and grid size changed</td></tr>
<tr>
<td>
protected virtual void Refresh(double AvailableWidth)</td><td>
Refreshes column widths when column sizer and grid size changed</td></tr>
<tr>
<td>
public void ResetAutoCalculation(GridColumn column)</td><td>
Reset Auto width calculation for the particular column</td></tr>
<tr>
<td>
public void ResetAutoCalculationforAllColumns()</td><td>
Reset Auto width calculation for all the columns</td></tr>
<tr>
<td>
protected internal void Resume()</td><td>
Used to resume the column width refresh when column propertychanged is called</td></tr>
<tr>
<td>
public virtual double SetColumnWidth(GridColumn column, double Width)</td><td>
Called to set the column width based on MinimumWidth and MaximumWidth</td></tr>
<tr>
<td>
protected virtual double SetNoneWidth(GridColumn column, double width)</td><td>
Called to set column width based on None column sizer</td></tr>
<tr>
<td>
private void SetSizerWidth(double viewPortWidth)</td><td>
Called to set column width based on Star column sizer</td></tr>
<tr>
<td>
protected internal void Suspend()</td><td>
Used to suspend the column width refresh when column propertychanged is called </td></tr>
<tr>
<td>
public boolean GetAutoRowHeight(int RowIndex, GridRowSizingOptions options, out double rowHeight)</td><td>
Used to cacluate the row height based on the content that located in the grid cells of the row.</td></tr>
</table>


<table>
<tr>
<td>
> {{ 'N> The above methods are useful when you create custom GridColumnSizer for SfDataGrid.' | markdownify }}</td></tr>
<tr>
<td>
</td></tr>
</table>
_GridColumnSizer Properties table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
Default Value</td></tr>
<tr>
<td>
ContentControl</td><td>
ContentControl</td><td>
Gets or sets the ContentControl to calculate cell width for template column</td><td>
null</td></tr>
<tr>
<td>
DataGrid</td><td>
SfDataGrid</td><td>
Gets the SfDataGrid instance</td><td>
null</td></tr>
<tr>
<td>
FilterIconWidth</td><td>
Double</td><td>
Gets or sets the FilterIconWidth to calculate the header width when column sizer is SizeToHeader or Auto</td><td>
28</td></tr>
<tr>
<td>
FontFamily</td><td>
FontFamily</td><td>
Gets or sets the FontFamily to calculate the width of the column based on cell value</td><td>
new FontFamily("Segoe UI")</td></tr>
<tr>
<td>
FontSize</td><td>
Double</td><td>
Gets or sets the FontSize to compute the width of the column based on cell value</td><td>
12</td></tr>
<tr>
<td>
Margin</td><td>
Thickness</td><td>
Gets or sets the Margin to compute the width of column based on cell value </td><td>
new Thickness(5, 1, 5, 1)</td></tr>
<tr>
<td>
SortIconWidth</td><td>
Double</td><td>
Gets or sets the SortIconWidth to calculate the header width when column sizer is SizeToHeader or Auto</td><td>
25</td></tr>
<tr>
<td>
TextBlock</td><td>
TextBlock</td><td>
Gets or sets the TextBlock to calculate cell width for the column</td><td>
null</td></tr>
</table>


#### Overriding and handling GridColumnSizer

The following code example illustrates to override methods and how to handle operations in GridColumnSizer. The extended class GridColumnSizerExt is new GridColumnSizer and you can assign it to existing GridColumnSizer.


{% highlight C# %}



// Assign custom GridColumnSizer to datagrid GridColumnSizer

dataGrid.GridColumnSizer = new GridColumnSizerExt(dataGrid);

…

    /// <summary>

    /// GridColumnSizerExt class is the custom GridColumnSizer

    /// </summary>



public class dColumnSizerExt : GridColumnSizer

{

   public GridColumnSizerExt(SfDataGrid grid)

                : base(grid)

   {

   }

        /// <summary>

        /// Calculate Width for Column When Column Sizer is SizeToCells

        /// </summary>

        /// <param name="column">GridColumn</param>

        /// <returns>column width</returns>     

     protected override double CalculateCellWidth(GridColumn column, bool setWidth = true)

          {

                return base.CalculateCellWidth(column, setWidth);

          }

           /// <summary>

           /// Calculate Width for column when ColumnSizer is SizeToHeader

           /// HeaderCell width is calculated based on headertext, sorticon and   filter icon

           /// </summary>

           /// <param name="column">GridColumn</param>

           /// <returns>column width</returns>      

          protected override double CalculateHeaderWidth(GridColumn column, bool setWidth = true)

          {

                return base.CalculateHeaderWidth(column, setWidth);

          }

}
{% endhighlight %}

## Hiding Columns

The DataGrid control provides support to hide a particular Column in XAML or C# by setting the GridColumn.IsHidden property to ‘true’.

The following code example shows how to hide the Columns in XAML.


{% highlight xml %}





<syncfusion:SfDataGrid AutoGenerateColumns="False"

                       ColumnSizer="Auto"

                       ItemsSource="{Binding OrderInfoCollection}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn HeaderText="Order ID"

                                   IsHidden="True"

                                   MappingName="OrderID" />

        <syncfusion:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />

        <syncfusion:GridTextColumn HeaderText="Name of Customer" MappingName="CustomerName" />

        <syncfusion:GridTextColumn HeaderText="Ship Country" MappingName="ShipCountry" />

        <syncfusion:GridTextColumn HeaderText="Ship City" MappingName="ShipCity" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight C# %}





((GridTextColumn)sfdatagrid.Columns["OrderID"]).IsHidden = true;
{% endhighlight %}


N> Hidden columns are not considered when applying column sizing.

## Resizing Columns

This section explains you how to resize the Columns and how to handle event that arises when resizing columns.

### Overview

DataGrid allows you to resize the Column at Execute time. By default, resizing the columns is disabled in Grid.

The following is the list of properties that participate in resizing columns.

* AllowResizingColumns
* AllowResizingHiddenColumns

To enable resizing you can set SfDataGrid.AllowResizingColumns property value to _‘_True’. DataGrid also allows you to enable or disable the resizing functionality for a particular column by using the GridColumn.AllowResizing property.

When resizing functionality enabled, Grid shows a resizing cursor during hovering at the edge of the column header as shown in the following screenshot:

![](Features_images/Features_img62.png)



_DataGrid with resizing cursor for resizing columns_

Hidden columns are resized by enabling SfDataGrid.AllowResizingHiddenColumns property.

The following screenshot displays how Hidden columns are displayed when AllowResizingHiddenColumns property is enabled.



![](Features_images/Features_img63.png)



_DataGrid with AllowResizingHiddenColumns property enabled_





![](Features_images/Features_img64.png)



_DataGrid with with resizing cursor for hidden columns_

The event that participates in resizing is ResSizingColumns. Resize event support resizing action 

#### SfDataGrid.ResizingColumns

This event occurs when the column in the DataGrid is about to resize or is being resized by you.

The ResizingColumns event handler receives two arguments sender that handles SfDataGridtype and ResizingColumnsEventArgs as objects.

The ResizingColumnsEventArgs object has the following properties:

* ColumnIndex: Gets or sets the column index of the reizing or resized column.
* Width : Gets or setsthe width of the reizing or resized column 
* Cancel: When this property is set to ‘true’, the event is cancelled and the column is not resized.

The following code example illustrates how to cancel the ResizingColumn. 


{% highlight xml %}




<syncfusion:SfDataGrid x:Name="sfdatagrid"

                       AllowEditing="{Binding ElementName=AllowEdit,

                                      Path=IsChecked}"

                       AllowResizingColumns="True"

                       AllowResizingHiddenColumns="True"

                       ItemsSource="{Binding OrderList}"

                       LiveDataUpdateMode="AllowDataShaping"                      

                       ShowRowHeader="True">

{% endhighlight %}



You need to wire ResizingColumns event for SfDataGrid. You can refer the following method. From event args, you can cancel it. Now the columns are not resized. The indication of resizing is shown, but it is not resized.


{% highlight C# %}





sfdatagrid.AllowResizingColumns = true;

sfdatagrid.AllowResizingHiddenColumns = true;



sfdatagrid.ResizingColumns += sfdatagrid_ResizingColumns;



void sfdatagrid_ResizingColumns(object sender, ResizingColumnsEventArgs e)

{

    e.Cancel = true;

}
{% endhighlight %}


N> Resizing is restricted based on GridColumn.MinimumWidth and GridColumn.MaximumWidth.You can resize the columns to the Header and Cell text by double-clicking the header gridlines.

## Reordering Columns

This section explains you about Reordering of Columns and how to handle event that participates in Reordering Columns.

### Overview

The DataGrid control provides the drag-and-drop functionality to rearrange the Columns at Execute time. You can drag a particular column and drop the column where you need it. By default, the drag-and-drop functionality is disabled in the DataGrid control. 

By using the SfDataGrid.AllowDraggingColumns property you can enable or disable the drag-and-drop functionality in the Grid. The DataGrid control also allows you to enable or disable the drag-and-drop functionality for a particular column by using the GridColumn.AllowDragging property.

You can drag the column using the mouse. DataGrid also provides extensive support for dragging columns in touch devices. When you press and hold the hand on column header, a pop-up window is displayed over the column header. You can then rearrange the Columns.

The following screenshot illustrates how to drag the column.

![](Features_images/Features_img65.png)


_Dragging column in DataGrid_

The event that participates in ReOredering is QueryColumnDragging. It arises when you start dragging a column. QueryColumnDragging event handler receives two arguments sender that handles SfDataGrid and QueryColumnDraggingEventArgs as objects. 

The QueryColumnDraggingEventArgs object has following properties.

* Cancel: you can stop dragging the Columns by setting ‘true’ to cancel.
* PopupPosition: You can get position of point where you drag or drop.
* From: you can get the index of column that you start dragging.
* To: you can get the index of column where you move.
* Reason: This property returns QueryColumnDraggingReason value.

QueryColumnDraggingReason has following enum values.

* DragStarting
* DragStarted
* Dragging
* Dropping
* Dropped

When you want to disable dragging for a particular column you can use this event and cancel the dragging of column.

### Drag and Drop Customization

By default, Column drag-and-drop operations are handled by GridColumnDragDropController class. You can achieve drag-and-drop customization by overriding the methods in GridColumnDragDropController class.

#### Virtual methods in GridColumnDragDropController class:

_Virtual methods in GridColumnDragDropController class table_

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
CanShowPopup</td><td>
CanShowPopup(GridColumn column)</td><td>
Returns whether the column shows pop-up for its header or not.</td></tr>
<tr>
<td>
OnColumnHiddenChanged</td><td>
OnColumnHiddenChanged(GridColumn column)</td><td>
Occurs when GridColumn’s Hidden property value is changed. </td></tr>
<tr>
<td>
OnPopupContentDropped</td><td>
OnPopupContentDropped(Point point)</td><td>
Occurs when the dragged popup is dropped.</td></tr>
<tr>
<td>
OnPopupContentPositionChanged</td><td>
OnPopupContentPositionChanged(double HorizontalDelta, double VerticalDelta, Point mousePoint, Point mousePointOverGrid)</td><td>
Occurs when popup position changes while dragging.</td></tr>
<tr>
<td>
PointToGridRegion</td><td>
PointToGridRegion(Point point)</td><td>
Called to find the GridRegion at a given point.</td></tr>
<tr>
<td>
CreatePopupContent </td><td>
CreatePopupContent(GridColumn column)</td><td>
Called when pop-up content is created.</td></tr>
<tr>
<td>
PopupContentDroppedOnGroupDropArea</td><td>
PopupContentDroppedOnGroupDropArea(GridColumn column)</td><td>
Called when a draggable pop-up is dropped on a GroupDropArea part</td></tr>
<tr>
<td>
PopupContentDroppedOnHeaderRow</td><td>
PopupContentDroppedOnHeaderRow(int oldIndex, int newColumnIndex)</td><td>
Called when a draggable pop-up is dropped on HeaderRow part</td></tr>
<tr>
<td>
PopupContentDroppedOnGrid</td><td>
PopupContentDroppedOnGrid(Point point)</td><td>
Called when a draggable pop-up is dropped on Grid part</td></tr>
</table>


We have added the Textbox inside the column when it is dragging and also we have added text as DraggingColumn in textbox. The below code sample illustarte this the different override methods available in GridColumnDragDropController.


{% highlight C# %}





this.dataGrid.GridColumnDragDropController = new CustomDragDrop(dataGrid);



public class CustomDragDrop : GridColumnDragDropController 

{

    public CustomDragDrop(SfDataGrid sfdatagrid):base(sfdatagrid)

    {



    }

    protected override System.Windows.UIElement CreatePopupContent(GridColumn column)

    {

        //You can use your own UIElement here.

                 return base.CreatePopupContent(column);

    }



    protected override void PopupContentDroppedOnGroupDropArea(GridColumn column)

    {          

        base.PopupContentDroppedOnGroupDropArea(column);                       

    }



    protected override void OnPopupContentDropped(System.Windows.Point point, System.Windows.Point pointOverGrid)

    {

        base.OnPopupContentDropped(point, pointOverGrid);

    }



    protected override void OnPopupContentPositionChanged(double HorizontalDelta, double VerticalDelta, System.Windows.Point mousePoint, System.Windows.Point mousePointOverGrid)

    {

        base.OnPopupContentPositionChanged(HorizontalDelta, VerticalDelta, mousePoint, mousePointOverGrid);        

    }

}

{% endhighlight %}

How to remove column when dragging and leaving outside the Grid?

You can achieve this using QueryColumnDragging. You need to hook this event from SfDataGrid.

The following code example explains you how to remove column when it’s dropped out side of the Grid.


{% highlight C# %}





this.dataGrid.QueryColumnDragging += dataGrid_QueryColumnDragging;



void dataGrid_QueryColumnDragging(object sender, Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs e)

{

    if (e.Reason == QueryColumnDraggingReason.Dropping)

    {              

        var rect = GetControlRect(this.dataGrid);

        if (!rect.Contains(e.PopupPosition))

        {

            var column = dataGrid.Columns[e.From];                  

            dataGrid.Columns.Remove(column);

        }

    }

}

public Rect GetControlRect(FrameworkElement control)

{

    Point locationfromWindow = control.TranslatePoint(new Point(0, 0), control);

    Point locationfromScreen = control.PointToScreen(locationfromWindow);

    return new Rect((locationfromScreen.X - locationfromWindow.X),

                        (locationfromScreen.Y - locationfromWindow.Y),

                        control.ActualWidth, control.ActualHeight);

}

{% endhighlight %}

## Frozen Columns

The DataGrid control provides extensive support to freeze the columns in horizontal scrolling. To freeze the column, you have to set the number of columns by using the SfDataGrid.FrozenColumnCount property. 

The following code example illustrates freezing two columns.

{% highlight xml %}






<syncfusion:SfDataGrid x:Name="syncgrid"

                       FrozenColumnCount="2"

                       ItemsSource="{Binding OrderInfoCollection}" />

{% endhighlight %}


{% highlight C# %}





this.dataGrid.FrozenColumnCount = 2;

{% endhighlight %}



The following screenshot illustrates the output.



![](Features_images/Features_img66.png)


_DataGrid with two Frozen columns_

N> In the above screenshot, the OrderID and CustomerID columns are frozen. When you group the columns, indent column (while group you can see that another column is created with grouped expander) is also frozen.

### Limitation

FrozenColumnCount should be lesser than number of Colums that can be displayed in View.

### For example:

Your defined columns count is Eight. You can set Frozen Column count as Four.

When your window displays only 4 columns, then you cannot scroll it to view other 4 columns. So you have to set FrozenColumnCount lesser than a number of columns in view.

### Stacked Headers 

DataGrid allows you to have additional unbound header rows, known as Stacked Header Rows that span across Grid Columns. You can group two or more columns under each of the Stacked Header.

### Overview

Stacked Header Row for the given DataGrid is loaded under Stacked Header Rows Collection.  This collection has definitions for Stacked Header Row that contains StackedColumns controlling the behavior and appearance of the Stacked Header.  A Stacked Header Row is viewed as a set of Stacked Columns where each StackedColumn contains a number of Child Columns. When the Child Columns in the Stacked Header is dragged and dropped to another area of columns, the Child Column isolates itself with its own Stacked Header in the dropped position.

N> Stacked Header does not participate in grouping, filtering, sorting and dragging. However, the Child Columns are allowed to group, sort or apply filter.

StackedColumn provides the following properties for implementing StackedHeaders.

* ChildColumns: Gets or sets string of Grid Columns separated by comma (,) to be grouped under the header. Commas are used as a separator for specifying list of Child Columns.
* HeaderText: Gets or sets a string for Stacked Header Text.

The following code example illustrates how to create StackedHeaders.


{% highlight xml %}



<syncfusion:SfDataGrid.StackedHeaderRows>

    <syncfusion:StackedHeaderRow>

        <syncfusion:StackedHeaderRow.StackedColumns>

            <syncfusion:StackedColumn ChildColumns="OrderID,CustomerID,EmployeeID,ShipCity,ShipCountry, Freight,OrderedDate,ShipPostalCode" HeaderText="Order Shipment Details" />

        </syncfusion:StackedHeaderRow.StackedColumns>

    </syncfusion:StackedHeaderRow>

    <syncfusion:StackedHeaderRow>

        <syncfusion:StackedHeaderRow.StackedColumns>

            <syncfusion:StackedColumn ChildColumns="OrderID,CustomerID,Freight,EmployeeID" HeaderText="Order Details" />

            <syncfusion:StackedColumn ChildColumns="ShipCity,ShipCountry,ShipPostalCode" HeaderText="Ship Details" />

        </syncfusion:StackedHeaderRow.StackedColumns>

    </syncfusion:StackedHeaderRow>

</syncfusion:SfDataGrid.StackedHeaderRows>

{% endhighlight %}



The following screenshot displays the output for the above XAML code.



![](Features_images/Features_img67.png)



_DataGrid with Stacked Headers_

## How To

### How to wrap text in Column header

When you have header text that has more length then you need to set it in a multiline. You can achieve this by using HeaderTemplate in Grid Column.

The following code example illustrates this.


{% highlight xml %}



<syncfusion:GridTextColumn DisplayBinding="{Binding Path=OrderID}">

    <syncfusion:GridTextColumn.HeaderTemplate>

        <DataTemplate>

            <TextBlock Text="OrderID of product has been purchased" TextWrapping="Wrap" />

        </DataTemplate>

    </syncfusion:GridTextColumn.HeaderTemplate>

</syncfusion:GridTextColumn>
{% endhighlight %}




The following screenshot illustrates the output.



![](Features_images/Features_img68.png)



_DataGrid with wrapped Header text_

N> You need to set HeaderRowHeight in SfDataGrid to differentiate TextWrap in columnHeader. SfDataGrid.HeaderRowHeight = “100”;

### How to skip AutoGenerate column for particular property

When you set AutoGenerateColumns to ‘true’, columns are generated based on [attributes](http://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations(v=vs.110).aspx) specified in the Model. You can achieve this in following ways.

#### Using DisplayAttribute


{% highlight C# %}



[Display(AutoGenerateField= false,Description="This filed is not created")]

public int OrderID

{

    get { return orderID; }

    set { orderID = value; }

}
{% endhighlight %}


AutoGenerateField disabled in Display attribute does not create the column.

#### Using BindableAttribute


{% highlight C# %}



[Bindable(false)]

public string CustomerName

{

    get { return customerName; }

    set { customerName = value; }

}
{% endhighlight %}


The property for which you have disabled Bindable, that property is added to columns collection.

#### Using AutoGeneratingColumns Event.


{% highlight C# %}



void sfdatagrid_AutoGeneratingColumn(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs e)

{

    if (e.Column.MappingName == "Country")                

        e.Cancel = true;          

}
{% endhighlight %}

### How to override existing Cell types?

In SfDataGrid each column has associated renderers that are added in DataGrid.CellRenderers collection. You can remove and add it back by your customized renderer. The following code example explains you how to override existing renderer. Render is respnisble for all key navigation and other interaction to associated column.


{% highlight C# %}



public class GrdiCellTextBoxRendererExt: GridCellTextBoxRenderer

{

    protected override bool ShouldGridTryToHandleKeyDown(KeyEventArgs e)

    {

        // TODO ACTION

    }

}
{% endhighlight %}


You can derive the required renderer and you can customize using override methods available in it.


{% highlight C# %}



public MainWindow()

{

    InitializeComponent();                        

    sfdatagrid.CellRenderers.Remove("TextBox");

    sfdatagrid.CellRenderers.Add("TextBox", new GrdiCellTextBoxRendererExt());            

}
{% endhighlight %}


The key argument that is used to remove is renderer name.You can add it back by using the name of renderer name with your Customized renderer (GrdiCellTextBoxRendererExt) name. You can do this for different Cell types. Available renderers for Columns in SfDataGrid are as folllows.

_List of renderers for columns in DataGrid_

<table>
<tr>
<th>
Column</th><th>
Renderer Name</th><th>
Renderer</th></tr>
<tr>
<td>
GridTextColumn</td><td>
TextBox </td><td>
GridCellTextBoxRenderer</td></tr>
<tr>
<td>
GridCheckBoxColumn</td><td>
CheckBox </td><td>
GridCellCheckBoxRenderer</td></tr>
<tr>
<td>
GridTemplateColumn</td><td>
Template </td><td>
GridCellTemplateRenderer</td></tr>
<tr>
<td>
GridImageColumn</td><td>
Image </td><td>
GridCellImageRenderer</td></tr>
<tr>
<td>
GridUnBoundColumn</td><td>
UnBoundColumn       </td><td>
GridCellUnBoundColumnRenderer</td></tr>
<tr>
<td>
GridComboBoxColumn</td><td>
ComboBox </td><td>
GridCellComboBoxRenderer</td></tr>
<tr>
<td>
GridNumericColumn</td><td>
Numeric </td><td>
GridCellNumericRenderer</td></tr>
<tr>
<td>
GridDateTimeColumn</td><td>
DateTime </td><td>
GridCellDateTimeRenderer</td></tr>
<tr>
<td>
GridHyperlinkColumn</td><td>
Hyperlink </td><td>
GridCellHyperLinkRenderer</td></tr>
</table>

### How to enable Tooltips for Cell and Headers?

SfDataGrid provides support to apply Tooltip for Cell and Headers. You can achieve this by using the properties ToolTipTemplate for Cells and HeaderToolTipTemplate for HeaderCells in GridColumn. The following code example illustrates this.


{% highlight xml %}



<syncfusion:GridTextColumn DisplayBinding="{Binding Path=CustomerID}" MappingName="CustomerID">

    <syncfusion:GridTextColumn.ToolTipTemplate>

        <DataTemplate>

            <TextBlock Text="{Binding CustomerID}" />

        </DataTemplate>

    </syncfusion:GridTextColumn.ToolTipTemplate>

    <syncfusion:GridTextColumn.HeaderToolTipTemplate>

        <DataTemplate>

            <TextBlock Text="Hedaer for CutomerID" />

        </DataTemplate>

    </syncfusion:GridTextColumn.HeaderToolTipTemplate>

</syncfusion:GridTextColumn>

{% endhighlight %}



The following screenshot displays the output of Tooltip applied in Header cell.



![](Features_images/Features_img69.png)


_DataGrid with Tooltip applied in Header cell_

The following screenshot displays the output of Tooltip applied in Cells.

![](Features_images/Features_img70.png)



_DataGrid with Tooltip applied in cells_

### How to disable drag and drop between Frozen columns and Non-Frozen columns

You can wire QueryColumnDragging event for DataGrid. Its aruguments have reason property that helps you to perform any actions while draging and dropping. It has From and To property that shows you where the dragging column is present.   

DataGrid has FrozenColumnCount property that gives you number of frozen column that you have set. 

ResolveToStartColumnIndex () is the method that returns the index of first column, since the start column index is not always first column index. When you group or set ShowRowHeader for SfDataGrid or define Master-Details View, column index gets varied. So, the method is used to calculate frozen column index at that time. 


{% highlight C# %}



this.datagrid.QueryColumnDragging += datagrid_QueryColumnDragging;

void datagrid_QueryColumnDragging(object sender, Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs e)

{

    if (e.Reason == QueryColumnDraggingReason.Dropping)

    {

        var frozencolindex = datagrid.FrozenColumnCount + this.datagrid.ResolveToStartColumnIndex();

        if (e.From < frozencolindex && e.To > frozencolindex - 1)

            e.Cancel = true;



        if (e.From > frozencolindex && e.To < frozencolindex || (e.From == frozencolindex && e.To < frozencolindex))

            e.Cancel = true;

    }

}
{% endhighlight %}

### How to bind Column properties from ViewModel

1.Create New Project in Visual Studio.   
2.Create ItemsSouce as mentioned in GettingStarted and populate items.      
3.In your View model, you can have property that you want bind to column.             


{% highlight C# %}



private bool allowFiltering = true;

public bool AllowFiltering 

{ 

    get { return allowFiltering;}

    set { allowFiltering = value; }

}
{% endhighlight %}


4.You can bind collection to ItemsSource property in SfDataGrid. The following code example illustrates how to add it to resource and how to bind it to ItemsSOurce.                    
5.The hightlighted lines creates key for binding collection to DataGrid.       


{% highlight xml %}




<Window x:Class="SimpleApplication.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:local="clr-namespace:SimpleApplication"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow"

        Width="525"

        Height="350">



    <Window.DataContext>

        <local:OrderInfoRepositiory />

    </Window.DataContext>



    <Window.Resources>

        <local:OrderInfoRepositiory x:Key="data" />

    </Window.Resources>

    <Grid>

        <syncfusion:SfDataGrid x:Name="sfdatagrid"

                               AutoGenerateColumns="False"

                               ColumnSizer="Star"

                               ItemsSource="{Binding OrderInfoCollection,

                                                     Source={StaticResource data}}">

            <syncfusion:SfDataGrid.Columns>

                <syncfusion:GridTextColumn AllowFiltering="{Binding RelativeSource={RelativeSource Mode=FindAncestor, AncestorType={x:Type local:MainWindow}}, Path=DataContext.AllowFiltering}" MappingName="OrderID" />

                <syncfusion:GridTextColumn MappingName="CustomerID" />

                <syncfusion:GridTextColumn AllowFiltering="{Binding AllowFiltering, Source={StaticResource data}}" MappingName="CustomerName" />

                <syncfusion:GridTextColumn MappingName="ShipCity" />

                <syncfusion:GridTextColumn MappingName="Country" />

            </syncfusion:SfDataGrid.Columns>

        </syncfusion:SfDataGrid>

    </Grid>

</Window>
{% endhighlight %}


To use RelativeSource way to bind, you can set DataContext. OrderID column AllowFiltering property value is binded using relative source. CustomerName column gets AllowFiltering value from StaticResource.

### How to bind ComboBoxColumn ItemsSource from ViewModel
 
1. Create New Project in VisualStudio.                             
2. Create ItemsSource as explained in GettingStarted.                              
3. Now create ItemsSource for ComboBoxColumn in viewmodel.                                    
4. You can have list of strings as items source to ComboBoxColumn.                                  
5. First highlighted box indicates your ComboBoxColumn ItemsSource declaration. Second highlighted box populates items for list.                     


{% highlight C# %}



public class ViewModel

{

    ObservableCollection<OrderInfo> orderCollection;



    private List<string> comboItems = new List<string>();

    public List<string> ComboItems

    {

        get { return comboItems; }

        set { comboItems = value; }

    }



    public ObservableCollection<OrderInfo> OrderInfoCollection

    {

        get { return orderCollection; }

        set { orderCollection = value; }

    }



    public ViewModel()

    {

        orderCollection = new ObservableCollection<OrderInfo>();

        this.GenerateOrders();



        foreach(OrderInfo o in orderCollection)

        {

            ComboItems.Add(o.CustomerName);

        }

    }

    private void GenerateOrders()

    {

        orderCollection.Add(new OrderInfo(1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));

        orderCollection.Add(new OrderInfo(1002, "Ana Trujilo", "Mexico", "ANATR", "México D.F."));

        orderCollection.Add(new OrderInfo(1003, "Antonio Moreno", "Mexico", "ANTON", "México D.F."));

        orderCollection.Add(new OrderInfo(1004, "Thomas Hardy", "UK", "AROUT", "London"));

        orderCollection.Add(new OrderInfo(1005, "Christina Berglund", "Sweden", "BERGS", "Luleå"));

        orderCollection.Add(new OrderInfo(1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));

        orderCollection.Add(new OrderInfo(1007, "Frédérique Citeaux", "France", "BLONP", "Strasbourg"));

        orderCollection.Add(new OrderInfo(1008, "Martin Sommer", "Spain", "BOLID", "Madrid"));

        orderCollection.Add(new OrderInfo(1009, "Laurence Lebihan", "France", "BONAP", "Marseille"));

        orderCollection.Add(new OrderInfo(1010, "Elizabeth Lincoln", "Canada", "BOTTM", "Tsawassen"));

    }

}

{% endhighlight %}

The following code example shows you how to Bind ComboItems to ComboBoxColumn. 



{% highlight xml %}



<Window x:Class="SimpleApplication.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:local="clr-namespace:SimpleApplication"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow"

        Width="525"

        Height="350">

    <Window.Resources>

        <local:ViewModel x:Key="data" />

    </Window.Resources>

    <syncfusion:SfDataGrid x:Name="sfdatagrid"

                           AllowEditing="True"

                           AutoGenerateColumns="False"

                           ColumnSizer="Star"

                           ItemsSource="{Binding OrderInfoCollection,

                                                 Source={StaticResource data}}">

        <syncfusion:SfDataGrid.Columns>

            <syncfusion:GridTextColumn MappingName="OrderID" />

            <syncfusion:GridComboBoxColumn ItemsSource="{Binding Path=ComboItems, Source={StaticResource data}}" MappingName="CustomerName" />

        </syncfusion:SfDataGrid.Columns>

    </syncfusion:SfDataGrid>

</Window>
{% endhighlight %}


The following screenshot displays the output.



 ![](Features_images/Features_img71.png)



_Binded ComboItems to ComboBoxColumn_

### How to style Hyperlink Column

SfDataGrid has Hyperlink Column that directly loads Hyperlink control as its UIElement. You can directly set style for Hyperlink control with its TargetType as Hyperlink. Then the style is applied to GridHyperlinkColumn. The following code example illustrates how to set style HyperlinkColumn.


{% highlight xml %}



<Window x:Class="SimpleApplication.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:local="clr-namespace:SimpleApplication"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow"

        Width="525"

        Height="350">

    <Window.DataContext>

        <local:ViewModel />

    </Window.DataContext>

    <syncfusion:SfDataGrid x:Name="sfdatagrid"

                           AllowDeleting="True"

                           AllowFiltering="True"

                           AllowResizingColumns="True"

                           AutoGenerateColumns="False"

                           ItemsSource="{Binding OrderInfoCollection}"                           ItemsSourceChanged="SfDataGrid_ItemsSourceChanged_1">

        <syncfusion:SfDataGrid.Resources>

            <Style TargetType="Hyperlink">

                <Setter Property="Foreground" Value="Red" />

            </Style>

        </syncfusion:SfDataGrid.Resources>

        <syncfusion:SfDataGrid.Columns>

            <syncfusion:GridTextColumn MappingName="CustomerName" />

            <syncfusion:GridHyperlinkColumn MappingName="ShipCity" />

        </syncfusion:SfDataGrid.Columns>

    </syncfusion:SfDataGrid>

</Window>
{% endhighlight %}




The following screenshot displays the output.



![](Features_images/Features_img72.png)



_Customized Hyperlink Column_

### How to load Button inside DataTemplate and bind command from ViewModel

SfDataGrid provides support to GridTemplateColumn that loads any control within it using DataTemplate property. You can add button control inside DataTemplate of GridTemplateColumn. The following code example illustrates how to load Button inside DataTemplate and bind command from ViewModel. 


{% highlight C# %}



public class BaseCommand : ICommand

{

    #region Fields



    readonly Action<object> _execute;

    readonly Predicate<object> _canExecute;



    #endregion // Fields



    #region Constructors



    /// <summary>

    /// Creates a new command that always execute.

    /// </summary>

    /// <param name="execute">The execution logic.</param>

    public BaseCommand(Action<object> execute)

        : this(execute, null)

    {

    }



    /// <summary>

    /// Creates a new command.

    /// </summary>

    /// <param name="execute">The execution logic.</param>

    /// <param name="canExecute">The execution status logic.</param>

    public BaseCommand(Action<object> execute, Predicate<object> canExecute)

    {

        if (execute == null)

            throw new ArgumentNullException("execute");



        _execute = execute;

        _canExecute = canExecute;

    }



    #endregion // Constructors



    #region ICommand Members



    public bool CanExecute(object parameter)

    {

        return _canExecute == null ? true : _canExecute(parameter);

    }



    public event EventHandler CanExecuteChanged

    {

        add { CommandManager.RequerySuggested += value; }

        remove { CommandManager.RequerySuggested -= value; }

    }



    public void Execute(object parameter)

    {

        _execute(parameter);

    }



    #endregion // ICommand Members

}
{% endhighlight %}


In ViewModel, you can write command for Button.


{% highlight C# %}



public class ViewModel

{

    static BaseCommand deleteRecord;

    public static BaseCommand DeleteRecord

    {

        get

        {

            if (deleteRecord == null)

                deleteRecord = new BaseCommand(OnDeleteRecordClicked, OnCanDelete);



            return deleteRecord;

        }

    }



    private static bool OnCanDelete(object obj)

    {

        return true;

    }



    private static void OnDeleteRecordClicked(object obj)

    {        

        //TODO ACTION.

    }

}
{% endhighlight %}


Bind command to button inside the DataTemplate.



{% highlight xml %}



<Window x:Class="SimpleApplication.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:local="clr-namespace:SimpleApplication"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow"

        Width="525"

        Height="350">



    <Window.DataContext>

        <local:ViewModel />

    </Window.DataContext>



    <Window.Resources>

        <local:ViewModel x:Key="data" />

    </Window.Resources>



    <syncfusion:SfDataGrid x:Name="sfdatagrid"

                           AllowDeleting="True"

                           AllowFiltering="True"

                           AllowResizingColumns="True"

                           AutoGenerateColumns="False"

                           ItemsSource="{Binding OrderInfoCollection}"

                           ItemsSourceChanged="SfDataGrid_ItemsSourceChanged_1">

        <syncfusion:SfDataGrid.Columns>

            <syncfusion:GridTextColumn MappingName="CustomerName" />



            <syncfusion:GridTemplateColumn MappingName="Delete">

                <syncfusion:GridTemplateColumn.CellTemplate>

                    <DataTemplate>

                        <Button Command="{Binding DeleteRecord,

                                                  Source={StaticResource data}}"

                                CommandParameter="{Binding}"

                                Content="Delete" />

                    </DataTemplate>

                </syncfusion:GridTemplateColumn.CellTemplate>

            </syncfusion:GridTemplateColumn>

        </syncfusion:SfDataGrid.Columns>

    </syncfusion:SfDataGrid>

</Window>
{% endhighlight %}


The following screenshot displays the output of the above code.



![](Features_images/Features_img73.png)



_Loaded Button inside DataTemplate and binded command from ViewModel_

### Difference between Displaybinding , ValueBinding and MappingName properties

#### DisplayBinding

Denotes the binding to DataModel while loading (In Non-Edit mode).

#### ValueBinding

Denotes the binding to DataModel for Edit element.

#### MappingName

MappingName property denotes the property that present in underlying DataModel that needs to bound to the Column. When seting MappingName, then DisplayBinding and ValueBinding will be created to the underlying DataModel based on MappingName. 

By default, data manipulation operations like Sorting, Grouping, Filtering and etc will be based MappingName and the values will be reflected using reflection from DataModel. Setting UseBindingValue property to true, will enable the advanced features like sorting, grouping, filtering and etc will reflects the values based in ValueBinding which enables you to bind more complex binding paths. 

N> Set UseBindingValue only when you are binding more complex property paths or when standard reflection can’t reflect the data from Data model.

### Build a DataGrid with Multiple Data Sources

DataGrid does not support binding to more than one Data Source out of the box. By utilizing unbound columns in the DataGrid, you can incorporate items from multiple Data Sources in the same DataGrid.  This is achieved by handling the QueryUnboundColumnValue event.

Consider a real use case scenario, where you have two Data Sources. One Data Source contains a list of employees working in a sales department, and the other contains a list of products sold on that day. Both Data Sources contain a unique property that is common, EmployeeID in this case. Now, both Data Sources are used to construct the Grid. As explained earlier, a QueryUnboundColumnValue event is raised when the UnboundColumn is initialized.

The following code example shows the process of building a DataGrid with multiple Data Sources in action.



{% highlight xml %}





<syncfusion:SfDataGrid x:Name="syncgrid"

ItemsSource="{Binding OrderInfoCollection}">

<syncfusion:SfDataGrid.Columns>

    <syncfusion:GridTextColumn MappingName="OrderID" />

    <syncfusion:GridUnBoundColumn MappingName="EmployeeName"/>

    <syncfusion:GridTextColumn MappingName="ShipCountry"/>

    <syncfusion:GridTextColumn MappingName="ShipCity"/>

</syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}




Now, you can handle the QueryUnboundColumnValue event to construct its value based on the other Data Source as shown in the following code example.


{% highlight C# %}





EmployeeDetails employeeDetails = new EmployeeDetails();

this.syncgrid.QueryUnboundColumnValue += syncgrid_QueryUnboundColumnValue;



void syncgrid_QueryUnboundColumnValue(object sender, GridUnboundColumnEventsArgs e)

{

    var record = e.Record as ProductInfo;

    var value = employeeDetails.FirstOrDefault

    (p => record != null && p.EmployeeId == record.EmployeeId);

    // Set the value for the column from another data source here.

    if (e.Column.MappingName == "EmployeeName")

    e.Value = value.EmployeeName;

}
{% endhighlight %}




The source results in the following output.



![](Features_images/Features_img74.png)



_Builded DataGrid with Multiple Data Sources_

### How to bind png image to Image Column

SfDataGrid has GridImageColumn. You can directly bind BitmapImages, since GridImageColumn loads Image as its UIElement. However, when you have path or only the name of the image then you cannot bind that image directly to the GridImageColumn. In such cases, you can use converter in ValueBinding. The following code example illustrates how to bind png image to Image Column. 


{% highlight C# %}



class StringToImageConverter : IValueConverter

{

    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

    {

        string imagename = value as string;

        return new BitmapImage(new Uri(string.Format(@"..\..\Images\{0}", imagename),UriKind.Relative));

    }



    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

    {

        throw new NotImplementedException();

    }

}
{% endhighlight %}




You can bind converter to GridImageColumn.



{% highlight xml %}



<syncfusion:GridImageColumn HeaderText="Movie"

                            MappingName="ImageLink"

                            ValueBinding="{Binding Path=ImageLink,

                                                    Converter={StaticResource stringToImageConverter}}" />

{% endhighlight %}

### Define Hyperlink Column that redirects to an URI whose values are not bound to a Column

When URI or URL is very long, and you can find it hard to bind the URL to the GridHyperlinkColumn, or you may want to hide the RequestURI from the View. In both cases, you can implement any of the following two approaches to define the GridHyperlinkColumn. 

#### Method 1

DisplayBinding and ValueBinding in GridColumns of SfDataGrid are used in this case. You can set the DisplayBinding to the value you want to display in view, and bind the ValueBinding to the URI where you want the control to navigate.

The following code example illustrates this.



{% highlight xml %}





<syncfusion:GridHyperlinkColumn DisplayBinding="{Binding Path=ProductName}"

                                HeaderText="Official Product Link"

                                MappingName="ProductName"

                                ValueBinding="{Binding Path=ProductURI}" />


{% endhighlight %}


The following screenshot displays the output.



![](Features_images/Features_img75.png)



_Hyperlink Column redirected to an URI whose values are not bound to a Column using DisplayBinding and ValueBinding_

#### Method 2

Hyperlink Column provides the CellRequestNavigate event that is raised whenever you try to navigate using the Hyperlink control in GridHyperlinkColumn. This event is used to set the sender’s (Hyperlink Button) NavigateURI dynamically at Execute time.

The following code example illustrates how to handle the CellRequestNavigate event and URI dynamically.


{% highlight C# %}



void sfDataGrid_CurrentCellRequestNavigate(object sender, CurrentCellRequestNavigateEventArgs args)

{

    var hyperlinkControl=(sender as Hyperlink);

    var URI = string.Format("http://www." + args.NavigateText + ".com");

    hyperlinkControl.NavigateUri = new Uri(URI);

    args.Handled = true;

}
{% endhighlight %}




The following screenshot illustrates the output.



![](Features_images/Features_img76.png)



_Hyperlink Column redirected to an URI whose values are not bound to a Column using CellRequestNavigate event_

### How to create custom column?

#### CustomColumn support

SfDataGrid allows you to create your own column other than SfDataGrid predefined [column collection](http://help.syncfusion.com/ug/wpf/default.htm). You can decide column’s key board interaction, the events you want to hook and validation from renderer creation. This section explains you on how to create custom column. Custom column can be created by overriding predefined renderers with [renderer replacement](http://help.syncfusion.com/ug/wpf/default.htm) or can be adding new custom renderer to renderer collection. There are two steps to create custom column.

* Creating custom Renderer for column
* Creating custom column

#### Creating custom Renderer for column

You can create custom renderer by deriving from GridVirtualizingCellRenderer<D, E>. It contains generic parameters Where ‘D’ denotes the type display control and ‘E’ denotes the type of edit control. You can load your custom control as display or edit control or you can also load standard controls (TextBlock, Text Box, Combo Box…) and you can customize it in your way. You can also override the existing renderers and you can create customized one. There are some list of existing [renderers](http://help.syncfusion.com/ug/wpf/default.htm) available in SfDataGrid.

The following code example illustrates on how to create custom renderer to load DatePicker as Edit element and TextBlock as display element. 


{% highlight C# %}



/// <summary>

/// CustomRenderer Creation

/// </summary>

/// <param name="TextBlock">Display Control</param>

/// <param name="DatePicker">Edit Control</param>

class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

// TextBlock has been set as Display control.

// DatePicker has been set as Edit control.

}

{% endhighlight %}

The following table lists the virtual methods and properties available in GridVirtualizingCellRenderer that helps you to create your custom renderer. 

_List of properties_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
IsEditable</td><td>
Bool</td><td>
The property that specify, the column can be editable. If you set false the column cannot edit.E.g.: Hyperlink, Image and Checkbox columns are not editable.  </td><td>
True</td></tr>
<tr>
<td>
CurrentCellIndex</td><td>
RowColumnIndex</td><td>
The property that returns row and column index of current cell</td><td>
Null</td></tr>
<tr>
<td>
CurrentCellElement</td><td>
FrameworkElement</td><td>
Returns the GridCell which hold the Edit/Display element of the CurrentCell. </td><td>
Null</td></tr>
<tr>
<td>
CurrentCellRendererElement</td><td>
FrameworkElement</td><td>
Return the Display/Edit element of the CurrentCell Renderer. </td><td>
Null</td></tr>
<tr>
<td>
IsInEditing</td><td>
bool</td><td>
The property that gets or sets whether the current cell is edit mode or not. If you set false when you edit, Edit element will not unload.</td><td>
False</td></tr>
<tr>
<td>
HasCurrentCellState</td><td>
bool</td><td>
Gets that cell state for the current cell has been set.</td><td>
False</td></tr>
<tr>
<td>
SupportsRenderOptimization</td><td>
bool</td><td>
The property that gets or sets that display and edit can be different controls. </td><td>
True</td></tr>
</table>
_Methods to override_

<table>
<tr>
<td>
Method</td><td>
Description</td></tr>
<tr>
<td>
protected virtual D OnCreateDisplayUIElement()</td><td>
Create the Element of type D specified with the GridVirtualizingCellRenderer. Which creates the default display element for renderer and returns.</td></tr>
<tr>
<td>
protected virtual E OnCreateEditUIElement()</td><td>
Creates a new Edit UIElement of type E specified with the GridVirtualizingCellRenderer type parameter. Which creates the default edit element for renderer and returns</td></tr>
<tr>
<td>
public abstract void OnInitializeDisplayElement(RowColumnIndex rowColumnIndex, D uiElement, GridColumn column, object dataContext);</td><td>
Creates binding between GridColumn properties, Display element properties and also initialize default settings for Display element. You can do, your own binding settings with skipping base.OnInitializeDisplayElement being called.</td></tr>
<tr>
<td>
public abstract void OnInitializeEditElement(RowColumnIndex rowColumnIndex, E uiElement, GridColumn column, object dataContext);</td><td>
Creates binding between GridColumn properties, Edit element properties and also initialize default settings for Edit element. You can do, your own binding settings with skipping base. OnInitializeEditElement being called.</td></tr>
<tr>
<td>
public abstract void OnUpdateDisplayBinding(RowColumnIndex cellRowcolumnIndex, D uiElement, GridColumn column, object dataContext);</td><td>
Updates the binding for display element when scrolling and Data Management operations like grouping, Sorting, Filtering. This method will internally call OnInitializeDisplayElement.</td></tr>
<tr>
<td>
public abstract void OnUpdateEditBinding(RowColumnIndex cellRowcolumnIndex, E element, GridColumn column, object dataContext);</td><td>
Updates only DataContext for Edit element. Which calls OnInitializeEditElement. For SupportRenderOptimization was set to false.</td></tr>
<tr>
<td>
protected virtual void OnEditElementLoaded(object sender, RoutedEventArgs e)</td><td>
When edit element was ready for interaction OnEditElementLoaded method will be called. You can set focus for edit element (sender) and can give selection behavior for the text in edit element. </td></tr>
<tr>
<td>
protected virtual void OnEnteredEditMode(FrameworkElement currentRendererElement)</td><td>
When you start edit mode. You can update the current cell state of editing with IsInEditing is update to true. If you set false, then the RowHeaderState changes, Cell or Row Validation, Setting Edit item will not happen.</td></tr>
<tr>
<td>
protected virtual void OnEditingComplete(FrameworkElement currentRendererElement)</td><td>
When you complete editing with the cell (When do, enter/Tab/Right/Left/Home/Page Up/page Down/Up/Down key navigation) you will get an edit control with edited value.</td></tr>
<tr>
<td>
protected virtual bool ShouldGridTryToHandleKeyDown(KeyEventArgs e)</td><td>
Key Interaction on column will be done in this method. You can decide that the selected cell can allow to navigate with the pressed key. If it return false, pressed key must be handled by GridCell else it leaves to handle by SfDataGrid.</td></tr>
<tr>
<td>
public virtual object GetControlValue()</td><td>
Returns the display or edit control value for validation purpose.</td></tr>
<tr>
<td>
public virtual void SetControlValue(object value)</td><td>
The method that set value to display or edit controls.</td></tr>
<tr>
<td>
public virtual void UpdateSource(FrameworkElement cellElement)</td><td>
Method that updates the source by BindingExpression </td></tr>
<tr>
<td>
public virtual bool CanUpdateBinding(GridColumn column)</td><td>
Decides Whether to refresh the bindings of Element whenever the DataContext gets changed. By default it return false. If you need to use different binding in one column then return as false</td></tr>
<tr>
<td>
public virtual bool CanValidate()</td><td>
Decides whether to do cell validation for GridCell. By default it returns true. (where you want the cell should always focused if it has invalid data) </td></tr>
</table>


You can define the default behavior by the properties with constructor of derived class.


{% highlight C# %}



//Renderer Creation.

class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    //Constructor of class

    public DatePickerRenderer()

    {



    }

}

{% endhighlight %}

The following code example illustrates you on how to create display and edit element in custom renderer.


{% highlight C# %}



class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    /// <summary>

    /// Create new display element.

    /// </summary>

    /// <returns></returns>

    protected override TextBlock OnCreateDisplayUIElement()

    {

        return new TextBlock();

    }

    /// <summary>

    /// Create new edit element.

    /// </summary>

    /// <returns></returns>

    protected override DatePicker OnCreateEditUIElement()

    {

        return new DatePicker();

    }    

}

{% endhighlight %}

The following code example explains you how to initialize properties binding for display element and update bindings.

{% highlight C# %}






class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    /// <summary>

    /// Initialize display element with binding.

    /// </summary>

    /// <param name="rowColumnIndex"></param>

    /// <param name="uiElement"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnInitializeDisplayElement(RowColumnIndex rowColumnIndex, TextBlock uiElement, GridColumn column,

        object dataContext)

    {

        base.OnInitializeDisplayElement(rowColumnIndex, uiElement, column, dataContext);

        SetDisplayBinding(uiElement, column, dataContext);

    }

    /// <summary>

    /// Update display elements binding while scrolling.

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="uiElement"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnUpdateDisplayBinding(RowColumnIndex cellRowcolumnIndex, TextBlock uiElement, GridColumn column, object dataContext)

    {

        base.OnUpdateDisplayBinding(cellRowcolumnIndex, uiElement, column, dataContext);

        SetDisplayBinding(uiElement, column, dataContext);

    }



    /// <summary>

    /// custom binding for display element.

    /// </summary>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    private static void SetDisplayBinding(TextBlock element, GridColumn column, object dataContext)

    {

        var customColumn = (DatePickerColumn)column;                 

        var binding = new Binding

        {

            Path = new PropertyPath(customColumn.DateMapping),

            Mode = BindingMode.TwoWay,

            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,

            Converter = column.DisplayBinding.Converter, //Bind Custom converter for display.

        };



        element.SetBinding(TextBlock.TextProperty, binding);          

    }

}
{% endhighlight %}


The following code example explains you on how to initialize properties binding for edit element and update bindings.


{% highlight C# %}





class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    /// <summary>

    /// Initialize edit element with binding

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnInitializeEditElement(RowColumnIndex cellRowcolumnIndex, DatePicker element, GridColumn column,

        object dataContext)

    {

        base.OnInitializeEditElement(cellRowcolumnIndex, element, column, dataContext);

        SetEditBinding(element, column, dataContext);

    }

    /// <summary>

    /// Update binding for edit element while scrolling.

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnUpdateEditBinding(RowColumnIndex cellRowcolumnIndex, DatePicker element, GridColumn column, object dataContext)

    {

        base.OnUpdateEditBinding(cellRowcolumnIndex, element, column, dataContext);

        SetEditBinding(element, column, dataContext);

    }

    /// <summary>

    /// Custom binding for edit element.

    /// </summary>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    private static void SetEditBinding(DatePicker element, GridColumn column, object dataContext)

    {

        var customColumn = (DatePickerColumn)column;

        var binding = new Binding

        {

            Source = dataContext,

            Path = new PropertyPath(customColumn.DateMapping),

            Mode = BindingMode.TwoWay,

            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,

        };



        element.SetBinding(DatePicker.TextProperty, binding);

    }

}

{% endhighlight %}

The following code example illustrates that how can you make use of OnEditElementLoaded method.


{% highlight C# %}



class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    /// <summary>

    /// When edit element ready for interaction this method will be called.

    /// </summary>

    /// <param name="sender"></param>

    /// <param name="e"></param>

    protected override void OnEditElementLoaded(object sender, RoutedEventArgs e)

    {

        var datePicker = (sender as DatePicker);

        datePicker.Focus();

        DatePickerTextBox datePickerTextBox = (DatePickerTextBox)GridUtil.FindDescendantChildByType(datePicker, typeof(DatePickerTextBox));

        // GridUtil is the helper class that has functions with Visual Tree

        if ((this.DataGrid.EditorSelectionBehavior == EditorSelectionBehavior.SelectAll || this.DataGrid.IsAddNewIndex(this.CurrentCellIndex.RowIndex)) && PreviewInputText == null)

        {

            datePickerTextBox.SelectAll();               

        }

        else

        {

            datePickerTextBox.Select(datePickerTextBox.SelectedText.Length, 0);

        }

        PreviewInputText = null;

    }

}
{% endhighlight %}


The following code example illustrates you on how the key board interaction can be customized with your custom renderer.


{% highlight C# %}





class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    /// <summary>

    /// Let Renderer decide whether the parent grid should be allowed to handle keys and prevent

    /// the key event from being handled by the visual UIElement for this renderer. If this method

    /// returns true the parent grid will handle arrow keys and set the Handled flag in the event

    /// data. Keys that the grid does not handle will be ignored and be routed to the UIElement

    /// for this renderer.

    /// </summary>

    /// <param name="e">A <see cref="KeyEventArgs" /> object.</param>

    /// <returns>

    /// True if the parent grid should be allowed to handle keys; false otherwise.

    /// </returns>

    protected override bool ShouldGridTryToHandleKeyDown(System.Windows.Input.KeyEventArgs e)

    {

        if (!HasCurrentCellState || !IsInEditing)

            return true;

        DatePickerTextBox datePickerTextBox = (DatePickerTextBox)GridUtil.FindDescendantChildByType(CurrentCellRendererElement as DatePicker, typeof(DatePickerTextBox));

        switch (e.Key)

        {

            case Key.End:

            case Key.Home:

            case Key.Enter:

            case Key.Escape:

                return !((DatePicker)CurrentCellRendererElement).IsDropDownOpen;

            case Key.Down:

            case Key.Up:

            case Key.Left:

            case Key.Right:

                return !((DatePicker)CurrentCellRendererElement).IsDropDownOpen;                               

        }

        return base.ShouldGridTryToHandleKeyDown(e);

    }

}
{% endhighlight %}


The following code examples illustrates the custom renderer with converter.


{% highlight C# %}





//Custom Converter Here

class ConvertToDateTimeClass

{

    public string ConvertToDateTime(object value)

    {

        DateTime date = Convert.ToDateTime(value);

        return date.Day+"/"+date.Month+"/"+date.Year;

    }

}

class CustomConverter : IValueConverter

{

    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

    {

        if(string.IsNullOrEmpty(value.ToString()))

            return null;

        return new ConvertToDateTimeClass().ConvertToDateTime(value);

    }



    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

    {

        return new ConvertToDateTimeClass().ConvertToDateTime(value);

    }

}



//Renderer Creation.

class DatePickerRenderer : GridVirtualizingCellRenderer<TextBlock,DatePicker>

{

    public DatePickerRenderer()

    {



    }

    /// <summary>

    /// Create new display element.

    /// </summary>

    /// <returns></returns>

    protected override TextBlock OnCreateDisplayUIElement()

    {

        return new TextBlock();

    }

    /// <summary>

    /// Create new edit element.

    /// </summary>

    /// <returns></returns>

    protected override DatePicker OnCreateEditUIElement()

    {

        return new DatePicker();

    }



    #region Display/Edit Value Overrides

    /// <summary>

    /// Gets the control value.

    /// </summary>

    /// <returns></returns>

    public override object GetControlValue()

    {

        if (!HasCurrentCellState)

            return base.GetControlValue();

        return CurrentCellRendererElement.GetValue(IsInEditing ? DatePicker.TextProperty : TextBlock.TextProperty);

    }



    /// <summary>

    /// Sets the control value.

    /// </summary>

    /// <param name="value">The value.</param>

    public override void SetControlValue(object value)

    {

        if (!HasCurrentCellState)

            return;

        if (IsInEditing)

            ((TextBox)CurrentCellRendererElement).Text = value.ToString();

        else

            throw new Exception("Value cannot be Set for Unloaded Editor");

    }

    #endregion



    /// <summary>

    /// Initialize display element with binding.

    /// </summary>

    /// <param name="rowColumnIndex"></param>

    /// <param name="uiElement"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnInitializeDisplayElement(RowColumnIndex rowColumnIndex, TextBlock uiElement, GridColumn column,

        object dataContext)

    {

        base.OnInitializeDisplayElement(rowColumnIndex, uiElement, column, dataContext);

        SetDisplayBinding(uiElement, column, dataContext);

    }



    /// <summary>

    /// Update display elements binding while scrolling.

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="uiElement"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnUpdateDisplayBinding(RowColumnIndex cellRowcolumnIndex, TextBlock uiElement, GridColumn column, object dataContext)

    {

        base.OnUpdateDisplayBinding(cellRowcolumnIndex, uiElement, column, dataContext);

        SetDisplayBinding(uiElement, column, dataContext);

    }



    /// <summary>

    /// custom binding for display element.

    /// </summary>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    private static void SetDisplayBinding(TextBlock element, GridColumn column, object dataContext)

    {

        var customColumn = (DatePickerColumn)column;                 

        var binding = new Binding

        {

            Path = new PropertyPath(customColumn.DateMapping),

            Mode = BindingMode.TwoWay,

            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,

            Converter = column.DisplayBinding.Converter, //Bind Custom converter for display.

        };



        element.SetBinding(TextBlock.TextProperty, binding);          

    }



    #region Edit Element

    /// <summary>

    /// Initialize edit element with binding

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnInitializeEditElement(RowColumnIndex cellRowcolumnIndex, DatePicker element, GridColumn column,

        object dataContext)

    {

        base.OnInitializeEditElement(cellRowcolumnIndex, element, column, dataContext);

        SetEditBinding(element, column, dataContext);

    }



    /// <summary>

    /// Update binding for edit element while scrolling.

    /// </summary>

    /// <param name="cellRowcolumnIndex"></param>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    public override void OnUpdateEditBinding(RowColumnIndex cellRowcolumnIndex, DatePicker element, GridColumn column, object dataContext)

    {

        base.OnUpdateEditBinding(cellRowcolumnIndex, element, column, dataContext);

        SetEditBinding(element, column, dataContext);

    }



    /// <summary>

    /// Custom binding for edit element.

    /// </summary>

    /// <param name="element"></param>

    /// <param name="column"></param>

    /// <param name="dataContext"></param>

    private static void SetEditBinding(DatePicker element, GridColumn column, object dataContext)

    {

        var customColumn = (DatePickerColumn)column;

        var binding = new Binding

        {

            Source = dataContext,

            Path = new PropertyPath(customColumn.DateMapping),

            Mode = BindingMode.TwoWay,

            UpdateSourceTrigger = UpdateSourceTrigger.PropertyChanged,

        };



        element.SetBinding(DatePicker.TextProperty, binding);

    }



    /// <summary>

    /// Let Renderer decide whether the parent grid should be allowed to handle keys and prevent

    /// the key event from being handled by the visual UIElement for this renderer. If this method

    /// returns true the parent grid will handle arrow keys and set the Handled flag in the event

    /// data. Keys that the grid does not handle will be ignored and be routed to the UIElement

    /// for this renderer.

    /// </summary>

    /// <param name="e">A <see cref="KeyEventArgs" /> object.</param>

    /// <returns>

    /// True if the parent grid should be allowed to handle keys; false otherwise.

    /// </returns>

    protected override bool ShouldGridTryToHandleKeyDown(System.Windows.Input.KeyEventArgs e)

    {

        if (!HasCurrentCellState || !IsInEditing)

            return true;

        DatePickerTextBox datePickerTextBox = (DatePickerTextBox)GridUtil.FindDescendantChildByType(CurrentCellRendererElement as DatePicker, typeof(DatePickerTextBox));

        switch (e.Key)

        {

            case Key.End:

            case Key.Home:

            case Key.Enter:

            case Key.Escape:

                return !((DatePicker)CurrentCellRendererElement).IsDropDownOpen;

            case Key.Down:

            case Key.Up:

            case Key.Left:

            case Key.Right:

                return !((DatePicker)CurrentCellRendererElement).IsDropDownOpen;                               

        }

        return base.ShouldGridTryToHandleKeyDown(e);

    }



    /// <summary>

    /// When edit element ready for interaction this method will be called.

    /// </summary>

    /// <param name="sender"></param>

    /// <param name="e"></param>

    protected override void OnEditElementLoaded(object sender, RoutedEventArgs e)

    {

        var datePicker = (sender as DatePicker);

        datePicker.Focus();

        DatePickerTextBox datePickerTextBox = (DatePickerTextBox)GridUtil.FindDescendantChildByType(datePicker, typeof(DatePickerTextBox));

        if ((this.DataGrid.EditorSelectionBehavior == EditorSelectionBehavior.SelectAll || this.DataGrid.IsAddNewIndex(this.CurrentCellIndex.RowIndex)) && PreviewInputText == null)

        {

            datePickerTextBox.SelectAll();               

        }

        else

        {

            datePickerTextBox.Select(datePickerTextBox.SelectedText.Length, 0);

        }

        PreviewInputText = null;

    }



    #endregion

}

{% endhighlight %}

Add your custom renderer to DataGrid renderer collection as in the following code example.


{% highlight C# %}





//Add renderer to CellRenderer Collection.

_dataGrid.CellRenderers.Add("DatePickerRenderer", new DatePickerRenderer());
{% endhighlight %}


###  Column Creation

Create a class that derives from GridColumn. Set cell type for a custom column in derived class constructor. 

The following code example explains you on how to create Custom Column.


{% highlight C# %}





//Column Creation

public class DatePickerColumn : GridColumn

{       

    public static readonly DependencyProperty DateMappingProperty = DependencyProperty.Register("DateMapping",

typeof(string), typeof(DatePickerColumn));

    public DatePickerColumn()

    {

        SetCellType("DatePickerRenderer");

    }

    public string DateMapping

    {

        get { return (string)GetValue(DateMappingProperty); }

        set { SetValue(DateMappingProperty, value); }

    }

    protected override Freezable CreateInstanceCore()

    {

        return new DatePickerColumn();

    }

}

{% endhighlight %}

Finally, add your custom column to SfDataGrid with the following code example in XAML.


{% highlight xml %}





//Converter for custom column display binding.

<Grid.Resources>

    <local:CustomConverter x:Key="converter"/>

</Grid.Resources>



<Syncfusion:SfDataGrid.Columns>    

    <demo:DatePickerColumn MappingName="DateOfMonth"    

                           DateMapping="DateOfMonth"   

                           HeaderText="DatePickerColumn"  

                           DisplayBinding="{Binding  DateOfMonth,Converter={StaticResource converter}}"

                           AllowEditing="True"/>

</Syncfusion:SfDataGrid.Columns>

{% endhighlight %}

The following screenshot displays the output.



![](Features_images/Features_img77.png)



_Custom Column in Display Mode_

![](Features_images/Features_img78.png)



_Custom Column in Edit mode_

### How to change FilterIconWidth and SortIconWidth when you calculate column width based on SizeToHeader column sizer

By default, column width is calculated based on the fixed FontSize, FilterIconWidth,and SortIconWidth. When you change FilterIconWidth and Sort icon width, it does not consider the changed width when you calculate column width. Therefore, the column width is not fit based on SizeToHeader column sizer. You can use the following code example to calculate the column width based on the new FilterIconWidth and SortIconWidth values.


{% highlight C# %}



dataGrid.GridColumnSizer.FilterIconWidth = 20;

dataGrid.GridColumnSizer.SortIconWidth = 20;
{% endhighlight %}

### How to customize star width calculation 

When column sizer is Star, the control content occupies total space in the parent, and column’s width is divided equally based on the total space by default. When you want to customize the star width calculation as in grid panel, you can use custom GridColumnSizer.

Consider, the grid has four columns and you can set the width as 1*,2*,3*,1* respectively.

The following code example illustrates how to customize star width calculation.


{% highlight xml %}


 

<syncfusion:SfDataGrid Name="dataGrid" AllowSorting="True"

                                       AutoGenerateColumns="False"

                                       ColumnSizer="Star"

                                       ItemsSource="{Binding OrderList}"

                                       LiveDataUpdateMode="AllowDataShaping">

                    <syncfusion:SfDataGrid.Columns>

                        <syncfusion:GridTextColumn HeaderText="Order ID" MappingName="OrderID" />



                        <syncfusion:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />



                        <syncfusion:GridTextColumn HeaderText="Contact Number" MappingName="ContactNumber" />

                        <syncfusion:GridNumericColumn HeaderText="Quantity"

                                                      MappingName="UnitPrice"

                                                      NumberDecimalDigits="0" />

                    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>

{% endhighlight %}

{% highlight C# %}

 

// Assign custom GridColumnSizer to datagrid GridColumnSizer

dataGrid.GridColumnSizer = new ColumnSizerExt(dataGrid);



public class ColumnSizerExt : GridColumnSizer

        {

            public ColumnSizerExt(SfDataGrid grid)

                : base(grid)

            {

            }

  protected override void SetStarWidth(double remainingColumnWidth, IEnumerable<GridColumn> remainingColumns)

            {

                var starValues=new Dictionary<string,int>();

                starValues.Add("OrderID",1);

                starValues.Add("CustomerID",2);

                starValues.Add("ContactNumber",3);

                starValues.Add("UnitPrice",1);



                var removedColumn = new List<GridColumn>();

                var columns = remainingColumns.ToList();

                var totalRemainingStarValue = remainingColumnWidth;

                double removedWidth = 0;

                bool isremoved;

                while (columns.Count > 0)

                {

                    isremoved = false;

                    removedWidth = 0;

                    var columnsCount = 0;

                    columns.ForEach((col)=>

                    {

                        columnsCount += starValues[col.MappingName];

                    });

                    double starWidth = Math.Floor((totalRemainingStarValue / columnsCount));                   

                    var column = columns.First();



                        starWidth *= starValues[column.MappingName];

                    double computedWidth = SetColumnWidth(column, starWidth);

                    if (starWidth != computedWidth && starWidth > 0)

                    {

                        isremoved = true;

                        columns.Remove(column);

                        foreach (var remColumn in removedColumn)

                        {

                            if (!columns.Contains(remColumn))

                            {

                                removedWidth += remColumn.ActualWidth;

                                columns.Add(remColumn);

                            }

                        }

                        removedColumn.Clear();

                        totalRemainingStarValue += removedWidth;

                    }

                    totalRemainingStarValue = totalRemainingStarValue - computedWidth;

                    if (!isremoved)

                    {

                        columns.Remove(column);

                        if (!removedColumn.Contains(column))

                            removedColumn.Add(column);

                    }

                }

            }

}

{% endhighlight %}



The following screenshot illustrates the output image after applying star column sizer. The column widths are calculated based on 1*, 2*, 3* and 1*.



![](Features_images/Features_img79.png)



_DataGrid with customized star column sizer_

### How to apply column sizer after resizing the columns?

When you resize the particular column, the width is set for that column. After resizing the column, when you apply column sizer, column width is not set based on column sizer. It maintains the previous width only. You can overcome this scenario by resetting the width of the columns before changing the ColumnSizer as in the following code example.


{% highlight C# %}

 

     foreach (var column in dataGrid.Columns)

     {

        if(!double.IsNaN(column.Width))

             column.Width = double.NaN;

     }

     dataGrid.ColumnSizer = GridLengthUnitType.SizeToCells;
{% endhighlight %}

### How to customize column width calculation for particular column?

By default, column width is calculated based on the fixed FontSize, FontFamily and Margin. When any column is customized with different FontSize and FontFamily, it is not considered when you calculate column width. Therefore, the column width is not fit based on the header and cell value even though column sizer is Auto. You can overcome this scenario by overriding GetTextBlock method in GridColumnSizer as illustrated in the following code example.


{% highlight C# %}

 

// Assign custom GridColumnSizer to datagrid GridColumnSizer

grid.GridColumnSizer = new CustomColumnSizer(grid);

public class CustomColumnSizer : GridColumnSizer

{

        public CustomColumnSizer(SfDataGrid sfdataGrid)

            : base(sfdataGrid)

        {

        }



        protected override TextBlock GetTextBlock(GridColumn column, object record)

        {

            if (TextBlock == null)

                TextBlock = new TextBlock();

            if (column.MappingName == "Name")

            {

                TextBlock.FontFamily = new System.Windows.Media.FontFamily("TimesNewRoman");

                TextBlock.Margin = new Thickness(50, 1, 0, 0);

                TextBlock.FontSize = 20;

            }

            else

            {

                TextBlock.FontFamily = FontFamily;

                TextBlock.Margin = Margin;

                TextBlock.FontSize = FontSize;

            }

            return TextBlock;

        }

}
{% endhighlight %}

### How to change column width based on the cell value at run time?

When grid column sizer is SizeToCells, the column width is adjusted with respect to cell content.

But after editing the cell value, column width is not adjusted based on new cell value instead it maintains the previous width only. You can overcome this by refreshing grid column width using the following code example.


{% highlight C# %}

 

this.dataGrid.Loaded += dataGrid_Loaded;

void dataGrid_Loaded(object sender, RoutedEventArgs e)

{

    dataGrid.View.RecordPropertyChanged += View_RecordPropertyChanged;

}



void View_RecordPropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)

{

     var column = dataGrid.Columns.FirstOrDefault(c => c.MappingName == e.PropertyName);

     dataGrid.GridColumnSizer.ResetAutoCalculation(column);

     dataGrid.GridColumnSizer.Refresh();

}
{% endhighlight %}