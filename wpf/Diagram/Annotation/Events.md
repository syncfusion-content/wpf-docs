---
layout: post
title: Events in WPF Diagram control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Events in WPF Diagram (SfDiagram)

The [AnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationChangedEventArgs.html) event will notify the annotation related actions and value changes. The `AnnotationChangedEventArgs` class is used to get or set the entire annotation related properties and their values.  

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

{% seealso %}

[How to add or remove annotation constraints](/wpf/sfdiagram/constraints#annotation-constraints)

[How to localize the annotations](/wpf/sfdiagram/localization)

{% endseealso %}
