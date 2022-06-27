---
layout: post
title: Squiggly text in PDF files using WPF PDF Viewer | Syncfusion
description: Learn about squiggly annotation support in Syncfusion WPF PDF Viewer control, and the manipulations.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Squiggly text in PDF files using WPF PDF Viewer

The WPF PDF Viewer allows the user to squiggly text in PDF files and provides options to edit or remove the existing squigglies. The squiggly inclusion mode can be enabled via the toolbar UI or the API. Once the squiggly inclusion mode is activated, you can squiggly the required text by selecting it. To select the text, hold down the left mouse button and drag the mouse pointer over the text.

To enable the mode from UI, click the below icon in the default toolbar of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

![Squiggly icon in the WPF PDF Viewer toolbar](Annotation-images\squiggly-icon.png)

N> From version 19.4.0.48, we have updated our default text extraction engine to PDFium for extracting text information from PDF documents. Based on the text information, we create text markup annotations in the PDF documents. Please refer to the [link](https://help.syncfusion.com/wpf/pdf-viewer/text-extraction-engines) for more details.

If you are using [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control, or your own toolbar, or if you want enable the mode programmatically, change the [AnnotationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationMode) property of PDF Viewer to **Squiggly**, as shown in the below code example.

{% tabs %}
{% highlight C# %}

private void EnableSquigglyInclusionMode()
{
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Squiggly;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub EnableSquigglyInclusionMode()
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Squiggly
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the squiggled text in the PDF file.

 ![squiggly annotation](Annotation-images\Squiggly-Annotation-1.jpg)

## Change the default color of the squiggly annotation

The squiggly color is red by default. However, you can change the default color of the squiggly programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultSquigglyColor()
{
    pdfViewer.SquigglyAnnotationSettings.Color = System.Windows.Media.Colors.Blue;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultSquigglyColor()
    pdfviewer.SquigglyAnnotationSettings.Color = System.Windows.Media.Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default opacity of the squiggly annotation

The squiggly opacity value is 1 by default. However, you can change the default opacity of the squiggly programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultSquigglyOpacity()
{
    pdfViewer.SquigglyAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultSquigglyOpacity()
    pdfviewer.SquigglyAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default author and subject of the squiggly annotation

You can change the default author and subject of the squiggly annotation programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultSquigglyDetails()
{
    pdfViewer.SquigglyAnnotationSettings.Author = "your name";
    pdfViewer.SquigglyAnnotationSettings.Subject = "your subject";
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultSquigglyDetails()
    pdfViewer.SquigglyAnnotationSettings.Author = "your name"
    pdfViewer.SquigglyAnnotationSettings.Subject = "your subject"
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing squiggly annotations

Squiggly annotation supports adding notes along with it, also it allows editing its color and opacity. To use these options, select the included/existing squiggly annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

### Open Pop-up notes

We can add notes to the squiggly annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected squiggly annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

![squiggly annotation](Annotation-images\Squiggly-Annotation-2.jpg)

### Properties

Selecting properties from the context menu will display the Squiggly Properties window, which would consist of two tabs

*	Appearance
*	General 

#### Appearance tab

The color and opacity of the squiggly annotation can be edited using Appearance tab of Squiggly Properties window.

##### Editing color of the annotation

The color of the selected squiggly annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the squiggly annotation.

The following image illustrates how to change the color of the squiggly annotation included.

![squiggly annotation](Annotation-images\Squiggly-Annotation-3.jpg)

The following image illustrated the change in color of the included squiggly annotation.

![squiggly annotation](Annotation-images\Squiggly-Annotation-4.jpg)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected squiggly annotation. You can also modify the opacity of the selected squiggly annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the squiggly annotation.

![squiggly annotation](Annotation-images\Squiggly-Annotation-5.jpg)

The following image illustrates the change in opacity of the included squiggly annotation.

![squiggly annotation](Annotation-images\Squiggly-Annotation-6.jpg)

#### General tab

We can add/edit the default Author and Subject to the included squiggly annotation using General tab of the Squiggly Properties window.

The following image illustrates the change in Author and Subject of the included Squiggly annotation.

![squiggly annotation](Annotation-images\Squiggly-Annotation-7.jpg)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![squiggly annotation](Annotation-images\Squiggly-Annotation-8.jpg)

## Notification when the squiggly has changed

The [TextMarkupAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_TextMarkupAnnotationChanged) event occurs when an squiggly annotation is added, removed or modified. The [TextMarkupAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html) provides the information such as the [type](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_TextMarkupAnnotationChangedEventArgs_Type) of the annotation, the [action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) performed, and the annotation properties.

The following code shows how to wire and handle the event.

{% tabs %}
{% highlight C# %}

//wire the text markup changed event.
pdfViewer.TextMarkupAnnotationChanged += PdfViewer_TextMarkupAnnotationChanged;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

private void PdfViewer_TextMarkupAnnotationChanged(object sender, TextMarkupAnnotationChangedEventArgs e)
{
    //Get the action performed on the annotation 
    //AnnotationChangedAction to identify action performed for annotation 
    AnnotationChangedAction action = e.Action;

    //Page index in which this shape annotation was modified 
    int pageNumber = e.PageNumber;

    //Get annotation's new and old bounds (position and size). 
    RectangleF newBounds = e.NewBounds;
    RectangleF oldBounds = e.OldBounds;

    //To identify which type text markup annotation
    TextMarkupAnnotationType type = e.Type;

    TextMarkupAnnotationSettings settings = e.Settings;
    //Annotation's properties which can be modify 
    string author = settings.Author;
    string subject = settings.Subject;
    string Text = settings.Text;
    float opacity = settings.Opacity;
}

{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.