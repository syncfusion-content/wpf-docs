---
layout: post
title: Positioning and Appearance in WPF Diagram control | Syncfusion
description: Learn here all about Positioning and Appearance support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Positioning and Appearance in WPF Diagram (SfDiagram)

Diagram allows you to customize the position and appearance of the annotation efficiently.

## How to position node's annotation 

Annotation can be aligned relative to the node boundaries. It has Margin, Offset, Horizontal, and Vertical alignment settings. It is quite tricky when all four alignments are used together but gives more control over alignments properties of `AnnotationEditorViewModel` class.

Annotations of a node can be positioned using the following properties of `AnnotationEditorViewModel` class.

* `Offset`
* `HorizontalAlignment` and `VerticalAlignment`
* `Margin`

### Offset

The `Offset` property of `AnnotationEditorViewModel` is used to align the annotations based on fractions. 0 represents top-left corner, 1 represents bottom-right corner, and 0.5 represents half of width/height. Default value is (0.5, 0.5).

{% tabs %}
{% highlight xaml %}

<!--Initialize the Node-->
<syncfusion:NodeViewModel UnitHeight="100" UnitWidth="100" 
                          Shape="{StaticResource Rectangle}" 
                          OffsetX="100" OffsetY="100">
    <syncfusion:NodeViewModel.Annotations>
        <!--Initialize the Annotation Collection-->
        <syncfusion:AnnotationCollection>
            <!--Initialize the annotation with offset values-->
            <syncfusion:AnnotationEditorViewModel Content="Offset(0,0)" 
                                                  Offset="0,0"/>
        </syncfusion:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

{% endhighlight %}
{% highlight c# %}
//Initialize the NodeViewModel
NodeViewModel node = new NodeViewModel()
{
    UnitWidth = 100,
    UnitHeight = 100,
    Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
    OffsetX = 100,
    OffsetY = 100,
    //Initialize the Annotation Collection
    Annotations = new ObservableCollection<IAnnotation>()
    {
        //Initialize the annotation with offset values
        new AnnotationEditorViewModel()
        {
            Content = "Offset(0,0)",
            Offset = new Point(0,0),
        },
    }
};            
{% endhighlight %}
{% endtabs %}

| Offset values | Output |
|---|---|
| (0,0) | ![Left](Annotation_images/Offset0,0.PNG) |
| (0,0.5) | ![Left](Annotation_images/Offset0,5.PNG) |
| (0,1) | ![Left](Annotation_images/Offset0,1.PNG) |
| (0.5,0) | ![Left](Annotation_images/Offset5,0.PNG) |
| (0.5,0.5) | ![Left](Annotation_images/Offset5,5.PNG) |
| (0.5,1) | ![Left](Annotation_images/Offset5,1.PNG) |
| (1,0) | ![Left](Annotation_images/Offset1,0.PNG) |
| (1,0.5) | ![Left](Annotation_images/Offset1,5.PNG) |
| (1,1) | ![Left](Annotation_images/Offset1,1.PNG) |

### Horizontal and vertical Alignments

The `HorizontalAlignment` property of `AnnotationEditorViewModel` class is used to align the annotation horizontally. Default value is Center.

The `VerticalAlignment` property of `AnnotationEditorViewModel` class is used to align the annotation vertically. Default value is Center.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with horizontal and vertical alignment properties-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" 
                                          HorizontalAlignment="Left" 
                                          VerticalAlignment="Top" 
                                          Offset="0,0"/>
</syncfusion:AnnotationCollection>

{% endhighlight %}
{% highlight c# %}
//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with horizontal and vertical alignment properties
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        HorizontalAlignment = HorizontalAlignment.Left,
        VerticalAlignment = VerticalAlignment.Top,
        Offset = new Point(0,0),
    }
}             
{% endhighlight %}
{% endtabs %}

| Horizontal Alignment | Vertical Alignment | Output with Offset(0,0) |
|---|---|---|
| Left | Top | ![Left](Annotation_images/Annotation_img3.PNG) |
| Center | Top | ![Center](Annotation_images/Annotation_img4.PNG) |
| Right | Top | ![Right](Annotation_images/Annotation_img5.PNG) |
| Left | Center | ![Left Center](Annotation_images/Annotation_img6.PNG) |
| Center | Center| ![Center](Annotation_images/Annotation_img7.PNG) |
| Right |Center | ![Right](Annotation_images/Annotation_img8.PNG) |
| Left | Bottom | ![Left](Annotation_images/Annotation_img9.PNG) |
| Center | Bottom | ![Center](Annotation_images/Annotation_img10.PNG) |
| Right | Bottom | ![Right](Annotation_images/Annotation_img11.PNG) |

### Margin

`Margin` is an absolute value used to add some blank space in any one of its four sides. The annotations can be displaced with the margin property. The following code example explains how to align an annotation based on its Margin value. Default value is (0,0,0,0).

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with margin property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Margin="0,60,0,0"/>
</syncfusion:AnnotationCollection>
 
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with margin property
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        Margin = new Thickness(0, 60, 0, 0),
    }
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation Margin](Annotation_images/wpf-diagram-annotation-margin.jpg)

## How to position connector's annotation 

Annotations of a connector can be positioned using the following properties of `AnnotationEditorViewModel` class:

* `Alignment`
* `Length`
* `Displacement`
* `Pivot`
* `Margin`

### Alignment

Connector's annotation can be aligned over its segment path using the `Alignment` property of `AnnotationEditorViewModel` class. Default value is Center.

{% tabs %}
{% highlight xaml %}

<!--Initialize the AnnotationCollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with alignment property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Alignment="Source" />
</syncfusion:AnnotationCollection>
 
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with alignment property
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        Alignment = ConnectorAnnotationAlignment.Source,
    }
}

{% endhighlight %}
{% endtabs %}

| Property| Value | Output |
|---|---|---|
| Alignment | Source | ![Source](Annotation_images/ConnectorSource.PNG) |
| | Center | ![Center](Annotation_images/ConnectorCenter.png) |
| | Target | ![Target](Annotation_images/ConnectorTarget.PNG) |

### Length

The `Length` property of annotation is used to align the annotations based on fractions. 0 represents Top-Left corner, 1 represents Bottom-Right corner, and 0.5 represents half of Width/Height. The default value is 0.5d.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with length property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Length="0" />
</syncfusion:AnnotationCollection>
 
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with length property
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        Length = 0,
    }
}

{% endhighlight %}
{% endtabs %}

The following image shows the relationship between the annotation position and Length (fraction values).

![WPF Diagram Annotation Length](Annotation_images/wpf-diagram-annotation-length.jpg)

### Displacement

The `Displacement` property is used to dislocate the annotation by the value given. By default, annotation will be in center of the connector path. When you assign value to the `Displacement` property, annotation will be displaced from its position by displacment value. Default value is 0d.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Annotation ollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with dispalcement property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Displacement="60" />
</syncfusion:AnnotationCollection>
{% endhighlight %}
{% highlight C# %}
//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with dispalcement property
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        Displacement = 60
    }
}
{% endhighlight %}
{% endtabs %}

| Property| Value | Output |
|---|---|---|
| Displacement | 0 | ![Source](Annotation_images/ConnectorCenter.png) |
| | 60 | ![Center](Annotation_images/DisplacmentPositive.PNG) |
| | -60 | ![Target](Annotation_images/DispalcementNegative.PNG) |

### Pivot

Position of an annotation is controlled by using its `Length` property, which represents the distance from connector center. The `Pivot` property is used to align the annotation based on its center point. Default value of the pivot point is (0.5, 0.5), that means center of length.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with pivot property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Pivot="0,0" Length="0" />
</syncfusion:AnnotationCollection>
 
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Initialize the Annotation with pivot property
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        Pivot = new Point(0,0),
        Length = 0,
    }
}

{% endhighlight %}
{% endtabs %}

| Property| Value | Output with 0 Length value |
|---|---|---|
|Pivot | (0.5,0.5) | ![Target](Annotation_images/Pivot5.PNG) |
| | (0,0) | ![Source](Annotation_images/Pivot0,0.png) |
| | (0,1) | ![Center](Annotation_images/Pivot0,1.PNG) |
| | 1,0) | ![Target](Annotation_images/Pivot1,0.PNG) |
| | (1,1) | ![Target](Annotation_images/Pivot1,1.png) |

### Margin

`Margin` is an absolute value used to add some blank space in any one of its four sides. You can displace the annotations with the `Margin` property. Default value is (0,0,0,0).

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation with margin property-->
    <syncfusion:AnnotationEditorViewModel  Content="Annotation" 
                                           Margin="0,0,0,-30" 
                                           RotationReference="Page" />
</syncfusion:AnnotationCollection>                       
                                
{% endhighlight %}
{% highlight c# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content="Annotation",
        //Initialize the margin property
        Margin = new Thickness(0,0,0,-30),
        // Decide to apply orientation or rotation based on segment when annotation is positioned.
        RotationReference = RotationReference.Page,
    }
}
{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation Connector Margin](Annotation_images/wpf-diagram-annotation-connector-margin.png)

## How to set size for annotation

Diagram allows you to set size for annotations by using the `UnitWidth` and `UnitHeight` properties. Default value of UnitWidth and UnitHeight properties are double.NaN. 

{% tabs %}
{% highlight xaml %}

<!--Initialize the AnnotationCollection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation wih size-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" 
                                          UnitWidth="50" UnitHeight="50" />
</syncfusion:AnnotationCollection>                       
                                
{% endhighlight %}
{% highlight c# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content="Annotation",
        //Set the size of annotation
        UnitWidth = 50,
        UnitHeight = 50,
    }
}
{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation Node Size](Annotation_images/wpf-diagram-annotation-node-size.png) &ensp;&ensp;&ensp;&ensp; ![WPF Diagram Annotation Connector Size](Annotation_images/wpf-diagram-annotation-connector-size.png)

N> Size of the annotation is 100% size of the node.

## Wrapping

When text overflows node boundaries, you can control it by using the `WrapText` property. So, it is wrapped into multiple lines. The Wrapping property of annotation defines how the content should be wrapped. Default value is Wrap.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation with wrap text property-->
    <syncfusion:AnnotationEditorViewModel Content="LengthyAnnotation with wrapping text" 
                                          WrapText="Wrap"/>
</syncfusion:AnnotationCollection>                    
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new AnnotationCollection()
{
    new AnnotationEditorViewModel()
    {
        Content = "LengthyAnnotation with wrapping text",
        //Define the value for wrap text property
        WrapText=TextWrapping.Wrap,
    }
}

{% endhighlight %}
{% endtabs %}

| Values | Description | Node |
|---|---|---|---|
| NoWrap | Text will not be wrapped. | ![NoWrap](Annotation_images/Annotation_img18.png) |
| Wrap | Text-wrapping occurs when the text overflows beyond the available annotation container width. | ![Wrap](Annotation_images/Annotation_img19.png) |
| WrapWithOverflow | Text-wrapping occurs when the text overflows beyond the available annotation container width. However, the text may overflow beyond the annotation container width in the case of a very long word. | ![Overflow](Annotation_images/annotation_img20.png) |

## How to change the appearance of annotation

Default appearance of the annotations can be customized by using the `EditTemplate` and `ViewTemplate` properties. ViewTemplate is used to control the appearance of the annotation when it is in non-editing stage. EditTemplate is used to control the appearance of the annotation while it is in editing.

{% tabs %}
{% highlight xaml %}

<!--Template overriding for view template-->
<DataTemplate x:Key="viewTemplate">
    <TextBlock Text="{Binding Path=Content, Mode=TwoWay}" 
               FontStyle="Italic" FontSize="12" 
               FontFamily="TimesNewRomen" 
               TextDecorations="Underline" 
               FontWeight="Bold" 
               Foreground="Black"/>
</DataTemplate>

<!--Template overriding for edit template-->
<DataTemplate x:Key="editTemplate">
    <TextBox Text="{Binding Path=Content, Mode=TwoWay}" 
             FontStyle="Oblique" FontSize="12" 
             FontFamily="TimesNewRomen" 
             FontWeight="Bold" Foreground="Red"/>
</DataTemplate>

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with view and edit templates-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" 
                                          ViewTemplate="{StaticResource viewTemplate}" 
                                          EditTemplate="{StaticResource editTemplate}"/>
</syncfusion:AnnotationCollection>

{% endhighlight %}
{% highlight C# %}

//Initialize the AnnotationCollection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        //Defines the view and edit templates
        ViewTemplate = App.Current.Resources["viewTemplate"] as DataTemplate,
        EditTemplate  = App.Current.Resources["editTemplate"] as DataTemplate,
    }
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation Appearance](Annotation_images/wpf-diagram-annotation-appearance.PNG) &ensp;&ensp;&ensp;&ensp;&ensp; ![WPF Diagram Annotation EditTemplate](Annotation_images/wpf-diagram-annotation-edittemplate.png)

Also, diagram have `TextAnnotationViewModel` class to customize the appearance of the annotation directly instead of overriding view and edit templates of the annotation. This class customization will be applied for both view and edit mode of annotation.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Text Annotation View Model class-->
    <syncfusion:TextAnnotationViewModel Text="Annotation" FontStyle="Italic" 
                                        FontSize="12" FontFamily="TimesNewRomen" 
                                        TextDecorations="Underline" 
                                        FontWeight="Bold" Foreground="Black"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    //Intialize the Text Annotation View Model class
    new TextAnnotationViewModel()
    {
        Text = "Annotation",
        FontStyle = FontStyles.Italic,
        FontSize = 12,
        FontFamily = new FontFamily("TimesNewRomen"),
        TextDecorations = TextDecorations.Underline,
        FontWeight = FontWeights.Bold,
        Foreground = new SolidColorBrush(Colors.Black),
    }
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram TextAnnotationViewModel](Annotation_images/wpf-diagram-annotation-appearance.PNG) &ensp;&ensp;&ensp;&ensp;&ensp; ![WPF Diagram Annotation TextEditor](Annotation_images/wpf-diagram-annotation-text-editor.png)

### How to change the editing mode

Diagram allows you to show the annotation in view or edit mode while loading the diagram elements by using the `Mode` property of `AnnotationEditorViewModel` class. Default value is View.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the Annotation with edit mode property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" Mode="Edit"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        //Initialize the editing mode property
        Mode = ContentEditorMode.Edit,
    }
}

{% endhighlight %}
{% endtabs %}

![WPF Diagram Annotation ContentEditMode](Annotation_images/wpf-diagram-content-edit-mode.PNG)

N> Edit mode will be applied to a single element at a time.

### How to edit the annotation

Annotation will be in editing state when you double click the node or annotation. Annotation will be selected when you single click the annotation if selectable constraints are enabled. 

Also, the `ReadOnly` property of `AnnotationEditorViewModel` class allows you to disable the editing option of annotation.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Annotation Collection-->
<syncfusion:AnnotationCollection>
    <!--Initialize the annotation with read only property-->
    <syncfusion:AnnotationEditorViewModel Content="Annotation" ReadOnly="True"/>
</syncfusion:AnnotationCollection>
                                
{% endhighlight %}
{% highlight C# %}

//Initialize the Annotation Collection
Annotations = new ObservableCollection<IAnnotation>()
{
    new AnnotationEditorViewModel()
    {
        Content = "Annotation",
        //Initialize the ReadOnly property
        ReadOnly = true,
    }
}

{% endhighlight %}
{% endtabs %}
