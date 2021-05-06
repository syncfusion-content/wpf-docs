---
layout: post
title: Ink Annotation in WPF Pdf Viewer control | Syncfusion
description: Learn about Ink Annotation support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Ink Annotation in WPF Pdf Viewer

PDF viewer WPF allows the user to include ink annotation in the PDF document and provides options to edit or remove the existing ink annotation in the PDF document. 

The following code shows how to switch to ink annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Ink;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Ink
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the ink annotation being included in the PDF Document.

 ![Inclusion of ink](Annotation-images\Ink-Annotation-1.png)

## How to set the color of the ink annotation?

The color of the ink annotation included can be customized at the time of inclusion itself. The following code shows how to set color of the ink annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.InkAnnotationSettings.InkColor = Colors.Green;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.InkAnnotationSettings.InkColor = Colors.Green
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the opacity of the ink annotation?

The opacity of the ink annotation can be customized at the time of inclusion itself. The following code shows how to set opacity value of the ink annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.InkAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.InkAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the thickness of the ink annotation?

The thickness of the ink annotation can be customized at the time of inclusion itself. The following code shows how to set thickness of the ink annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.InkAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.InkAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the ink annotation?

The author and subject fields of the ink annotation can be added for the ink annotation to be added to the PDF document. The follow code shows how to set the author and subject field of the ink annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.InkAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.InkAnnotationSettings.Subject = "Ink annotation";
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.InkAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.InkAnnotationSettings.Subject = "Ink annotation"
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing ink annotations

Ink annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing ink annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

### Open Pop-up notes

We can add notes to the ink annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected ink annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

![Popup note](Annotation-images\Ink-Annotation-2.png)

### Properties

Selecting properties from the context menu will display the Ink Properties window, which would consist of two tabs

*	Appearance
*	General 

### Appearance tab

The color, opacity and thickness of the ink annotation can be edited using Appearance tab of Ink Properties window.

#### Editing the thickness of the ink annotation

Modifying the value in the NumericUpDown control in the Appearance tab of ink annotation properties window will allow us to modify the thickness of the selected ink annotation.

The following image illustrates how to change the thickness of the ink annotation.

![Ink thickness](Annotation-images\Ink-Annotation-3.png)

The following image illustrates the change in thickness of the selected ink annotation.

![Modified ink thickness](Annotation-images\Ink-Annotation-4.png)

#### Editing color of the annotation

The color of the selected ink annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the ink annotation.

The following image illustrates how to change the color of the ink annotation included.

![Ink color](Annotation-images\Ink-Annotation-5.png)

The following image illustrates the change in the color of the ink annotation.

![Modified ink color](Annotation-images\Ink-Annotation-6.png)

#### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected ink annotation. You can also modify the opacity of the selected ink annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the ink annotation.

![Ink opacity](Annotation-images\Ink-Annotation-7.png)

The following image illustrates the change in the opacity of the ink annotation.

![Modified ink opacity](Annotation-images\Ink-Annotation-8.png)

### General tab

We can add or edit the Author and Subject of the ink annotation using General tab of the Ink Properties window.

The following image illustrates the change in Author and Subject of the included Ink annotation.

![General details](Annotation-images\Ink-Annotation-9.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![Ink deletion](Annotation-images\Ink-Annotation-10.png)

### Erase ink annotation

The Eraser tool in the toolbar helps you to erase (remove) the unwanted parts in an ink annotation. You can enable the eraser tool by simply clicking the tool.

![Erase ink annotation](Annotation-images\Ink-Eraser.png)

After the tool is enabled, you can erase the unwanted parts by holding the mouse button down and drag over the parts of an ink annotation.

The Eraser tool can also be enabled programmatically using the [AnnotationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationMode) property of the [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) and [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). Please refer to the following code.

{% tabs %}
{% highlight C# %}

pdfViewer.AnnotationMode = PdfViewerAnnotationMode.InkEraser;

{% endhighlight %}
{% endtabs %}

N> This tool can be used to erase the ink annotation only and not applicable for other annotations.

### Keyboard shortcuts

The below keyboard shortcuts are available to customize the annotation in the PDF document.

*	Delete key: Deletes the selected annotation from the PDF document.
*	Ctrl + Z: Performs undo functionality for recently performed operations.
*	Ctrl + Y: Performs redo functionality for recently performed operations.
*	Esc key: To exit from the annotation mode.

## Events

The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) notifies through events, when [AnnotationChangedAction](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) such us adding, deleting, select, deselect, moving and resizing made in annotations. It also provides the annotations common information such as page index, bounds and action type performed in respective annotation. 

### InkAnnotationChanged Event

The [InkAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_InkAnnotationChanged) event occurs when the [Action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Action) performed in ink annotation. It provides the common information and annotation properties which are available in `Settings` through the [InkAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.InkAnnotationChangedEventArgs.html). The user can modify the annotation properties through [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.InkAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_InkAnnotationChangedEventArgs_Settings).

The following code shows how to write the `InkAnnotationChanged` event in `PdfViewerControl`

{% tabs %}
{% highlight C# %}

private void PdfViewer_InkAnnotationChanged(object sender, InkAnnotationChangedEventArgs e)
{
    //COMMON PROPERTIES
    //AnnotationChangedAction to identify action performed for annotation 
    AnnotationChangedAction action = e.Action;

    //Page index in which this shape annotation was modified 
    int pageNumber = e.PageNumber;

    //Annotation's previous position and current position 
    RectangleF currentBound = e.NewBounds;
    RectangleF previousBound = e.NewBounds;

    PdfViewerInkSettings settings = e.Settings;
    //Annotation's properties which can be modify 
    string author = settings.Author;
    string subject = settings.Subject;
    string Text = settings.Text;
    float opacity = settings.Opacity;
    System.Windows.Media.Color color = settings.InkColor;
    double thickness = settings.Thickness;
}
{% endhighlight %}
{% endtabs %}
