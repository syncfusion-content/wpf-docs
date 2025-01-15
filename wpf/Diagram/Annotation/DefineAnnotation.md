---
layout: post
title: Annotation in WPF Diagram control | Syncfusion
description: Learn here all about Annotation support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Annotation in WPF Diagram (SfDiagram)

Annotation is a block of text that can be displayed over a node or connector. Annotation is used to textually represent an object with a string that can be edited at run time. Multiple annotations can be added to a node or connector.

## Define annotation

An annotation can be added to a node or connector by defining the annotation object and adding that to the annotation collection of the node or connector. The [`Content`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationEditorViewModel.html#Syncfusion_UI_Xaml_Diagram_AnnotationEditorViewModel_Content) property of [`AnnotationEditorViewModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.AnnotationEditorViewModel.html) class defines the text to be displayed. The following code explains how to create an annotation.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the node view model-->
            <syncfusion:NodeViewModel UnitWidth="100" UnitHeight="100" 
                                      OffsetX="100" OffsetY="100" 
                                      Shape="{StaticResource Rectangle}" >
                <!--Initialize the annotations-->
                <syncfusion:NodeViewModel.Annotations>
                    <!--Initialize the AnnotationCollection-->
                    <syncfusion:AnnotationCollection>
                        <!--Initialize the Annotation editor view model-->
                        <syncfusion:AnnotationEditorViewModel Content="Annotation"/>
                    </syncfusion:AnnotationCollection>
                </syncfusion:NodeViewModel.Annotations>
            </syncfusion:NodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
    <!--Initialize the Connector-->
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--Initialize the Connector view model-->
            <syncfusion:ConnectorViewModel SourcePoint="200,50" TargetPoint="300,150">
                <syncfusion:ConnectorViewModel.Annotations>
                    <!--Initialize the AnnotationCollection-->
                    <syncfusion:AnnotationCollection>
                        <!--Initialize the Annotation editor view model-->
                        <syncfusion:AnnotationEditorViewModel Content="Annotation"/>
                    </syncfusion:AnnotationCollection>
                </syncfusion:ConnectorViewModel.Annotations>
            </syncfusion:ConnectorViewModel>
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the Node View Model
NodeViewModel node = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 100,
    OffsetX = 100,
    OffsetY = 100,
    Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
    //Initialize the AnnotationCollection
    Annotations = new ObservableCollection<IAnnotation>()
    {
        //Initialize the Annotation with content
        new AnnotationEditorViewModel()
        {
            Content="Annotation"
        }
    }
};

//Initialize the Connector View Model
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(200, 50),
    TargetPoint = new Point(300, 150),
    //Initialize the AnnotationCollection
    Annotations = new ObservableCollection<IAnnotation>()
    {
        //Initialize the Annotation with content
        new AnnotationEditorViewModel()
        {
            Content="Annotation"
        }
    }
};

// Add the node into Node's collection
(diagram.Nodes as NodeCollection).Add(node);

// Add the Connector into connector's collection
(diagram.Connectors as ConnectorCollection).Add(connector);
{% endhighlight %}
{%  endtabs %}

![Create Annotation](Annotation_images/Create_Annotation.jpg)

## Multiple Annotations

You can add any number of annotations to a node or connector.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the multiple annotation-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation"/>
    <syncfusion:AnnotationEditorViewModel Content="Annotation"/>
    <syncfusion:AnnotationEditorViewModel Content="Annotation"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the multiple annotation
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
    },
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
    },
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
    },
}

{% endhighlight %}
{% endtabs %}

![Multiple Annotations](Annotation_images/annotation_img21.png) &ensp;&ensp;&ensp;&ensp;&ensp; ![Multiple Annotations](Annotation_images/MultipleAnnotationConnector.png)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Annotations/MultipleAnnotation).

##  See Also

[How to add annotations to nodes/connectors and its customization?](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Annotations)

[How to add image annotations to a Node?](https://support.syncfusion.com/kb/article/6078/how-to-add-image-annotations-to-a-node-in-wpf-diagram-sfdiagram-control)

[How to restrict annotation editing by double-clicking the node or connector?](https://support.syncfusion.com/kb/article/8539/how-to-restrict-annotation-editing-by-double-clicking-the-node-or-connector-in-wpf-diagram)

[How to programmatically Show/Hide the Annotations of node and connector?](https://support.syncfusion.com/kb/article/6281/how-to-programmatically-showhide-annotations-in-wpf-diagram-)

[How to set font properties for newly added items Annotations in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18670/how-to-set-font-properties-for-newly-added-items-annotations-in-wpf-diagram-sfdiagram)

[How to highlight the node when selecting an annotation of the node and vice versa in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18245/how-to-highlight-the-node-when-selecting-an-annotation-of-the-node-and-vice-versa-in-the-wpf-diagram-sfdiagram)

[How to update text formatting properties of an Annotation in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18407/how-to-update-text-formatting-properties-of-an-annotation-in-wpf-diagram-sfdiagram)