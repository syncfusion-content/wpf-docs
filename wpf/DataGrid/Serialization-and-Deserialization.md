---
layout: post
title: Serialization in WPF DataGrid Control | Syncfusion
description: Learn here all about Serialization and Deserialization support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Serialization and Deserialization in WPF DataGrid

SfDataGrid allows you to serialize and deserialize the SfDataGrid settings using [DataContractSerializer](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.serialization.datacontractserializer).
 
## Serialization 
You can serialize the SfDataGrid by using [SfDataGrid.Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Serialize_System_IO_Stream_) method which exports the current DataGrid control properties to an XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{           
    dataGrid.Serialize(file);
}    
{% endhighlight %}
{% endtabs %}


### Serialize as Stream

You can store the SfDataGrid settings as [Stream](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream) using [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Serialize_System_IO_Stream_) method by passing the stream.

{% tabs %}
{% highlight c# %}
FileStream stream = new FileStream("DataGrid", FileMode.Create);
this.dataGrid.Serialize(stream);
{% endhighlight %}
{% endtabs %}


## Serialization options 

SfDataGrid serialization  operation can be customized by passing [SerializationOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html) instance as an argument to [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Serialize_System_IO_Stream_Syncfusion_UI_Xaml_Grid_SerializationOptions_) method.


### Serialize sorting

By default, SfDataGrid allows you to serialize the sorting operation. You can disable the sorting serialization by setting the [SerializationOptions.SerializeSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeSorting) to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeSorting = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize grouping

By default, SfDataGrid allows you to serialize the grouping operation. You can disable the grouping  serialization by setting the [SerializationOptions.SerializeGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeGrouping) to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeGrouping = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize filtering

By default, SfDataGrid allows you to serialize the filtering operation. You can disable the filtering  serialization by setting the [SerializationOptions.SerializeFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeFiltering) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeFiltering = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize columns

By default, SfDataGrid allows you to serialize the columns manipulation operation. You can disable the columns serialization by setting the [SerializationOptions.SerializeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeColumns) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeColumns = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize summaries
 
By default, SfDataGrid allows you to serialize the caption summary, group summary and table summary settings in SfDataGrid. 

You can disable the summaries serialization by setting [SerializationOptions.SerializeCaptionSummary](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeCaptionSummary) , [SerializationOptions.SerializeGroupSummaries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeGroupSummaries) , [SerializationOptions.SerializeTableSummaries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeTableSummaries) properties to `false`

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeCaptionSummary = false;
    options.SerializeGroupSummaries = false;
    options.SerializeTableSummaries = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize stacked headers

By default, SfDataGrid allows you to serialize the stack headers operation. You can disable the stack headers serialization by setting the [SerializationOptions.SerializeStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeStackedHeaders) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeStackHeaders = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}


### Serialize Details View

By default, SfDataGrid allows you to serialize the DetailsViewDefinition. You can disable the DetailsViewDefinition serialization by setting the [SerializationOptions.SerializeDetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeDetailsViewDefinition) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeDetailsViewDefinition = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize unbound rows

By default, SfDataGrid allows you to serialize the unbound rows settings. You can disable the unbound rows serialization by setting the [SerializationOptions.SerializeUnBoundRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationOptions.html#Syncfusion_UI_Xaml_Grid_SerializationOptions_SerializeUnBoundRows) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{
    SerializationOptions options = new SerializationOptions();
    options.SerializeUnBoundRows = false;
    dataGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

## Deserialization

You can deserialize the SfDataGrid setting by using [SfDataGrid.Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Deserialize_System_IO_Stream_) method which reconstructs the SfDataGrid based on the setting in the stored XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    dataGrid.Deserialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Deserialize from Stream

You can deserialize the SfDataGrid settings from [Stream](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream) using [Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Deserialize_System_IO_Stream_) method.

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream("DataGrid", FileMode.Open);
this.dataGrid.Deserialize(fileStream);
{% endhighlight %}
{% endtabs %}

## Deserialization options
 
Deserialization operation can be customized by passing [DeserializationOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html) instance as an argument to [Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Deserialize_System_IO_Stream_Syncfusion_UI_Xaml_Grid_DeserializationOptions_) method.

### Deserialize sorting

By default, SfDataGrid allows you to deserialize the sorting operation. You can disable the sorting  deserialization by setting the [DeserializationOptions.DeserializeSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeSorting) to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeSorting = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize grouping

By default, SfDataGrid allows you to deserialize the grouping operation. You can disable the grouping deserialization by setting the [DeserializationOptions.DeserializeGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeGrouping) to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeGrouping = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize filtering

By default, SfDataGrid allows you to deserialize the filtering. you can disable the filtering deserialization by setting [DeserializationOptions.DeserializeFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeFiltering) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeFiltering = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize columns

By default, SfDataGrid allows you to deserialize the columns manipulation operations. You can disable the columns deserialization by setting the [DeserializationOptions.DeserializeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeColumns) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeColumns = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize summaries
 
By default, SfDataGrid allows you to deserialize the group summary, caption summary and table summary settings. 

You can disable the summaries deserialization by setting [DeserializationOptions.DeserializeCaptionSummary](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeCaptionSummary) , [DeserializationOptions.DeserializeGroupSummaries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeGroupSummaries) , [DeserializationOptions.DeserializeTableSummaries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeTableSummaries) properties to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeCaptionSummary = false ;
    options.DeserializeGroupSummaries = false ;
    options.DeserializeTableSummaries = false ;
    dataGrid.Deserialize(file, options);
}    
{% endhighlight %}
{% endtabs %}

### Deserialize stacked headers

By default, SfDataGrid allows you to deserialize the stack headers. You can disable the stacked headers deserialization by setting the [DeserializationOptions.DeserializeStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeStackedHeaders) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeStackedHeaders = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize Details View

By default, SfDataGrid allows you to deserialize the DetailsViewDefinition. You can disable the DetailsViewDefinition deserialization by setting the [DeserializationOptions.DeserializeDetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeDetailsViewDefinition) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeDetailsViewDefinition = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize unbound rows

By default, SfDataGrid allows you to deserialize the unbound rows settings. You can disable the unbound rows deserialization by setting the [DeserializationOptions.DeserializeUnBoundRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DeserializationOptions.html#Syncfusion_UI_Xaml_Grid_DeserializationOptions_DeserializeUnBoundRows) to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    DeserializationOptions options = new DeserializationOptions();
    options.DeserializeUnBoundRows = false ;
    dataGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

## Customizing Serialization and Deserialization Operations

SfDataGrid allows you to customize the serialization and deserialization operations by deriving [SerializationController](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html) class and override the necessary virtual methods.

### Serialize custom column 

By default, the unknown(custom) column types are serialized as `GridTextColumn` type. If you want to serialize the custom column, you have to add custom column type into predefined types. 

In the below code snippet, DatePickerColumn is created . For more information about creating custom column refer [here](http://help.syncfusion.com/wpf/sfdatagrid/column-types#custom-column-support).

{% tabs %}
{% highlight c# %}
public class DatePickerColumn : GridColumn
{        
    public DatePickerColumn()
    {
        SetCellType("DatePicker");
    }

    public static readonly DependencyProperty DateMappingNameProperty = DependencyProperty.Register("DateMappingName",
typeof(string), typeof(DatePickerColumn));

    public string DateMappingName
    {
        get { return (string)GetValue(DateMappingNameProperty); }
        set { SetValue(DateMappingNameProperty, value); }
    }

    protected override Freezable CreateInstanceCore()
    {
        return new DatePickerColumn();
    }

    protected override void SetDisplayBindingConverter()
    {
        (this.DisplayBinding as Binding).Converter = new CustomConverter();      
    }
}
{% endhighlight %}
{% endtabs %}

In the below code snippet, the DatePickerColumn is defined in SfDataGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                        AutoGenerateColumns="False"
                        ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.Columns>
        <local:DatePickerColumn HeaderText="OrderDate" MappingName="OrderDate" />
    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


To serialize the above DatePickerColumn, follow the below steps.
 
1. Create a class derived from [SerializableGridColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializableGridColumn.html) and define the custom column properties in `SerializableCustomGridColumn` class.

{% tabs %}
{% highlight c# %}
[DataContract(Name="SerializableCustomGridColumn")]

public class SerializableCustomGridColumn : SerializableGridColumn
{
    [DataMember]

    public string DateMappingName { get; set; }
}
{% endhighlight %}
{% endtabs %}

2.Create a new class named as SerializationControllerExt by overriding [SerializationController](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html) class.

{% tabs %}
{% highlight c# %}
dataGrid.SerializationController = new SerializationControllerExt(dataGrid);

public class SerializationControllerExt : SerializationController
{
 
    public SerializationControllerExt(SfDataGrid dataGrid)
        : base(dataGrid)
    {
    }
}
{% endhighlight %}
{% endtabs %}

3.You can get the custom column property settings for serialization by overriding the [GetSerializableGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_GetSerializableDataGrid) virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : SerializationController
{

    public SerializationControllerExt(SfDataGrid dataGrid)
        : base(dataGrid)
    {
    }

    protected override SerializableGridColumn GetSerializableGridColumn(GridColumn column)
    {

        if (column.MappingName == "OrderDate")
        {
            return new SerializableCustomGridColumn();
        }
        return base.GetSerializableGridColumn(column);
    }
}
{% endhighlight %}
{% endtabs %}

4.Store the custom column property settings during serialization by overriding the [StoreGridColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_StoreGridColumnProperties_Syncfusion_UI_Xaml_Grid_GridColumn_Syncfusion_UI_Xaml_Grid_SerializableGridColumn_) virtual method.
 
{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : SerializationController
{

    public SerializationControllerExt(SfDataGrid dataGrid)
            : base(dataGrid)
    {
    }

    protected override void StoreGridColumnProperties(GridColumn column, SerializableGridColumn serializableColumn)
    {
        base.StoreGridColumnProperties(column, serializableColumn);

        if (column is DatePickerColumn)
            (serializableColumn as SerializableCustomGridColumn).DateMappingName = (column as DatePickerColumn).DateMappingName;
    }
}
{% endhighlight %}
{% endtabs %}

5.Add the custom column in to known column types by overriding the [KnownTypes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_KnownTypes) virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : SerializationController
{
    public SerializationControllerExt(SfDataGrid dataGrid)
            : base(dataGrid)
    {
    }

    public override Type[] KnownTypes()
    {
        var types = base.KnownTypes();
        var list = types.Cast<Type>().ToList();
        list.Add(typeof(SerializableCustomGridColumn));
        return list.ToArray();
    }
}
{% endhighlight %}
{% endtabs %}

6.During deserialization, you can get the custom column settings from [SerializableGridColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializableGridColumn.html) by overriding [GetGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_GetGridColumn_Syncfusion_UI_Xaml_Grid_SerializableGridColumn_) virtual method.
 
{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : SerializationController
{
    public SerializationControllerExt(SfDataGrid dataGrid)
            : base(dataGrid)
    {
    }

    protected override GridColumn GetGridColumn(SerializableGridColumn serializableColumn)
    {

        if (serializableColumn is SerializableCustomGridColumn)
            return new DatePickerColumn();
            return base.GetGridColumn(serializableColumn);
    }
}
{% endhighlight %}
{% endtabs %}

7.Now restore the custom column settings from SerializableGridColumn by overriding the [RestoreColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_RestoreColumnProperties_Syncfusion_UI_Xaml_Grid_SerializableGridColumn_Syncfusion_UI_Xaml_Grid_GridColumn_) virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : SerializationController
{

    public SerializationControllerExt(SfDataGrid dataGrid)
        : base(dataGrid)
    {
    }

    protected override void RestoreColumnProperties(SerializableGridColumn serializableColumn, GridColumn column)
    {
        base.RestoreColumnProperties(serializableColumn, column);
        
        if (column is DatePickerColumn)
            (column as DatePickerColumn).DateMappingName = (serializableColumn as SerializableCustomGridColumn).DateMappingName;
    }

}
{% endhighlight %}
{% endtabs %}

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Serialization_Deserialization-1590961253.zip).

### Serializing template column content

By default, you cannot serialize the template content in SfDataGrid. This is the default behavior during  Serialization and Deserialization operation.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <DataTemplate x:Key="cellTemplate">
        <Button Content="{Binding Value}" />
    </DataTemplate>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="False"
                       ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTemplateColumn CellTemplate="{StaticResource cellTemplate}"
                                       HeaderText="Order ID"
                                       MappingName="OrderID"
                                       SetCellBoundValue="True" />        
    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

If you want to serialize and deserialize the template content, you have to reconstruct the same template during deserialization in [RestoreColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SerializationController.html#Syncfusion_UI_Xaml_Grid_SerializationController_RestoreColumnProperties_Syncfusion_UI_Xaml_Grid_SerializableGridColumn_Syncfusion_UI_Xaml_Grid_GridColumn_) method.

{% tabs %}
{% highlight c# %}

this.dataGrid.SerializationController = new SerializationControllerExt(this.dataGrid);

public class SerializationControllerExt : SerializationController
{

    public SerializationControllerExt(SfDataGrid grid)
        : base(grid)
    {

    }
        
    protected override void RestoreColumnProperties(SerializableGridColumn serializableColumn, GridColumn column)
    {
        base.RestoreColumnProperties(serializableColumn, column);

        if (column is GridTemplateColumn)
        {

            if (column.MappingName == "OrderID")
            {
                column.CellTemplate = App.Current.Resources["cellTemplate"] as DataTemplate;
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Serialization_Deserialization-1041317411.zip).
