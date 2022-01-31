---
layout: post
title: Underline text in PDF files using WPF PDF Viewer | Syncfusion
description: Learn about underline annotation support in Syncfusion WPF PDF Viewer control, and the manipulations.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Underline text in PDF files using WPF PDF Viewer

The WPF PDF Viewer allows the user to underline text in PDF files and provides options to edit or remove the existing underlines. The underline inclusion mode can be enabled via the toolbar UI or the API. Once the underline inclusion mode is activated, you can underline the required text by selecting it. To select the text, hold down the left mouse button and drag the mouse pointer over the text.

To enable the mode from UI, click the below icon in the default toolbar of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

![Underline icon in the WPF PDF Viewer toolbar](Annotation-images\underline-icon.png)

N> From version 19.4.0.48, we have updated our default text extraction engine to PDFium for extracting text information from PDF documents. Based on the text information, we create text markup annotations in the PDF documents. Please refer to the [link](https://help.syncfusion.com/wpf/pdf-viewer/text-extraction-engines) for more details.

If you are using [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control, or your own toolbar, or if you want enable the mode programmatically, change the [AnnotationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationMode) property of PDF Viewer to **Underline**, as shown in the below code example.

{% tabs %}
{% highlight C# %}

private void EnableUnderlineInclusionMode()
{
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Underline;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub EnableUnderlineInclusionMode()
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Underline
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the underlined text in the PDF file.

 ![underline annotation](Annotation-images\Underline-Annotation-1.png)

N> The left click selection for the underline annotation is supported from 19.3.0.5X version.

## Change the default color of the underline annotation

The underline color is dark green by default. However, you can change the default color of the underline programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultUnderlineColor()
{
    pdfViewer.UnderlineAnnotationSettings.UnderlineColor = System.Windows.Media.Colors.Blue;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultUnderlineColor()
    pdfviewer.UnderlineAnnotationSettings.UnderlineColor = System.Windows.Media.Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default opacity of the underline annotation

The underline opacity value is 1 by default. However, you can change the default opacity of the underline programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultUnderlineOpacity()
{
    pdfViewer.UnderlineAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultUnderlineOpacity()
    pdfviewer.UnderlineAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default author and subject of the underline annotation

You can change the default author and subject of the underline annotation programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultUnderlineDetails()
{
    pdfViewer.UnderlineAnnotationSettings.Author = "your name";
    pdfViewer.UnderlineAnnotationSettings.Subject = "your subject";
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultUnderlineDetails()
    pdfViewer.UnderlineAnnotationSettings.Author = "your name"
    pdfViewer.UnderlineAnnotationSettings.Subject = "your subject"
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing underline annotations

Underline annotation supports adding notes along with it, also it allows editing its color and opacity. To use these options, select the included/existing underline annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

### Open Pop-up notes

We can add notes to the underline annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected underline annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

![underline annotation](Annotation-images\Underline-Annotation-2.png)

### Properties

Selecting properties from the context menu will display the Underline Properties window, which would consist of two tabs

*	Appearance
*	General 

#### Appearance tab

The color and opacity of the underline annotation can be edited using Appearance tab of Underline Properties window.

##### Editing color of the annotation

The color of the selected underline annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the underline annotation.

The following image illustrates how to change the color of the underline annotation included.

![underline annotation](Annotation-images\Underline-Annotation-3.png)

The following image illustrated the change in color of the included underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-4.png)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected underline annotation. You can also modify the opacity of the selected underline annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-5.png)

The following image illustrates the change in opacity of the included underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-6.png)

#### General tab

We can add/edit the default Author and Subject to the included underline annotation using General tab of the Underline Properties window.

The following image illustrates the change in Author and Subject of the included Underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![underline annotation](Annotation-images\Underline-Annotation-8.png)

## Notification when the underline has changed

The [TextMarkupAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_TextMarkupAnnotationChanged) event occurs when an underline annotation is added, removed or modified. The [TextMarkupAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html) provides the information such as the [type](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_TextMarkupAnnotationChangedEventArgs_Type) of the annotation, the [action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) performed, and the annotation properties.

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