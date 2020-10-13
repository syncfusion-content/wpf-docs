---
layout: post
title: Visualize graphical object using BPMN Gateway | Syncfusion 
description: How th eBPMN Gateway is used to control the flow of a business process and how to customize their appearance?
platform: wpf
control: SfDiagram
documentation: ug
---

# BPMN gateway and its customization

Gateway is used to control the flow of a process and it is represented as a diamond shape. To create a gateway shape, the `Type` property of the `BpmnNodeViewModel` should be set to [Gateway](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#GateWay) and the `GatewayType` property can be set to any of the appropriate [[GatewayType]](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.GatewayType.html). The default[GatewayType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_GatewayType) will be **None**. The following code example explains how to create a BPMN Gateway.

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

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Gateway,
  GatewayType = GatewayType.None
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Gateway](BPMN-Shapes-Images/bpmn-gataway-none.png)


The following table shows the different types of gateways:

| GatewayType | Symbol |Description|
| -------- | -------- |
| None | ![GateWay BPMN Shape](BPMN-Shapes-Images/bpmn-gataway-none.png) ||
| Exclusive | ![Exclusive GateWay BPMN Shape](BPMN-Shapes-Images/Exclusive.png) ||
| Parallel | ![Parallel GateWay BPMN Shape](BPMN-Shapes-Images/Parallel.png) ||
| Inclusive | ![Inclusive GateWay BPMN Shape](BPMN-Shapes-Images/Inclusive.png) ||
| Complex | ![Complex GateWay BPMN Shape](BPMN-Shapes-Images/Complex.png) ||
| EventBased | ![EventBased GateWay BPMNShape](BPMN-Shapes-Images/EventBased.png) ||
| ExclusiveEventBased | ![Exclusive EventBased GateWay BPMN Shape](BPMN-Shapes-Images/EEBased.png) ||
| ParallelEventBased | ![Parallel EventBased GateWay BPMN Shape](BPMN-Shapes-Images/PEBased.png) ||
