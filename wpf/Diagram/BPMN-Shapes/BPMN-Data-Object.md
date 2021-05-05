---
layout: post
title: Data Object in WPF Diagram control | Syncfusion
description: Learn here all about Data Object support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---
# Data Object in WPF Diagram (SfDiagram)

A data object represents information flowing through the process, such as data placed into the process, data resulting from the process, data that needs to be collected, or data that must be stored. To define a [`DataObject`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#DataObject), the `Type` property of the `BpmnNodeViewModel` should be set to **DataObject** and the [DataObjectType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_DataObjectType) property defines whether the data is an input or output.
You can indicate the collection of data object by setting the `IsCollectiveData` property to `true`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="DataObject" DataObjectType="None"  IsCollectiveData="True"> 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel.
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.DataObject,
  DataObjectType = DataObjectType.None,
  IsCollectiveData = true,
};

// Add the node into the Node's collection.
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create DataObject](BPMN-Shapes-Images/IsCollectiveDataObject.png)

The following table contains various representation of the BPMN data object.

| DataObjectType | Symbol | IsCollectiveData|Description|
| -------- | -------- |-------- |-------- |
| None | ![Collection Data BPMN Shape](BPMN-Shapes-Images/DataObject.png) |![Collection Data BPMN Shape](BPMN-Shapes-Images/NoneCollectiveDataObject.png) |None of the business process with the signified information collected within a DataObject|
| Data Input | ![Data Input BPMN Shape](BPMN-Shapes-Images/InputDataObject.png) |![Collection Data BPMN Shape](BPMN-Shapes-Images/InputCollectiveDataObject.png) |Represents the data requirements that the tasks in the business process depend on with the signified information collected within a DataObject|
| Data Output | ![Data Output BPMN Shape](BPMN-Shapes-Images/OutputDataObject.png) |![Collection Data BPMN Shape](BPMN-Shapes-Images/OutputCollectiveDataObject.png) |Demonstrates information produced as the result of a business process with the signified information collected within a DataObject|
