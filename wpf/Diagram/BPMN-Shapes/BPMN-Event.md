---
layout: post
title: BPMN Event | Syncfusion 
description: Event is notated with a circle and it represents an event in a business process.
platform: wpf
control: SfDiagram
documentation: ug
---
# BPMN event

An [`Event`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#Event) is a common BPMN process model element that represents something happens during a business process and its is notated with a circle.
The [EventType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_EventType) property of the node allows you to set the type of event and by default, it is set to None.
 The type of events are as follows:

    * Start - indicates the beginning of the process and every business process start with an event.
    * Intermediate - indicates the middle of the process.
    * End - indicates the beginning of the process and every business process end with an event.

The event property of the node allows you to define the type of the event. The default value of the event is [Start](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.EventType.html#fields#Start). The following code example explains how to create a BPMN event.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Event" EventType="Start">
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Event,
  EventType = EventType.Start,
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Event](BPMN-Shapes-Images/None1.png)

## BPMN event trigger

Event triggers are notated as icons inside the circle and they represent the specific details of the process. The [EventTrigger](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_EventTrigger) property of the node allows you to set the type of trigger and by default, it is set to None. The following code example explains how to create a BPMN trigger.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="50" UnitWidth="50" OffsetX="100" OffsetY="100" Type="Event" EventType="Start" EventTrigger="Message">
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 50,
  UnitWidth = 50,
  Type = BpmnShapeType.Event,
  EventType = EventType.Start,
  EventTrigger = EventTrigger.Message
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Event and Trigger](BPMN-Shapes-Images/Message1.png)

The following table illustrates the type of event triggers.

| Event / Trigger | Start | Non-Interrupting Start | Intermediate | Non-Interrupting Intermediate | Throwing Intermediate | End |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| None | ![None Trigger Start event BPMN Shape](BPMN-Shapes-Images/None1.png)  | ![None Trigger Interupting event BPMN Shape](BPMN-Shapes-Images/None2.png) | ![None Trigger Intermediate event  BPMN Shape](BPMN-Shapes-Images/None3.png) | ![None Trigger NonInteruptingIntermediate BPMNShape](BPMN-Shapes-Images/None4.png) |![None Trigger Throwing Intermediate event BPMNShape](BPMN-Shapes-Images/None5.png) | ![None Trigger End event  event  BPMNShape](BPMN-Shapes-Images/None6.png) |
| Message | ![Message Trigger Start Event BPMN Shape](BPMN-Shapes-Images/Message1.png) | ![Message Trigger NonInterupting Event BPMN Shape](BPMN-Shapes-Images/Message2.png) | ![Message Trigger Intermediate Event BPMN Shape](BPMN-Shapes-Images/Message3.png) | ![Message Trigger NonInteruptingIntermediate Event BPMN Shape](BPMN-Shapes-Images/Message4.png) |![Message Trigger ThrowingIntermediate Event BPMNShape](BPMN-Shapes-Images/Message5.png) | ![Message Trigger End Event BPMN EndShape](BPMN-Shapes-Images/Message6.png) |
| Timer | ![Timer Trigger Start Event BPMNShape](BPMN-Shapes-Images/Timer1.png) | ![Timer Trigger NonInterupting Event BPMN Shape](BPMN-Shapes-Images/Timer2.png) | ![Timer Trigger Intermediate Event BPMN Shape](BPMN-Shapes-Images/Timer3.png)|![Timer Trigger NonInteruptingIntermediate  Event BPMN Shape](BPMN-Shapes-Images/Timer4.png) |![Timer Trigger Throwing Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Timer5.png) |![Timer Trigger End Event BPMN Shape](BPMN-Shapes-Images/Timer6.png) |
| Conditional | ![Conditional Trigger Start BPMN Shape](BPMN-Shapes-Images/Conditional1.png) | ![Conditional Trigger NonInterupting BPMN Shape](BPMN-Shapes-Images/Conditional2.png) | ![Conditional Trigger Intermediate BPMN Shape](BPMN-Shapes-Images/Conditional3.png) |![Conditional Trigger NonInteruptingIntermediateBPMNShape](BPMN-Shapes-Images/Conditional4.png) |![Conditional Trigger ThrowingIntermediateBPMNShape](BPMN-Shapes-Images/Conditional5.png) |![Conditional Trigger EndBPMNShape](BPMN-Shapes-Images/Conditional6.png) |
| Link | ![Link Trigger Start BPMN Shape](BPMN-Shapes-Images/Link1.png) | ![Link Trigger NonInterupting BPMN Shape](BPMN-Shapes-Images/Link2.png) |![Link Trigger Intermediate Event BPMNShape](BPMN-Shapes-Images/Link3.png) |![Link Trigger NonInteruptingIntermediateBPMNShape](BPMN-Shapes-Images/Link4.png) | ![Link Trigger ThrowingIntermediate  Event BPMN Shape](BPMN-Shapes-Images/Link5.png) |![Link Trigger EndBPMNShape](BPMN-Shapes-Images/Link6.png) |
| Signal | ![Signal Trigger Start Event BPMN Shape](BPMN-Shapes-Images/Signal1.png) | ![Signal Trigger NonInterrupting Event BPMN Shape](BPMN-Shapes-Images/Signal2.png) | ![Signal Trigger Intermediate Event BPMN Shape](BPMN-Shapes-Images/Signal3.png) | ![Signal Trigger NonInterrupting Event BPMN Shape](BPMN-Shapes-Images/Signal4.png) | ![SignalThrowing Trigger Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Signal5.png) | ![Signal Trigger End Event BPMN Shape](BPMN-Shapes-Images/Signal6.png) |
| Error | ![Error Trigger Start Event BPMN Shape](BPMN-Shapes-Images/Error1.png) | ![Error Trigger NonInterrupting Event BPMN Shape](BPMN-Shapes-Images/Error2.png) | ![Error Trigger Intermediate Event BPMN Shape](BPMN-Shapes-Images/Error3.png) |![Error Trigger NonInterrupting Event BPMN Shape](BPMN-Shapes-Images/Error4.png) | ![Error Throwing Trigger Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Error5.png)| ![Error Trigger End Event BPMN Shape](BPMN-Shapes-Images/Error6.png)|
| Escalation | ![Escalation Trigger Start Event BPMN Shape](BPMN-Shapes-Images/Esclation1.png) | ![Escalation  Trigger  Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Esclation2.png) | ![Escalation  Trigger  Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Esclation3.png) | ![Escalation  Trigger Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Esclation4.png)| ![Escalation  Trigger  Throwing Intermediate Event  BPMN Shape](BPMN-Shapes-Images/Esclation5.png) |  ![Escalation  Trigger  End Event BPMN Shape](BPMN-Shapes-Images/Esclation6.png)|
| Termination | ![Termination Trigger Start Event BPMN Shape](BPMN-Shapes-Images/Termination1.png) | ![Termination  Trigger  Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Termination2.png) | ![Termination  Trigger  Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Termination3.png) | ![Termination  Trigger Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Termination4.png) | ![Termination  Trigger  Throwing Intermediate Event  BPMN Shape](BPMN-Shapes-Images/Termination5.png) | ![Termination Trigger End  Event BPMN Shape](BPMN-Shapes-Images/Termination6.png)|
| Compensation |![Compensation  Trigger Start Event  BPMN Shape](BPMN-Shapes-Images/Compensation1.png)  | ![Compensation  Trigger  Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Compensation2.png) | ![Compensation Trigger Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Compensation3.png) |![Compensation  Trigger Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Compensation4.png) | ![Compensation  Trigger  Throwing Intermediate Event  BPMN Shape](BPMN-Shapes-Images/Compensation5.png) |![Compensation  Trigger End BPMN  Event Shape](BPMN-Shapes-Images/Compensation6.png) |
| Cancel |![Cancel  Trigger Start Event  BPMN Shape](BPMN-Shapes-Images/Cancel1.png)  | ![Cancel  Trigger  Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Cancel2.png) | ![Cancel Trigger Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Cancel3.png) |![Cancel  Trigger Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Cancel4.png) | ![Cancel  Trigger  Throwing Intermediate Event  BPMN Shape](BPMN-Shapes-Images/Cancel5.png)  | ![Cancel Trigger End  Event BPMN Shape](BPMN-Shapes-Images/Cancel6.png) |
| Multiple | ![Multiple Trigger Start  Event BPMN Shape](BPMN-Shapes-Images/Multiple1.png) | ![Multiple Trigger Non-Interrupting  Event BPMN Shape](BPMN-Shapes-Images/Multiple2.png)  | ![Multiple Trigger Intermediate BPMN Shape](BPMN-Shapes-Images/Multiple3.png) | ![Multiple Trigger Non-Interrupting Event BPMN Shape](BPMN-Shapes-Images/Multiple4.png) | ![Multiple Trigger  Throwing Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Multiple5.png)  | ![Multiple Trigger End Event  BPMN Shape](BPMN-Shapes-Images/Multiple6.png) |
| Parallel | ![Parallel Trigger Start  Event BPMN Shape](BPMN-Shapes-Images/Parallel1.png) | ![Parallel Trigger Non-Interrupting Event  BPMN Shape](BPMN-Shapes-Images/Parallel2.png) | ![Parallel Trigger Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Parallel3.png) | ![Parallel Trigger End Event  BPMN Shape](BPMN-Shapes-Images/Parallel4.png) | ![Parallel Trigger  Throwing Intermediate  Event BPMN Shape](BPMN-Shapes-Images/Parallel5.png)  | ![Parallel Trigger End Event  BPMN Shape](BPMN-Shapes-Images/Parallel6.png)  |
