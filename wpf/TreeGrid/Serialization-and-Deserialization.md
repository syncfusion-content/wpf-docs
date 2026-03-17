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

You can serialize the SfTreeGrid by using [SfTreeGrid.Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Serialize_System_IO_Stream_) method which exports the current TreeGrid control properties to an XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Create("TreeGrid.xml"))
{           
    treeGrid.Serialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Serialize as Stream

You can store the SfTreeGrid settings as [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-8.0) using [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Serialize_System_IO_Stream_) method by passing the stream.

{% tabs %}
{% highlight c# %}
FileStream stream = new FileStream("TreeGrid", FileMode.Create);
this.treeGrid.Serialize(stream);
{% endhighlight %}
{% endtabs %}

## Serialization options 

SfTreeGrid serialization operation can be customized by passing [TreeGridSerializationOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationOptions.html) instance as an argument to [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Serialize_System_IO_Stream_Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationOptions_) method.

### Serialize sorting

By default, SfTreeGrid allows you to serialize the sorting operation. You can disable the sorting serialization by setting the [TreeGridSerializationOptions.SerializeSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationOptions_SerializeSorting) to `false`.
 
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

By default, SfTreeGrid allows you to serialize the filtering operation. You can disable the filtering serialization by setting the [TreeGridSerializationOptions.SerializeFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationOptions_SerializeFiltering) to `false`.

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

By default, SfTreeGrid allows you to serialize the columns manipulation operation. You can disable the columns serialization by setting the[TreeGridSerializationOptions.SerializeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationOptions_SerializeColumns) to `false`.

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

By default, SfTreeGrid allows you to serialize the stack headers operation. You can disable the stack headers serialization by setting the [TreeGridSerializationOptions.SerializeStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationOptions_SerializeStackedHeaders) to `false`.

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

You can deserialize the SfTreeGrid setting by using [SfTreeGrid.Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Deserialize_System_IO_Stream_) method which reconstructs the SfTreeGrid based on the setting in the stored XML file.

{% tabs %}
{% highlight c# %}
using (var file = File.Open("TreeGrid.xml", FileMode.Open))
{
    treeGrid.Deserialize(file);
}    
{% endhighlight %}
{% endtabs %}

### Deserialize from Stream

You can deserialize the SfTreeGrid settings from [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-8.0) using [Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Deserialize_System_IO_Stream_) method.

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream("TreeGrid", FileMode.Open);
this.treeGrid.Deserialize(fileStream);
{% endhighlight %}
{% endtabs %}

## Deserialization options
 
Deserialization operation can be customized by passing [TreeGridDeserializationOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDeserializationOptions.html) instance as an argument to [Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Deserialize_System_IO_Stream_Syncfusion_UI_Xaml_TreeGrid_TreeGridDeserializationOptions_) method.

### Deserialize sorting

By default, SfTreeGrid allows you to deserialize the sorting operation. You can disable the sorting  deserialization by setting the [TreeGridDeserializationOptions.DeserializeSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDeserializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridDeserializationOptions_DeserializeSorting) to `false`.
 
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

By default, SfTreeGrid allows you to deserialize the filtering. you can disable the filtering deserialization by setting [TreeGridDeserializationOptions.DeserializeFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDeserializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridDeserializationOptions_DeserializeFiltering) to `false`.

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

By default, SfTreeGrid allows you to deserialize the columns manipulation operations. You can disable the columns deserialization by setting the [TreeGridDeserializationOptions.DeserializeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDeserializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridDeserializationOptions_DeserializeColumns) to `false`.

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

By default, SfTreeGrid allows you to deserialize the stack headers. You can disable the stacked headers deserialization by setting the [TreeGridDeserializationOptions.DeserializeStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDeserializationOptions.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridDeserializationOptions_DeserializeStackedHeaders) to `false`.

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

SfTreeGrid allows you to customize the serialization and deserialization operations by deriving [TreeGridSerializationController](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html) class and override the necessary virtual methods.

### Serialize custom column 

By default, the unknown(custom) column types are serialized as `TreeGridTextColumn` type. If you want to serialize the custom column, you have to add custom column type into predefined types. 

In the below code snippet, TreeGridDatePickerColumn is created . For more information about creating custom column refer [here](https://help.syncfusion.com/wpf/treegrid/column-type#custom-column-support).

{% tabs %}
{% highlight c# %}
public class TreeGridDatePickerColumn : TreeGridColumn
{        
    public TreeGridDatePickerColumn()
    {
        SetCellType("DatePickerRenderer");
    }

    public static readonly DependencyProperty DateMappingNameProperty = DependencyProperty.Register("DateMappingName",
typeof(string), typeof(TreeGridDatePickerColumn));

    public string DateMappingName
    {
        get { return (string)GetValue(DateMappingNameProperty); }
        set { SetValue(DateMappingNameProperty, value); }
    }

    protected override Freezable CreateInstanceCore()
    {
        return new TreeGridDatePickerColumn();
    }

    protected override void SetDisplayBindingConverter()
    {
        (this.DisplayBinding as Binding).Converter = new CustomConverter();      
    }
}
{% endhighlight %}
{% endtabs %}

In the below code snippet, the TreeGridDatePickerColumn is defined in SfTreeGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
              ChildPropertyName="ReportsTo"
              ItemsSource="{Binding Employees}"
              ParentPropertyName="ID"
              AutoGenerateColumns="False"
              AllowEditing="True">

    <syncfusion:SfTreeGrid.Columns>
        <local:TreeGridDatePickerColumn HeaderText="DOJ" MappingName="DOJ" DateMappingName="JoiningDate"/>
    </syncfusion:SfTreeGrid.Columns>

</syncfusion:SfTreeGrid>
{% endhighlight %}
{% endtabs %}

To serialize the above TreeGridDatePickerColumn, follow the below steps.
 
1. Create a class derived from [SerializableTreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SerializableTreeGridColumn.html) and define the custom column properties in `SerializableCustomTreeGridColumn` class.

{% capture codesnippet1 %}
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
{% endcapture %}
{{ codesnippet1 | EmployeeList_Indent_Level_1 }}

2. Create a new class named as TreeGridSerializationControllerExt by overriding [TreeGridSerializationController](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html) class.

{% capture codesnippet2 %}
{% tabs %}
{% highlight c# %}
treeGrid.SerializationController = new TreeGridSerializationControllerExt(treeGrid);

public class TreeGridSerializationControllerExt : TreeGridSerializationController
{
 
    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | EmployeeList_Indent_Level_1 }}

3. You can get the custom column property settings for serialization by overriding the [GetSerializableTreeGridColumn](Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_GetSerializableTreeGridColumn_Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_) virtual method.

{% capture codesnippet3 %}
{% tabs %}
{% highlight c# %}
public class TreeGridSerializationControllerExt : TreeGridSerializationController
{

    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
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
{% endcapture %}
{{ codesnippet3 | EmployeeList_Indent_Level_1 }}

4. Store the custom column property settings during serialization by overriding the [StoreTreeGridColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_StoreTreeGridColumnProperties_Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_Syncfusion_UI_Xaml_TreeGrid_SerializableTreeGridColumn_) virtual method.

{% capture codesnippet4 %} 
{% tabs %}
{% highlight c# %}
public class TreeGridSerializationControllerExt : TreeGridSerializationController
{

    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
            : base(treeGrid)
    {
    }

    protected override void StoreTreeGridColumnProperties(TreeGridColumn column, SerializableTreeGridColumn serializableColumn)
    {
        base.StoreTreeGridColumnProperties(column, serializableColumn);

        if (column is TreeGridDatePickerColumn)
            (serializableColumn as SerializableCustomTreeGridColumn).DateMappingName = (column as TreeGridDatePickerColumn).DateMappingName;
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet4 | EmployeeList_Indent_Level_1 }}

5. Add the custom column into known column types by overriding the [KnownTypes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_KnownTypes) virtual method.

{% capture codesnippet5 %}
{% tabs %}
{% highlight c# %}
public class TreeGridSerializationControllerExt : TreeGridSerializationController
{
    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
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
{% endcapture %}
{{ codesnippet5 | EmployeeList_Indent_Level_1 }}

6. During deserialization, you can get the custom column settings from [SerializableTreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SerializableTreeGridColumn.html) by overriding [GetTreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_GetTreeGridColumn_Syncfusion_UI_Xaml_TreeGrid_SerializableTreeGridColumn_) virtual method.

{% capture codesnippet6 %} 
{% tabs %}
{% highlight c# %}
public class TreeGridSerializationControllerExt : TreeGridSerializationController
{
    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
            : base(treeGrid)
    {
    }

    protected override TreeGridColumn GetTreeGridColumn(SerializableTreeGridColumn serializableColumn)
    {

        if (serializableColumn is SerializableCustomTreeGridColumn)
            return new TreeGridDatePickerColumn();
            return base.GetTreeGridColumn(serializableColumn);
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet6 | EmployeeList_Indent_Level_1 }}

7. Now restore the custom column settings from SerializableTreeGridColumn by overriding the [RestoreColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_RestoreColumnProperties_Syncfusion_UI_Xaml_TreeGrid_SerializableTreeGridColumn_Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_) virtual method.

{% capture codesnippet7 %}
{% tabs %}
{% highlight c# %}
public class TreeGridSerializationControllerExt : TreeGridSerializationController
{

    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
        : base(treeGrid)
    {
    }

    protected override void RestoreColumnProperties(SerializableTreeGridColumn serializableColumn, TreeGridColumn column)
    {
        base.RestoreColumnProperties(serializableColumn, column);
        
        if (column is TreeGridDatePickerColumn)
            (column as TreeGridDatePickerColumn).DateMappingName = (serializableColumn as SerializableCustomTreeGridColumn).DateMappingName;
    }

}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet7 | EmloyeeList_Indent_Level_1 }}

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

If you want to serialize and deserialize the template content, you have to reconstruct the same template during deserialization in [RestoreColumnProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSerializationController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridSerializationController_RestoreColumnProperties_Syncfusion_UI_Xaml_TreeGrid_SerializableTreeGridColumn_Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_) method.

{% tabs %}
{% highlight c# %}
this.treeGrid.SerializationController = new TreeGridSerializationControllerExt(this.treeGrid);

public class TreeGridSerializationControllerExt : TreeGridSerializationController
{

    public TreeGridSerializationControllerExt(SfTreeGrid treeGrid)
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
