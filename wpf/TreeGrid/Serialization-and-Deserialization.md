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