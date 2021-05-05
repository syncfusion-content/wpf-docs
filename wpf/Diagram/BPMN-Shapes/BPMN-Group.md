---
layout: post
title: Group in WPF Diagram control | Syncfusion
description: Learn here all about Group support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Group in WPF Diagram (SfDiagram)

Groups organize tasks or processes that have significance in the overall process.
A group may control the flow of a process and describe shared goals. A group is denoted by dashes and dots.

## Create BPMN Group

To create a [BpmnGroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnGroupViewModel.html), you have to define the BpmnGroupViewModel object and add that to groups collection of the Diagram.

The following code example explains how to create a BPMN group.

{% tabs %}
{% highlight xaml %}
 <!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram">
   <syncfusion:SfDiagram.Groups>
    <!--Initialize the Group Collection-->
    <syncfusion:GroupCollection>
    <!--Initialize the BpmnGroupViewModel-->
      <syncfusion:BpmnGroupViewModel OffsetX="300" OffsetY="300" UnitHeight="300" UnitWidth="250" ></syncfusion:BpmnGroupViewModel>
     </syncfusion:GroupCollection>
    </syncfusion:SfDiagram.Groups>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnGroupViewModel.
BpmnGroupViewModel group = new BpmnGroupViewModel()
{
  OffsetX = 300,
  OffsetY = 300,
  UnitWidth = 300,
  UnitHeight = 250,
 };
 // Add the group into the Group's collection.
(Diagram.Groups as GroupCollection).Add(group);

{% endhighlight %}
{%  endtabs %}

![BPMN Group](BPMN-Shapes-Images/Bpmn-Group.png)

## Add BPMNNode into BPMNGroup by Programmatically

To add a [BpmnNodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html) into the BPMNGroup, you have to define the BpmnNodeViewModel object and add that to the nodes collection of the BPMNGroup.

The following code example explains how to create a BPMN group.

{% tabs %}
{% highlight xaml %}
 <!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram">
   <syncfusion:SfDiagram.Groups>
    <!--Initialize the Group Collection-->
    <syncfusion:GroupCollection>
    <!--Initialize the BpmnGroupViewModel-->
       <syncfusion:BpmnGroupViewModel OffsetX="300" OffsetY="300" UnitHeight="300" UnitWidth="300" >
       <syncfusion:BpmnGroupViewModel.Nodes>
         <syncfusion:NodeCollection>
           <syncfusion:BpmnNodeViewModel ID="node1" OffsetX="220" OffsetY="200" UnitHeight="70" UnitWidth="100"></syncfusion:BpmnNodeViewModel>
           <syncfusion:BpmnNodeViewModel ID="node2" OffsetX="380" OffsetY="400" UnitHeight="70" UnitWidth="100"></syncfusion:BpmnNodeViewModel>
         </syncfusion:NodeCollection>
        </syncfusion:BpmnGroupViewModel.Nodes>
        <syncfusion:BpmnGroupViewModel.Connectors>
          <syncfusion:ConnectorCollection>
           <syncfusion:BpmnFlowViewModel SourceNodeID="node1" TargetNodeID="node2"></syncfusion:BpmnFlowViewModel>
          </syncfusion:ConnectorCollection>
        </syncfusion:BpmnGroupViewModel.Connectors>
        </syncfusion:BpmnGroupViewModel>
     </syncfusion:GroupCollection>
    </syncfusion:SfDiagram.Groups>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnGroupViewModel.
BpmnGroupViewModel group = new BpmnGroupViewModel()
{
  OffsetX = 300,
  OffsetY = 300,
  UnitWidth = 300,
  UnitHeight = 300,
 };
 //Initialize the BpmnNodeViewModel.
 BpmnNodeViewModel node1 = new BpmnNodeViewModel()
 {
    OffsetX = 220,
    OffsetY = 200,
    UnitWidth = 100,
    UnitHeight = 70,
    Type = BpmnShapeType.Activity,
 };
 //Initialize the BpmnNodeViewModel.
 BpmnNodeViewModel node2 = new BpmnNodeViewModel()
 {
    OffsetX = 380,
    OffsetY = 400,
    UnitWidth = 100,
    UnitHeight = 70,
    Type = BpmnShapeType.Activity,
 };
 //Initialize the BpmnFlowViewModel.
 BpmnFlowViewModel flow = new BpmnFlowViewModel()
 {
    SourceNode = node1,
    TargetNode = node2,
 };
 // Add the node into the Node's collection.
(group.Nodes as NodeCollection).Add(node1);
// Add the node into the Node's collection.
(group.Nodes as NodeCollection).Add(node2);
// Add the connector into the Connector's collection.
(group.Connectors as ConnectorCollection).Add(flow);
 // Add the group into the Group's collection.
(Diagram.Groups as GroupCollection).Add(group);

{% endhighlight %}
{%  endtabs %}

![BPMN Group](BPMN-Shapes-Images/Bpmn-Group-Child.png)

## Add Group from stencil

Groups can be predefined and added to the stencil and can be dropped into the diagram when needed. For more information about adding the nodes from Stencil, refer to the [Stencil](/wpf/sfdiagram/stencil "Stencil") and [BPMN-Shapes-Palette](/wpf/sfdiagram/BPMN-Shapes/BPMN-Shapes-Palette "BPMN-Shapes-Palette").

## Add BPMN Nodes/Groups into BPMNGroup at runtime
You can add the BPMN Nodes or Groups into BPMNGroup at runtime in two ways.

  1. Drag and drop the BPMN Nodes or Groups from stencil to BPMN Group 
  2. Drag and drop the BPMN Nodes or Groups from diagram to BPMN Group.

 * While resize or drag the child Node, if the child node bounds within the group bounds, the group size will be updated along with that.

 The following image shows how to add BPMNNode into the BPMNGroup at runtime.

![BPMNGroup from diagram](BPMN-Shapes-Images/BPMN-GroupElement.gif)
