---
layout: post
title: Annotation Selection and Resizing | Syncfusion 
description: how to define basic annotations for Node and Connectors
platform: wpf
control: SfDiagram
documentation: ug
---

# How to select and resize the annotation

Basic intersections of selection and Resizing can be applied over annotation. These interactions can be controlled by Annotation and it's Parent (Node/Connector).
To explore about Annotation Constraints, please refer to the [Annotation Constraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.AnnotationConstraints.html).

## Selecting the Annotation

Selection of annotation can be enabled by using `Constraints` property `AnnotationEditorViewModel` class and setting its value as `AnnotationConstraints.Selectable`

{% tabs %}

{% highlight xaml %}

<!--Initialize the AnnotationCollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the AnnotationEditorViewModel-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Constraints="Selectable"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}

{% highlight C# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
    {
        //Initialize the Annotation selectable constraint
        new AnnotationEditorViewModel()
            {
                Content = "Annotation",
                Constraints = AnnotationConstraints.Selectable 
            }
    }

{% endhighlight %}
{% endtabs %}

![Interaction](Annotation_images/AnnotationSelectable.png)

## Resizing the Annotation

Resizing of annotation can be enabled by using `Constraints` property `AnnotationEditorViewModel` class and setting its value as `AnnotationConstraints.Resizable`

{% tabs %}
{% highlight xaml %}

<!--Initialize the AnnotationCollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the AnnotationEditorViewModel-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Constraints="Selectable,Resizable"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
    {
        //Initialize the Annotation Rotatable constraint
        new AnnotationEditorViewModel()
            {
                Content = "Annotation",
                Constraints = AnnotationConstraints.Selectable | AnnotationConstraints.Resizable
            }
    }

{% endhighlight %}
{% endtabs %}

![Interaction](Annotation_images/AnnotationResizing.gif)

