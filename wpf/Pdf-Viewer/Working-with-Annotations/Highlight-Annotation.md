---
layout: post
title: Highlight text in PDF files using WPF PDF Viewer | Syncfusion&reg;
description: Learn about highlight annotation support in Syncfusion&reg; WPF PDF Viewer control, and the manipulations.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Highlight text in PDF files using WPF PDF Viewer

The WPF PDF Viewer allows the user to highlight text in PDF files and provides options to edit or remove the existing highlights. The highlight inclusion mode can be enabled via the toolbar UI or the API. Once the highlight inclusion mode is activated, you can highlight the required text by selecting it. To select the text, hold down the left mouse button and drag the mouse pointer over the text.

To enable the mode from UI, click the below icon in the default toolbar of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

![Highlight icon in the WPF PDF Viewer toolbar](Annotation-images\highlight-icon.png)

N> From version 19.4.0.48, we have updated our default text extraction engine to PDFium for extracting text information from PDF documents. Based on the text information, we create text markup annotations in the PDF documents. Please refer to the [link](https://help.syncfusion.com/wpf/pdf-viewer/text-extraction-engines) for more details.

If you are using [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control, or your own toolbar, or if you want enable the mode programmatically, change the [AnnotationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationMode) property of PDF Viewer to **Highlight**, as shown in the below code example.

{% tabs %}
{% highlight C# %}

private void EnableHighlightInclusionMode()
{
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Highlight;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub EnableHighlightInclusionMode
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Highlight
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the highlighted text in the PDF file.

 ![highlight annotation](Annotation-images\Highlight-Annotation-1.png)

N> The left click selection for the highlight annotation is supported from 19.3.0.5X version.

## Change the default color of the highlight annotation

The highlight color is yellow by default. However, you can change the default color of the highlight programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultHighlightColor()
{
    pdfviewer.HighlightAnnotationSettings.HighlightColor= System.Windows.Media.Colors.Green;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultHighlightColor()
    pdfviewer.HighlightAnnotationSettings.HighlightColor= System.Windows.Media.Colors.Green
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default opacity of the highlight annotation

The highlight opacity value is 1 by default. However, you can change the default opacity of the highlight programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultHighlightOpacity()
{
    pdfviewer.HighlightAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultHighlightOpacity()
    pdfviewer.HighlightAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default author and subject of the highlight annotation

You can change the default author and subject of the highlight annotation programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultHighlightDetails()
{
    pdfviewer.HighlightAnnotationSettings.Author = "your name";
    pdfviewer.HighlightAnnotationSettings.Subject = "your subject";
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultHighlightDetails()
    pdfviewer.HighlightAnnotationSettings.Author = "your name"
    pdfviewer.HighlightAnnotationSettings.Subject = "your subject"    
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing highlight annotations

Highlight annotation supports adding notes along with it, also it allows editing its color and opacity. To use these options, select the included/existing highlight annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

### Open Pop-up notes

We can add notes to the highlight annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected highlight annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

 ![highlight annotation](Annotation-images\Highlight-Annotation-2.png)

### Properties

Selecting properties from the context menu will display the Highlight Properties window, which would consist of two tabs

*	Appearance
*	General 

#### Appearance tab

The color and opacity of the highlight annotation can be edited using Appearance tab of Highlight Properties window.

##### Editing color of the annotation

The color of the selected highlight annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the highlight annotation.

The following image illustrates how to change the color of the highlight annotation included.

![highlight annotation](Annotation-images\Highlight-Annotation-3.png)

The following image illustrates the change in the color of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-4.png)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected highlight annotation. You can also modify the opacity of the selected highlight annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-5.png)

The following image illustrates the change in the opacity of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-6.png)

#### General tab

We can add/edit the default Author and Subject to the included highlight annotation using General tab of the Highlight Properties window.

The following image illustrates the change in Author and Subject of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![highlight annotation](Annotation-images\Highlight-Annotation-8.png)

## Notification when the highlight has changed

The [TextMarkupAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_TextMarkupAnnotationChanged) event occurs when a highlight annotation is added, removed or modified. The [TextMarkupAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html) provides the information such as the [type](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_TextMarkupAnnotationChangedEventArgs_Type) of the annotation, the [action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) performed, and the annotation properties.

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