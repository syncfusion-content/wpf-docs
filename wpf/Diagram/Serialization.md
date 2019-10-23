---
layout: post
title: Serialize the Diagram as XAML and load Diagram from serialized XAML.
description: How to save and load the Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---

# Serialization

Serialization is the process of saving and loading the Essential Diagram for state persistence of the SfDiagram.

In SfDiagram, DataContractSerializer is used for Serialization. The functionalities in DataContractSerializer are applicable to the SfDiagram Serialization. It supports saving the SfDiagram to stream. The SfDiagram gets saved with all its properties. On loading, it gets loaded in the current view with all its Nodes and Connectors. As a result, this feature enables you to save the SfDiagram for future use. You can continue working on the SfDiagram by loading the appropriate stream.

{% highlight C# %}

//SfDiagram saved to steam

SfDiagram sfdiagram = new SfDiagram();

System.IO.MemoryStream str = new System.IO.MemoryStream();

sfdiagram.Save(str);

//SfDiagram loaded to stream

str.Position = 0;

sfdiagram.Load(str);

{% endhighlight %}

## Serialization of Nodes

The properties in INode interface and Known types are serializable.

For example, the following steps illustrate how to serialize the Custom Property:

### All serializable [DataMember] custom fields or custom properties in a [DataContract] type must be set to public, and read or write.

{% highlight C# %}

public class NodeContent : INotifyPropertyChanged
{
	[DataMember]
       public string NodeType
       {
		get;
		set;
	}
}

{% endhighlight %}

### Known types must be specified in code for the custom class.

{% highlight C# %}

sfdiagram.KnownTypes = () => new List<Type>()
{
	typeof(NodeContent)

};

{% endhighlight %}

If we need to serialize the NodeType property(custom property) of NodeContent(custom class), then we must add DataMember attribute to NodeType property.

In the preceding code, NodeContent is unknown type to Serializer. So, we must specify the type to the KnownTypes of SfDiagram.

I> We should not add DataMember attribute to the built-in properties of built-in classes(Node, Connector, INode, IConnector,....).

Diagram can also be saved as raster or vector image files. For more information about saving the Diagram as images, refer to [Exporting](/wpf/sfdiagram/exporting "Exporting").