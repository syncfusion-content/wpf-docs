---
layout: post
title: Annotation Dragging | Syncfusion 
description: how to drag the annotations of nodes and Connectors and how to customize the dragging behaviour of annotations.
platform: wpf
control: SfDiagram
documentation: ug
---

# How to drag the annotation

Dragging process can be applied over annotation and dragging can be controlled by the annotation and its parent node or connector.
To learn about annotation constraints, refer to the [Annotation Constraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationConstraints.html).

## Dragging the annotation

Dragging of annotation can be enabled by using the [`Constraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationEditorViewModel.html#Syncfusion_UI_Xaml_Diagram_AnnotationEditorViewModel_Constraints) property of [`AnnotationEditorViewModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationEditorViewModel.html) class and setting its value as `AnnotationConstraints.Draggable`.

{% tabs %}

{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation with draggable constraint-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Constraints="Draggable"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        //Initialize the constraint as draggable
        Constraints = AnnotationConstraints.Draggable 
    }
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation Dragging](Annotation_images/wpf-diagram-annotation-dragging.gif)

## Nudging an annotation

Diagram allows users to nudge annotations by one pixel in a specific direction using the arrow keys. By enabling the `AnnotationConstraints.Selectable` and `AnnotationConstraints.Draggable` through the `Constraints` property in the `AnnotationEditorViewModel` class, users can interact with annotations and adjust their positions incrementally. Additionally, holding down the shift key while pressing the arrow key will move the annotation ten pixels instead of one.

![WPF Diagram Annotation Nudging](Annotation_images/wpf-diagram-annotation-nudging.gif)

## How to restrict the dragging area

Diagram allows you to specify the amount of dragging area around the annotation by enabling the `Constraints` as `AnnotationConstraints.DragLimit` and dragging area can be specified by using the [`DragLimit`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationEditorViewModel.html#Syncfusion_UI_Xaml_Diagram_AnnotationEditorViewModel_DragLimit) property. You cannot drag the annotation behind this drag limit value. Default value is (10, 10, 10, 10).

{% tabs %}
{% highlight xaml %}

<!--Initialize the AnnotationCollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation with drag limit value-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" 
                                          Constraints="Draggable,DragLimit" 
                                          DragLimit="40,80,40,40"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        //Initialize the drag limit constraint
        Constraints = AnnotationConstraints.Draggable | AnnotationConstraints.DragLimit,
        //Initialize the drag limit value
        DragLimit = new Thickness(40,80,40,40),
    }
}

{% endhighlight %}
{% endtabs %}

| Property | Value | Output | Keyboard Output |
|---|---|---|---| --- |
| DragLimit | (10,10,10,10) | ![WPF Diagram Annotation NoWrap](Annotation_images/wpf-diagram-annotation-drag-limit-default.gif) | ![WPF Diagram Annotation Nudging](Annotation_images/wpf-diagram-annotation-nudging-draglimit-default.gif) |
| |(40,80,40,40) | ![WPF Diagram Annotation Wrap](Annotation_images/wpf-diagram-annotation-custom-drag-limit.gif) | ![WPF Diagram Annotation Nudging Custom](Annotation_images/wpf-diagram-annotation-nudging-draglimit-custom.gif) |

