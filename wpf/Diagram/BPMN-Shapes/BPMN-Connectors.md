---
layout: post
title: Connectors in WPF Diagram control | Syncfusion
description: Learn here all about Connectors support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Connectors in WPF Diagram (SfDiagram)

The [BpmnFlowViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html) are lines that used to connection between the BPMN flow objects.

They are represent in the following types.
* Association
* Sequence
* Message

## Association

The BPMN Association flow is used to link the flow objects with its corresponding text or artifact. An Association is represented as a dotted graphical line with an opened arrow. 

To create an [Association](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnFlowType.html#fields#Association), the [FlowType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnFlowViewModel_FlowType) property of the [BpmnFlowViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html) should be set to **Association**. The types of association are as follows:

* DirectionalAssociation: Represented as a dotted graphical line with one side arrow.
* BiDirectionalAssociation: Represented as a dotted graphical line with double side arrow.
* Association: An Association is represented as a dotted graphical line with an opened arrow.

 The following code example explains how to create an association.

{% tabs %}
{% highlight xaml %}
 <!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Connectors>
     <!--Initialize the Group Collection-->
     <syncfusion:ConnectorCollection>
        <syncfusion:BpmnFlowViewModel FlowType="Association" SourcePoint="100,100" TargetPoint="200,100"></syncfusion:BpmnFlowViewModel>
     </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnFlowViewModel.
 BpmnFlowViewModel flow = new BpmnFlowViewModel()
 {
    FlowType = BpmnFlowType.Association,
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 100)
 };
 // Add the BpmnFlowViewModel into the Connectors's collection.
(Diagram.Connectors as GroupCollection).Add(flow);

{% endhighlight %}
{%  endtabs %}

![BPMN Association](BPMN-Shapes-Images/Association.png)

The following table shows the visual representation of the association flows.

| FlowType | Symbol |
| -------- | -------- |
| Association | ![Default BPMN FlowShapes](BPMN-Shapes-Images/Association.png) |
| DirectionalAssociation | ![Directional BPMN FlowShapes](BPMN-Shapes-Images/DirectionalAssociation.png) |
| BiDirectionalAssociation | ![BiDirectional BPMN FlowShapes](BPMN-Shapes-Images/BiDirectionalAssociation.png) |


## SequenceFlow

A SequenceFlow flow shows the order that the activities are performed in a BPMN process and is represented by a solid graphical line. To create a [SequenceFlow](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnFlowType.html#fields#SequenceFlow), the [FlowType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnFlowViewModel_FlowType) property of the [BpmnFlowViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html) should be set to **SequenceFlow**. The types of sequence are as follows:

* SequenceFlow: Sequence flows represent the typical path between the two flow objects.
* ConditionalSequenceFlow: Conditional sequence flows are used to control the flow of a process based on the certain conditions.
* DefaultSequenceFlow: Default sequence flows are represented by an arrow with a tic mark on one end.

The sequence property allows you to define the type of sequence. The following code example explains how to create a sequence flow.

{% tabs %}
{% highlight xaml %}
 <!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Connectors>
     <!--Initialize the Group Collection-->
     <syncfusion:ConnectorCollection>
        <syncfusion:BpmnFlowViewModel FlowType="ConditionalSequenceFlow" SourcePoint="100,100" TargetPoint="200,100"></syncfusion:BpmnFlowViewModel>
     </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnFlowViewModel.
 BpmnFlowViewModel flow = new BpmnFlowViewModel()
 {
    FlowType = BpmnFlowType.ConditionalSequenceFlow,
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 100)
 };
 // Add the BpmnFlowViewModel into the Connectors's collection.
(Diagram.Connectors as GroupCollection).Add(flow);

{% endhighlight %}
{%  endtabs %}

![BPMN Association](BPMN-Shapes-Images/ConditionalSequenceFlow.png)

The following table contains various representation of sequence flows.

| FlowType | Symbol |
| -------- | -------- |
| SequenceFlow | ![SequenceFlow BPMN Shpae](BPMN-Shapes-Images/SequenceFlow.png) |
| ConditionalSequenceFlow | ![ConditionalSequenceFlow BPMN Shpae](BPMN-Shapes-Images/ConditionalSequenceFlow.png) |
| DefaultSequenceFlow | ![DefaultSequenceFlow BPMN Shpae](BPMN-Shapes-Images/DefaultSequenceFlow.png) |

## MessageFlow

Message flows are the two separately controlled processes communicate and collaborate with one another.  An activity or event in one pool can initiate a message to the another pool.  Message Flows are depicted as lines with an empty circle showing where the message originates and and empty arrowhead where the message terminates. To create a [MessageFlow](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnFlowType.html#fields#MessageFlow), the [FlowType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnFlowViewModel_FlowType) property of the [BpmnFlowViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnFlowViewModel.html) should be set to **MessageFlow**. The types of message are as follows:

* InitiatingMessageFlow: An activity or event in one pool can initiate a message to another pool.
* NonInitiatingMessageFlow: An activity or event in one pool can not initiate a message to another pool.
* MessageFlow: A MessageFlow flow shows the flow of messages between two participants and is represented by line.

The message property allows you to define the type of message. The following code example explains how to define a message flow.

{% tabs %}
{% highlight xaml %}
 <!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Connectors>
     <!--Initialize the Group Collection-->
     <syncfusion:ConnectorCollection>
        <syncfusion:BpmnFlowViewModel FlowType="InitiatingMessageFlow" SourcePoint="100,100" TargetPoint="200,100"></syncfusion:BpmnFlowViewModel>
     </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnFlowViewModel.
 BpmnFlowViewModel flow = new BpmnFlowViewModel()
 {
    FlowType = BpmnFlowType.InitiatingMessageFlow,
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 100)
 };
 // Add the BpmnFlowViewModel into the Connectors's collection.
(Diagram.Connectors as GroupCollection).Add(flow);

{% endhighlight %}
{%  endtabs %}

![BPMN MessageFlow](BPMN-Shapes-Images/InitiatingMessageFlow.png)

The following table contains various representation of the message flows.

| Message | Symbol |
| -------- | -------- |
| MessageFlow | ![MessageFlow BPMN Shape](BPMN-Shapes-Images/MessageFlow.png) |
| InitiatingMessageFlow | ![InitiatingMessageFlow BPMN Shape](BPMN-Shapes-Images/InitiatingMessageFlow.png) |
| NonInitiatingMessageFlow | ![NonInitiatingMessageFlow BPMN Shape](BPMN-Shapes-Images/NonInitiatingMessageFlow.png) |

>Note: The default value for the `FlowType` property is **SequenceFlow**.
