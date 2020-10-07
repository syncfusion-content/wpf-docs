---
layout: post
title: Visualize graphical object using BPMN Shapes | Syncfusion 
description: How to define diagram BPMN shapes and how to graphically notate the internal business procedure and how to customize their appearance?
platform: wpf
control: SfDiagram
documentation: ug
---

# BPMN Shapes and its customization

BPMN(Business Process Model and Notation) shapes are used to represent the internal business procedure in a graphical notation and enable you to communicate the procedures in a standard manner. To create a [BpmnNodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html) shape,in the [Type](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_Type) property, type should be set to “Activity” and its shape should be set as any one of the built-in shapes.

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

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create BPMNShapes](BPMN-Shapes-Images/BpmnShape_Default.png)

>Note : The default value for the property [`Type`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_Type) is BpmnShapeType.Activity.

The list of BPMN shapes are as follows:

| Shape | Image |
| -------- | -------- |
| Event | ![Event Shape](BPMN-Shapes-Images/Event.png) |
| Gateway | ![Gateway Shape](BPMN-Shapes-Images/Gateway.png) |
| Task | ![Task Shape](BPMN-Shapes-Images/Task.png) |
| Message | ![Message Shape](BPMN-Shapes-Images/Message.png) |
| DataSource | ![Datasource Shape](BPMN-Shapes-Images/Datasource.png) |
| DataObject | ![Dataobject Shape](BPMN-Shapes-Images/Dataobject.png) |
| TextAnnotation | ![TextAnnotation Shape](BPMN-Shapes-Images/TextAnnotation.png) |
| Group | ![Group Shape](BPMN-Shapes-Images/Group.png) |
| Expandedsubprocess | ![Expandedsubprocess Shape](BPMN-Shapes-Images/Expandedsubprocess.png) |
| Sequenceflow | ![Sequenceflow Shape](BPMN-Shapes-Images/Sequenceflow.png) |
| DefaultSequenceflow | ![DefaultSequenceflow Shape](BPMN-Shapes-Images/DefaultSequenceflow.png) |
| ConditionalSequenceflow | ![ConditionalSequenceflow Shape](BPMN-Shapes-Images/ConditionalSequenceflow.png) |
| Association | ![Association Shape](BPMN-Shapes-Images/Association.png) |
| DirectionalAssociation | ![DirectionalAssociation Shape](BPMN-Shapes-Images/DirectionalAssociation.png) |
| BiDirectionalAssociation | ![BiDirectionalAssociation Shape](BPMN-Shapes-Images/BiDirectionalAssociation.png) |
| MessageFlow | ![MessageFlow Shape](BPMN-Shapes-Images/Messageflow.png) |
| InitiatingMessageflow | ![InitiatingMessageflow Shape](BPMN-Shapes-Images/InitiatingMessageflow.png) |
| NonInitiatingMessageflow | ![NonInitiatingMessageflow Shape](BPMN-Shapes-Images/NonInitiatingMessageflow.png) |

Please find the BPMN Editor sample as follows.

[View BPMN Editor sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/BPMNEditor/Sample)