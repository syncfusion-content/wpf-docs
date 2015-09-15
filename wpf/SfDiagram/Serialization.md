---
layout: post
title: Serialization
description: serialization
platform: wpf
control: Control Name undefined
documentation: ug
---

### Serialization

Serialization is the process of saving and loading the Essential Diagram for state persistence of the SfDiagram.



In SfDiagram, DataContractSerializer is used for serialization. The functionalities in DataContractSerializer are applicable to the SfDiagram Serialization. It supports saving the SfDiagram to stream; the SfDiagram gets saved with all its properties. On loading, it gets loaded in the current view with all its nodes and connections. As a result, this feature enables you to save the SfDiagram for future use. You can continue working on the SfDiagram by loading the appropriate stream.


The following code example illustrates how to save and load the SfDiagram control to Stream:

[C#]



// SfDiagram saved to Stream.

SfDiagram sfdigram = new SfDiagram();

System.IO.MemoryStream str = new System.IO.MemoryStream();

sfdiagram.Save(str);



// SfDiagram loaded to Stream.

sfdiagram.Load(str);



Serialization of Nodes

The properties in INode interface and Known types are serializable.

For example, the following steps illustrate how to serialize the Custom Property:


1. All serializable [DataMember] custom fields or custom properties in a [DataContract] type must be set to public, and read or write.



[C#]



[DataContract]

public class NodeContent : INotifyPropertyChanged

{

[DataMember]

public string NodeType

{

get;

set;            

}

}



2. Known types must be specified in code for the custom class.



[C#]



sfdiagram.KnownTypes = () => new List<Type>()

{

typeof(NodeContent)

};



In the preceding code, NodeContent is unknown type to Serializer. This is similar to IConnector and IGroup.



