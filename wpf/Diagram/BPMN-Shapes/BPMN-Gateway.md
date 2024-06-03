---
layout: post
title: Gateway in WPF Diagram control | Syncfusion
description: Learn here all about Gateway support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Gateway in WPF Diagram (SfDiagram)

Gateway is used to control the flow of a process and it is represented as a diamond shape. To create a gateway shape, the [`Type`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_Type) property of the [`BpmnNodeViewModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html) should be set to [Gateway](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#GateWay) and the [`GatewayType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_GatewayType) property can be set to any of the appropriate [GatewayType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.GatewayType.html). The default `GatewayType` will be [`None`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.GatewayType.html#fields). The following code example explains how to create a BPMN Gateway.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Gateway" GatewayType="None"> 
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
  Type = BpmnShapeType.Gateway,
  GatewayType = GatewayType.None
};

// Add the node into the Node's collection.
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Gateway](BPMN-Shapes-Images/bpmn-gataway-none.png)


The following table shows the different types of gateways:

| GatewayType | Symbol |Description|
| -------- | -------- | -------- |
| None | ![GateWay BPMN Shape](BPMN-Shapes-Images/bpmn-gataway-none.png) |It is represented as a diamond shape. None of the symbol shows inside this shape|
| Exclusive | ![Exclusive GateWay BPMN Shape](BPMN-Shapes-Images/Exclusive.png) |It is a state of the business process and based on the condition, breaks the flow into one or more mutually exclusive paths|
| Parallel | ![Parallel GateWay BPMN Shape](BPMN-Shapes-Images/Parallel.png) |The Parallel gateways are used to represent two concurrent tasks in a business flow|
| Inclusive | ![Inclusive GateWay BPMN Shape](BPMN-Shapes-Images/Inclusive.png) |Breaks the process flow into one or more flows|
| Complex | ![Complex GateWay BPMN Shape](BPMN-Shapes-Images/Complex.png) |These gateways are only used for the most complex flows in a business process|
| EventBased | ![EventBased GateWay BPMNShape](BPMN-Shapes-Images/EventBased.png) |The event-based Gateway allows you to make a decision based on events|
| ExclusiveEventBased | ![Exclusive EventBased GateWay BPMN Shape](BPMN-Shapes-Images/EEBased.png) |Starts a new process instance with each occurrence of a subsequent event|
| ParallelEventBased | ![Parallel EventBased GateWay BPMN Shape](BPMN-Shapes-Images/PEBased.png) |This gateway is similar to a parallel gateway. It allows for multiple processes to happen at the same time but unlike the parallel gateway, the processes are event-dependent|
