---
layout: post
title: Serialization in WPF TreeGrid Control | Syncfusion®
description: Learn here all about Serialization and Deserialization support in Syncfusion® WPF TreeGrid (SfTreeGrid) control and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Serialization and Deserialization in WPF TreeGrid

SfTreeGrid allows you to serialize and deserialize the SfTreeGrid settings using [DataContractSerializer](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.serialization.datacontractserializer?view=net-8.0).
 
## Serialization

You can serialize the SfTreeGrid by using `SfTreeGrid.Serialize` method which exports the current TreeGrid control properties to an XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{           
    treeGrid.Serialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Serialize as Stream

You can store the SfTreeGrid settings as [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-8.0) using `Serialize` method by passing the stream.

{% tabs %}
{% highlight c# %}
FileStream stream = new FileStream("TreeGrid", FileMode.Create);
this.treeGrid.Serialize(stream);
{% endhighlight %}
{% endtabs %}

## Serialization options 

SfTreeGrid serialization operation can be customized by passing `TreeGridSerializationOptions` instance as an argument to `Serialize` method.

### Serialize sorting

By default, SfTreeGrid allows you to serialize the sorting operation. You can disable the sorting serialization by setting the `TreeGridSerializationOptions.SerializeSorting` to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{
    TreeGridSerializationOptions options = new TreeGridSerializationOptions();
    options.SerializeSorting = false;
    treeGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize filtering

By default, SfTreeGrid allows you to serialize the filtering operation. You can disable the filtering serialization by setting the `TreeGridSerializationOptions.SerializeFiltering` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{
    TreeGridSerializationOptions options = new TreeGridSerializationOptions();
    options.SerializeFiltering = false;
    treeGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize columns

By default, SfTreeGrid allows you to serialize the columns manipulation operation. You can disable the columns serialization by setting the `TreeGridSerializationOptions.SerializeColumns` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{
    TreeGridSerializationOptions options = new TreeGridSerializationOptions();
    options.SerializeColumns = false;
    treeGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Serialize stacked headers

By default, SfTreeGrid allows you to serialize the stack headers operation. You can disable the stack headers serialization by setting the `TreeGridSerializationOptions.SerializeStackedHeaders` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{
    TreeGridSerializationOptions options = new TreeGridSerializationOptions();
    options.SerializeStackHeaders = false;
    treeGrid.Serialize(file, options);
}
{% endhighlight %}
{% endtabs %}

## Deserialization

You can deserialize the SfTreeGrid setting by using `SfTreeGrid.Deserialize` method which reconstructs the SfTreeGrid based on the setting in the stored XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    treeGrid.Deserialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Deserialize from Stream

You can deserialize the SfTreeGrid settings from [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-8.0) using `Deserialize` method.

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream("TreeGrid", FileMode.Open);
this.treeGrid.Deserialize(fileStream);
{% endhighlight %}
{% endtabs %}

## Deserialization options
 
Deserialization operation can be customized by passing `TreeGridDeserializationOptions` instance as an argument to `Deserialize` method.

### Deserialize sorting

By default, SfTreeGrid allows you to deserialize the sorting operation. You can disable the sorting  deserialization by setting the `TreeGridDeserializationOptions.DeserializeSorting` to `false`.
 
{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    TreeGridDeserializationOptions options = new TreeGridDeserializationOptions();
    options.DeserializeSorting = false ;
    treeGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize filtering

By default, SfTreeGrid allows you to deserialize the filtering. you can disable the filtering deserialization by setting `TreeGridDeserializationOptions.DeserializeFiltering` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    TreeGridDeserializationOptions options = new TreeGridDeserializationOptions();
    options.DeserializeFiltering = false ;
    treeGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize columns

By default, SfTreeGrid allows you to deserialize the columns manipulation operations. You can disable the columns deserialization by setting the `TreeGridDeserializationOptions.DeserializeColumns` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    TreeGridDeserializationOptions options = new TreeGridDeserializationOptions();
    options.DeserializeColumns = false ;
    treeGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

### Deserialize stacked headers

By default, SfTreeGrid allows you to deserialize the stack headers. You can disable the stacked headers deserialization by setting the `TreeGridDeserializationOptions.DeserializeStackedHeaders` to `false`.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    TreeGridDeserializationOptions options = new TreeGridDeserializationOptions();
    options.DeserializeStackedHeaders = false ;
    treeGrid.Deserialize(file, options);
}
{% endhighlight %}
{% endtabs %}

## Customizing Serialization and Deserialization Operations

SfTreeGrid allows you to customize the serialization and deserialization operations by deriving `TreeGridSerializationController` class and override the necessary virtual methods.

### Serialize custom column 

By default, the unknown(custom) column types are serialized as `TreeGridTextColumn` type. If you want to serialize the custom column, you have to add custom column type into predefined types. 

In the below code snippet, DatePickerColumn is created . For more information about creating custom column refer [here](https://help.syncfusion.com/wpf/treegrid/column-type#custom-column-support).

{% tabs %}
{% highlight c# %}
public class DatePickerColumn : TreeGridColumn
{        
    public DatePickerColumn()
    {
        SetCellType("DatePickerRenderer");
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

In the below code snippet, the DatePickerColumn is defined in SfTreeGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
              ChildPropertyName="ReportsTo"
              ItemsSource="{Binding Employees}"
              ParentPropertyName="ID"
              AutoGenerateColumns="False"
              AllowEditing="True">

    <syncfusion:SfTreeGrid.Columns>
        <local:DatePickerColumn HeaderText="DOJ" MappingName="DOJ" DateMappingName="JoiningDate"/>
    </syncfusion:SfTreeGrid.Columns>

</syncfusion:SfTreeGrid>
{% endhighlight %}
{% endtabs %}

To serialize the above DatePickerColumn, follow the below steps.
 
1. Create a class derived from `SerializableTreeGridColumn`and define the custom column properties in `SerializableCustomTreeGridColumn` class.

{% tabs %}
{% highlight c# %}
[DataContract(Name="SerializableCustomTreeGridColumn")]

public class SerializableCustomTreeGridColumn : SerializableTreeGridColumn
{
    [DataMember]

    public string DateMappingName { get; set; }
}
{% endhighlight %}
{% endtabs %}

2. Create a new class named as SerializationControllerExt by overriding `TreeGridSerializationController` class.

{% tabs %}
{% highlight c# %}
treeGrid.SerializationController = new SerializationControllerExt(treeGrid);

public class SerializationControllerExt : TreeGridSerializationController
{
 
    public SerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {
    }
}
{% endhighlight %}
{% endtabs %}

3. You can get the custom column property settings for serialization by overriding the `GetSerializableTreeGridColumn` virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : TreeGridSerializationController
{

    public SerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {
    }

    protected override SerializableTreeGridColumn GetSerializableTreeGridColumn(TreeGridColumn column)
    {

        if (column.MappingName == "DOJ")
        {
            return new SerializableCustomTreeGridColumn();
        }
        return base.GetSerializableTreeGridColumn(column);
    }
}
{% endhighlight %}
{% endtabs %}

4. Store the custom column property settings during serialization by overriding the `StoreTreeGridColumnProperties` virtual method.
 
{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : TreeGridSerializationController
{

    public SerializationControllerExt(SfTreeGrid treeGrid)
            : base(treeGrid)
    {
    }

    protected override void StoreTreeGridColumnProperties(TreeGridColumn column, SerializableTreeGridColumn serializableColumn)
    {
        base.StoreTreeGridColumnProperties(column, serializableColumn);

        if (column is DatePickerColumn)
            (serializableColumn as SerializableCustomTreeGridColumn).DateMappingName = (column as DatePickerColumn).DateMappingName;
    }
}
{% endhighlight %}
{% endtabs %}

5. Add the custom column into known column types by overriding the `KnownTypes` virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : TreeGridSerializationController
{
    public SerializationControllerExt(SfTreeGrid treeGrid)
            : base(treeGrid)
    {
    }

    public override Type[] KnownTypes()
    {
        var types = base.KnownTypes();
        var list = types.Cast<Type>().ToList();
        list.Add(typeof(SerializableCustomTreeGridColumn));
        return list.ToArray();
    }
}
{% endhighlight %}
{% endtabs %}

6. During deserialization, you can get the custom column settings from `SerializableTreeGridColumn` by overriding `GetTreeGridColumn`virtual method.
 
{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : TreeGridSerializationController
{
    public SerializationControllerExt(SfDataGrid dataGrid)
            : base(dataGrid)
    {
    }

    protected override TreeGridColumn GetTreeGridColumn(SerializableTreeGridColumn serializableColumn)
    {

        if (serializableColumn is SerializableCustomTreeGridColumn)
            return new DatePickerColumn();
            return base.GetTreeGridColumn(serializableColumn);
    }
}
{% endhighlight %}
{% endtabs %}

7. Now restore the custom column settings from SerializableTreeGridColumn by overriding the `RestoreColumnProperties` virtual method.

{% tabs %}
{% highlight c# %}
public class SerializationControllerExt : TreeGridSerializationController
{

    public SerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {
    }

    protected override void RestoreColumnProperties(SerializableTreeGridColumn serializableColumn, TreeGridColumn column)
    {
        base.RestoreColumnProperties(serializableColumn, column);
        
        if (column is DatePickerColumn)
            (column as DatePickerColumn).DateMappingName = (serializableColumn as SerializableCustomTreeGridColumn).DateMappingName;
    }

}
{% endhighlight %}
{% endtabs %}

You can download the sample demo `here`.

### Serializing template column content

By default, you cannot serialize the template content in SfTreeGrid. This is the default behavior during  Serialization and Deserialization operation.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <DataTemplate x:Key="cellTemplate">
        <Button Content="{Binding Value}" />
    </DataTemplate>
</Application.Resources>

<syncfusion:SfTreeGrid Name="treeGrid"
              ChildPropertyName="ReportsTo"
              ItemsSource="{Binding Employees}"
              ParentPropertyName="ID"
              AutoGenerateColumns="False">

    <syncfusion:SfTreeGrid.Columns>

        <syncfusion:TreeGridTemplateColumn CellTemplate="{StaticResource cellTemplate}"
                                       HeaderText="Salary"
                                       MappingName="Salary"
                                       SetCellBoundValue="True" />        
    </syncfusion:SfTreeGrid.Columns>

</syncfusion:SfTreeGrid>
{% endhighlight %}
{% endtabs %}

If you want to serialize and deserialize the template content, you have to reconstruct the same template during deserialization in `RestoreColumnProperties` method.

{% tabs %}
{% highlight c# %}
this.treeGrid.SerializationController = new SerializationControllerExt(this.treeGrid);

public class SerializationControllerExt : TreeGridSerializationController
{

    public SerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {

    }
        
    protected override void RestoreColumnProperties(SerializableTreeGridColumn serializableColumn, TreeGridColumn column)
    {
        base.RestoreColumnProperties(serializableColumn, column);

        if (column is TreeGridTemplateColumn)
        {

            if (column.MappingName == "Salary")
            {
                column.CellTemplate = App.Current.Resources["cellTemplate"] as DataTemplate;
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample demo `here`.