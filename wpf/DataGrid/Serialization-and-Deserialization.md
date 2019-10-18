---
layout: post
title: Serialization and Deserialization in WPF DataGrid control | Syncfusion
description: Learn about Serialization and Deserialization support in Syncfusion WPF DataGrid (SfDataGrid) control and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Serialization and Deserialization in WPF DataGrid (SfDataGrid)

SfDataGrid allows you to serialize and deserialize the SfDataGrid settings using [DataContractSerializer](https://msdn.microsoft.com/en-in/library/system.runtime.serialization.datacontractserializer.aspx).
 
## Serialization 
You can serialize the SfDataGrid by using [SfDataGrid.Serialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Serialize(Stream).html) method which exports the current DataGrid control properties to an XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("DataGrid.xml"))
{           
    dataGrid.Serialize(file);
}    
{% endhighlight %}
{% endtabs %}


### Serialize as Stream

You can store the SfDataGrid settings as [Stream](https://msdn.microsoft.com/en-us/library/system.io.stream.aspx) using [Serialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Serialize(Stream).html) method by passing the stream.

{% tabs %}
{% highlight c# %}
FileStream stream = new FileStream("DataGrid", FileMode.Create);
this.dataGrid.Serialize(stream);
{% endhighlight %}
{% endtabs %}


## Serialization options 

SfDataGrid serialization  operation can be customized by passing [SerializationOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions.html) instance as an argument to [Serialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Serialize(Stream,SerializationOptions).html) method.


### Serialize sorting

By default, SfDataGrid allows you to serialize the sorting operation. You can disable the sorting serialization by setting the [SerializationOptions.SerializeSorting](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeSorting.html) to `false`.
 
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

By default, SfDataGrid allows you to serialize the grouping operation. You can disable the grouping  serialization by setting the [SerializationOptions.SerializeGrouping](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeGrouping.html) to `false`.
 
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

By default, SfDataGrid allows you to serialize the filtering operation. You can disable the filtering  serialization by setting the [SerializationOptions.SerializeFiltering](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeFiltering.html) to `false`.

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

By default, SfDataGrid allows you to serialize the columns manipulation operation. You can disable the columns serialization by setting the [SerializationOptions.SerializeColumns](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeColumns.html) to `false`.

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

You can disable the summaries serialization by setting [SerializationOptions.SerializeCaptionSummary](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeCaptionSummary.html) , [SerializationOptions.SerializeGroupSummaries](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeGroupSummaries.html) , [SerializationOptions.SerializeTableSummaries](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeTableSummaries.html) properties to `false`

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

By default, SfDataGrid allows you to serialize the stack headers operation. You can disable the stack headers serialization by setting the [SerializationOptions.SerializeStackedHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeStackedHeaders.html) to `false`.

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

By default, SfDataGrid allows you to serialize the DetailsViewDefinition. You can disable the DetailsViewDefinition serialization by setting the [SerializationOptions.SerializeDetailsViewDefinition](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeDetailsViewDefinition.html) to `false`.

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

By default, SfDataGrid allows you to serialize the unbound rows settings. You can disable the unbound rows serialization by setting the [SerializationOptions.SerializeUnBoundRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationOptions~SerializeUnBoundRows.html) to `false`.

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

You can deserialize the SfDataGrid setting by using [SfDataGrid.Deserialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Deserialize(Stream).html) method which reconstructs the SfDataGrid based on the setting in the stored XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("DataGrid.xml", FileMode.Open))
{
    dataGrid.Deserialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Deserialize from Stream

You can deserialize the SfDataGrid settings from [Stream](https://msdn.microsoft.com/en-us/library/system.io.stream.aspx) using [Deserialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Deserialize(Stream).html) method.

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream("DataGrid", FileMode.Open);
this.dataGrid.Deserialize(fileStream);
{% endhighlight %}
{% endtabs %}

## Deserialization options
 
Deserialization operation can be customized by passing [DeserializationOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions.html) instance as an argument to [Deserialize](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~Deserialize(Stream,DeserializationOptions).html) method.

### Deserialize sorting

By default, SfDataGrid allows you to deserialize the sorting operation. You can disable the sorting  deserialization by setting the [DeserializationOptions.DeserializeSorting](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeSorting.html) to `false`.
 
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

By default, SfDataGrid allows you to deserialize the grouping operation. You can disable the grouping deserialization by setting the [DeserializationOptions.DeserializeGrouping](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeGrouping.html) to `false`.
 
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

By default, SfDataGrid allows you to deserialize the filtering. you can disable the filtering deserialization by setting [DeserializationOptions.DeserializeFiltering](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeFiltering.html) to `false`.

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

By default, SfDataGrid allows you to deserialize the columns manipulation operations. You can disable the columns deserialization by setting the [DeserializationOptions.DeserializeColumns](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeColumns.html) to `false`.

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

You can disable the summaries deserialization by setting [DeserializationOptions.DeserializeCaptionSummary](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeCaptionSummary.html) , [DeserializationOptions.DeserializeGroupSummaries](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeGroupSummaries.html) , [DeserializationOptions.DeserializeTableSummaries](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeTableSummaries.html) properties to `false`.

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

By default, SfDataGrid allows you to deserialize the stack headers. You can disable the stacked headers deserialization by setting the [DeserializationOptions.DeserializeStackedHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeStackedHeaders.html) to `false`.

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

By default, SfDataGrid allows you to deserialize the DetailsViewDefinition. You can disable the DetailsViewDefinition deserialization by setting the [DeserializationOptions.DeserializeDetailsViewDefinition](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeDetailsViewDefinition.html) to `false`.

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

By default, SfDataGrid allows you to deserialize the unbound rows settings. You can disable the unbound rows deserialization by setting the [DeserializationOptions.DeserializeUnBoundRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DeserializationOptions~DeserializeUnBoundRows.html) to `false`.

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

SfDataGrid allows you to customize the serialization and deserialization operations by deriving [SerializationController](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController.html) class and override the necessary virtual methods.

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
 
1. Create a class derived from [SerializableGridColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializableGridColumn.html) and define the custom column properties in `SerializableCustomGridColumn` class.

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

2.Create a new class named as SerializationControllerExt by overriding [SerializationController](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController.html) class.

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

3.You can get the custom column property settings for serialization by overriding the [GetSerializableGridColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~GetSerializableDataGrid.html) virtual method.

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

4.Store the custom column property settings during serialization by overriding the [StoreGridColumnProperties](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~StoreGridColumnProperties.html) virtual method.
 
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

5.Add the custom column in to known column types by overriding the [KnownTypes](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~KnownTypes.html) virtual method.

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

6.During deserialization, you can get the custom column settings from [SerializableGridColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializableGridColumn.html) by overriding [GetGridColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~GetGridColumn.html) virtual method.
 
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

7.Now restore the custom column settings from SerializableGridColumn by overriding the [RestoreColumnProperties](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~RestoreColumnProperties.html) virtual method.

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

If you want to serialize and deserialize  the template content , you have to reconstruct  the same template during deserialization in  [RestoreColumnProperties](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SerializationController~RestoreColumnProperties.html) method.

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
