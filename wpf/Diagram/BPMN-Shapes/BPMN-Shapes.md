---
layout: post
title: BPMN Shapes in WPF Diagram control | Syncfusion
description: Learn here all about BPMN Shapes support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# BPMN Shapes in WPF Diagram (SfDiagram)

BPMN(Business Process Model and Notation) shapes are used to represent the internal business procedure in a graphical notation and enable you to communicate the procedures in a standard manner. To create BPMN shapes, you have to initialize [BpmnNodeViewModel]((https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html)) with the [Type](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_Type) property. The Type property can be set to any one of the built-in bpmn shapes using the BpmnShapeType enumeration. The default value for the Type property of BpmnNodeViewModel is "Activity".

The following code example explains how to create a simple business process.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity">
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
  Type = BpmnShapeType.Activity,
};

// Add the node into the Node's collection.
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create BPMNShapes](BPMN-Shapes-Images/BpmnShape_Default.png)


The list of supported BPMN shapes are as follows:

| Shape | Symbol | Description
| -------- | -------- | --------|
| Event | ![Event Shape](BPMN-Shapes-Images/Event.png) |Event shape represents something happens during a business process|
| Gateway | ![Gateway Shape](BPMN-Shapes-Images/Gateway.png) |Gateway is used to control the flow of a process|
| Activity | ![Task Shape](BPMN-Shapes-Images/Task.png) | Activities describe the kind of work being done in a particular process instance |
| Message | ![Message Shape](BPMN-Shapes-Images/Message.png) | The message is just the content of the communication|
| DataStore | ![Datasource Shape](BPMN-Shapes-Images/Datasource.png) |DataStore is used to store or access data associated with a business process|
| DataObject | ![Dataobject Shape](BPMN-Shapes-Images/Dataobject.png) |A DataObject represents information flowing using the process, such as data placed into the process, data resulting from the process, data that needs to be collected, or data that must be stored|
| TextAnnotation | ![TextAnnotation Shape](BPMN-Shapes-Images/TextAnnotation.png) |A TextAnnotation points at or references the another BPMN shape, which we call as the TextAnnotationTarget of the TextAnnotation|
| Group | ![Group Shape](BPMN-Shapes-Images/Group.png) |Organize tasks or processes that have significance in the overall process.|
| Expandedsubprocess | ![Expandedsubprocess Shape](BPMN-Shapes-Images/Expandedsubprocess.png) |ExpandedSubProcess is the extended version of the Group|
| Sequenceflow | ![Sequenceflow Shape](BPMN-Shapes-Images/Sequenceflow.png) |Sequence flows represent the typical path between two flow objects.|
| DefaultSequenceflow | ![DefaultSequenceflow Shape](BPMN-Shapes-Images/DefaultSequenceflow.png) |Default sequence flows are represented by an arrow with a tic mark on the one end|
| ConditionalSequenceflow | ![ConditionalSequenceflow Shape](BPMN-Shapes-Images/ConditionalSequenceflow.png) |Conditional sequence flows are used to control the flow of a process based on the certain conditions|
| Association | ![Association Shape](BPMN-Shapes-Images/Association.png) |An Association is represented as a dotted graphical line with an opened arrow.|
| DirectionalAssociation | ![DirectionalAssociation Shape](BPMN-Shapes-Images/DirectionalAssociation.png) | DirectionalAssociation is represented as a dotted graphical line with one side arrow.|
| BiDirectionalAssociation | ![BiDirectionalAssociation Shape](BPMN-Shapes-Images/BiDirectionalAssociation.png) |BiDirectionalAssociation is represented as a dotted graphical line with the double side arrow.|
| MessageFlow | ![MessageFlow Shape](BPMN-Shapes-Images/Messageflow.png) |A MessageFlow flow shows the flow of messages between two participants and is represented by line.|
| InitiatingMessageflow | ![InitiatingMessageflow Shape](BPMN-Shapes-Images/InitiatingMessageflow.png) | An activity or event in one pool can initiate a message to another pool|
| NonInitiatingMessageflow | ![NonInitiatingMessageflow Shape](BPMN-Shapes-Images/NonInitiatingMessageflow.png) | An activity or event in one pool cann't initiate a message to another pool|

Please find the BPMN Editor sample as follows.

[View BPMN Editor sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/BPMNEditor/Sample)
