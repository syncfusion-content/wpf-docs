---
layout: post
title: TextAnnotation in WPF Diagram control | Syncfusion
description: Learn here all about TextAnnotation support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# TextAnnotation in WPF Diagram (SfDiagram)

* A [Text Annotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#TextAnnotation) points at or references the another BPMN shape, which we call the [`TextAnnotationTarget`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_TextAnnotationTarget) of the `TextAnnotation`. When a target shape is moved, copied, or deleted, any Text Annotations attached to the shape will be moved, copied, or deleted too.  Thus, the Text Annotations stay with their target shapes though you can reposition the `TextAnnotation` to any offset from its target. The `TextAnnotationTarget` property of the [`BpmnNodeViewModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html) is used to connect an annotation element to the `BpmnNodeViewModel`.

* The annotation element can be switched from a BPMN node to another BPMN node simply by dragging the source end of the annotation connector into the other BPMN node.

* By default, the `TextAnnotation` shape having a connection.

* The [`TextAnnotationDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_TextAnnotationDirection) property is used to set the shape direction of the text annotation.

* To set the size for text annotation, use the [`UnitWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_UnitWidth) and [`UnitHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_UnitHeight) properties.

* The [`OffsetX`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_OffsetX) and [`OffsetY`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html#Syncfusion_UI_Xaml_Diagram_NodeViewModel_OffsetY) property is used to set the distance between the BPMN node and the `TextAnnotation`.

* The `TextAnnotation` element can be moved (if their have connected with any BPMN Node) while dragging the BPMN node.

The following code example represents how to create a Text Annotation.

{% tabs %}
{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

 //Initialize the BpmnNodeViewModel with the type as TextAnnotation.
BpmnNodeViewModel textannotation = new BpmnNodeViewModel()
{
   OffsetX = 300,
   OffsetY = 100,
   UnitWidth = 100,
   UnitHeight = 70,
   Type = BpmnShapeType.TextAnnotation,
   TextAnnotationDirection = TextAnnotationDirection.Left,
   Annotations = new ObservableCollection<IAnnotation>()
   {
     new AnnotationEditorViewModel()
     {
        Content="Text"
     }
   }
};

// Add the node into the Node's collection.
(diagram.Nodes as NodeCollection).Add(textannotation);

{% endhighlight %}
{%  endtabs %}

![BPMN Text Annotation](BPMN-Shapes-Images/bpmn-textannotation.png)

The following code example represents how to create a Text Annotation and make a connection between the `Activity` and `TextAnnotation` shape.

{% tabs %}
{% highlight c# %}

//Initialize the diagram.
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel.
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
   OffsetX = 150,
   OffsetY = 250,
   UnitWidth = 100,
   UnitHeight = 100,
   Type = BpmnShapeType.Activity,
};

 //Initialize the BpmnNodeViewModel with the type as TextAnnotation.
BpmnNodeViewModel textannotation = new BpmnNodeViewModel()
{
   OffsetX = 300,
   OffsetY = 100,
   UnitWidth = 100,
   UnitHeight = 70,
   Type = BpmnShapeType.TextAnnotation,
   TextAnnotationTarget = node,
   Annotations = new ObservableCollection<IAnnotation>()
   {
     new AnnotationEditorViewModel()
     {
        Content="Text"
     }
   }
};

// Add the node into the Node's collection.
(diagram.Nodes as NodeCollection).Add(node);
(diagram.Nodes as NodeCollection).Add(textannotation);

{% endhighlight %}
{%  endtabs %}

![BPMN Text Annotation](BPMN-Shapes-Images/bpmn-text-annotation.png)

## How to create a connection between the TextAnnotation to BPMNNode

Drag and drop any bpmn shapes from the stencil to diagram and make a connection between the BPMN Node and `TextAnnotation`.


The following image shows how to drag a symbol from the palette and create a connection between the `TextAnnotation` to `BPMNNode` with interaction.

![BPMN Text Annotation](BPMN-Shapes-Images/textannotationbpmn.gif)
