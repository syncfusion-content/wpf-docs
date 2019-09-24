---
layout: post
title: Annotation Selection and Resizing | Syncfusion 
description: how to define basic annotations for Node and Connectors
platform: wpf
control: SfDiagram
documentation: ug
---

# How to Select and Resize the Annotation

Basic intersections of selecting and resizing can be applied over annotation. These interactions can be controlled by annotation and its parent node or connector.
To learn about annotation constraints, refer to the [Annotation Constraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.AnnotationConstraints.html).

## Selecting the annotation

Selection of annotation can be enabled by using the `Constraints` property `AnnotationEditorViewModel` class and setting its value to `AnnotationConstraints.Selectable`

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

## Resizing the annotation

Resizing of annotation can be enabled by using the `Constraints` property `AnnotationEditorViewModel` class and setting its value to `AnnotationConstraints.Resizable`

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

