---
layout: post
title: Events in WPF Diagram control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Events in WPF Diagram (SfDiagram)
## Annotation Changed Event
The [AnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_AnnotationChanged) event will notify the annotation related actions and value changes. The [AnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationChangedEventArgs.html) class is used to get or set the entire annotation related properties and their values.  

{% tabs %}
{% highlight C# %}

//Register the AnnotationChanged event
(diagram.Info as IGraphInfo).AnnotationChanged += Diagram_AnnotationChanged;

//Method to show message box when annotation is changed
private void Diagram_AnnotationChanged(object sender, ChangeEventArgs<object, AnnotationChangedEventArgs> args)
{
    //When annotation is resized
    if (args.NewValue.AnnotationInteractionState == AnnotationInteractionState.Resized)
    {
        MessageBox.Show("Annotation has been resized!");
    }

    //When annotation is resized
    if (args.NewValue.AnnotationInteractionState == AnnotationInteractionState.Rotated)
    {
        MessageBox.Show("Annotation has been rotated!");
    }

    //When annotation is resized
    if (args.NewValue.AnnotationInteractionState == AnnotationInteractionState.Edited)
    {
        MessageBox.Show("Annotation has been edited!");
    }
}

{% endhighlight %}
{% endtabs %}

## Selection Events:

* The [ItemSelectingEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemSelectingEvent) and [ItemSelectedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemSelectedEvent) notify you when an annotation is selected. The args parameter, derived from the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html) classes, provides either the AnnotationEditorViewModel or TextAnnotationViewModel.

* The [ItemUnSelectingEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemUnSelectingEvent) and [ItemUnSelectedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemUnSelectedEvent) notify you when an annotation is unselected. The args parameter, also derived from the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html) classes, provides either the AnnotationEditorViewModel or TextAnnotationViewModel.

## See Also

[How to add or remove annotation constraints?](/wpf/sfdiagram/constraints#annotation-constraints)

[How to localize the annotations?](/wpf/sfdiagram/localization)

[How to restrict annotation editing by double-clicking the node or connector?](https://support.syncfusion.com/kb/article/8539/how-to-restrict-annotation-editing-by-double-clicking-the-node-or-connector-in-wpf-diagram)