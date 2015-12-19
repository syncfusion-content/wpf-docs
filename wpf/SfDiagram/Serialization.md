# Serialization

Serialization is the process of saving and loading the Essential Diagram for state persistence of the SfDiagram.

In SfDiagram, DataContractSerializer is used for Serialization. The functionalities in DataContractSerializer are applicable to the SfDiagram Serialization. It supports saving the SfDiagram to stream. The SfDiagram gets saved with all its properties. On loading, it gets loaded in the currect view with all its Nodes and Connectors. As a result, this feature enables you to save the SfDiagram for future use. You can continue working on the SfDiagram by loading the appropriate stream.

The following code example illustrate how to save and load the SfDiagram control to Stream

<table>
<tr>
<td>
{{'__//__'| markdownify }}{{'__SfDiagram__ '| markdownify }}{{'__saved__ '| markdownify }}{{'__to__ '| markdownify }}{{'__steam__'| markdownify }}{{'____'| markdownify }}<br/><br/>SfDiagram sfdiagram = new SfDiagram();<br/><br/>System.IO.MemoryStream str = new System.IO.MemoryStream();<br/><br/>sfdiagram.Save(str);<br/><br/>{{'__//__'| markdownify }}{{'__SfDiagram__ '| markdownify }}{{'__loaded__ '| markdownify }}{{'__to__ '| markdownify }}{{'__stream__'| markdownify }}{{'____'| markdownify }}<br/><br/>sfdiagram.Load(str);<br/><br/><br/><br/></td></tr>
</table>
Serialization of Nodes

The properties in INode interface and Known types are serializable.

For example, the following steps illustrate how to serialize the Custom Property:

1. All serializable [DataMember] custom fields or custom properties in a [DataContract] type must be set to public, and read or write.
<table>
<tr>
<td>
<br/>public class NodeContent : INotifyPropertyChanged<br/><br/>{<br/><br/>[DataMember]<br/><br/>public string NodeType<br/><br/>{<br/><br/>get;<br/><br/>set;<br/><br/>}<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
2. Known types must be specified in code for the custom class.
<table>
<tr>
<td>
<br/>sfdiagram.KnownTypes = () => new List<Type>()<br/><br/>{<br/><br/>typeof(NodeContent)<br/><br/>};<br/><br/><br/><br/></td></tr>
</table>
In the preceding code, NodeContent is unknown type to Serializer. This is similar to IConnector and IGroup.

