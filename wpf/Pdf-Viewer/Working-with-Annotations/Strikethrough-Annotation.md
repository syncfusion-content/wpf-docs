---
layout: post
title: Strikethrough text in PDF files using WPF PDF Viewer | Syncfusion
description: Learn about Strikethrough annotation support in Syncfusion WPF PDF Viewer control, and the manipulations.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Strikethrough text in PDF files using WPF PDF Viewer

The WPF PDF Viewer allows the user to strikethrough text in PDF files and provides options to edit or remove the existing strikethrough. The strikethrough inclusion mode can be enabled via the toolbar UI or the API. To enable the mode from UI, click the below icon in the default toolbar of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

![Strikethrough icon in the WPF PDF Viewer toolbar](Annotation-images\strikethrough-icon.png)

If you are using [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control, or your own toolbar, or if you want enable the mode programmatically, change the [AnnotationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationMode) property of PDF Viewer to **Strikethrough**, as shown in the below code example.

{% tabs %}
{% highlight C# %}

private void EnableStrikethroughInclusionMode()
{
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Strikethrough;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub EnableStrikethroughInclusionMode()
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Strikethrough
End Sub

{% endhighlight %}
{% endtabs %}

Once the strikethrough inclusion mode is activated, you can strikethrough the required text by selecting it. You can select the text by holding down the left mouse button and dragging the mouse pointer over the text. The following image shows the strikethrough text in the PDF file.

 ![strikethrough annotation](Annotation-images\Strikethrough-Annotation-1.png)

## Change the default color of the strikethrough annotation

The strikethrough color is red by default. However, you can change the default color of the strikethrough programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultStrikethroughColor()
{
    pdfViewer.StrikethroughAnnotationSettings.StrikethroughColor=System.Windows.Media.Colors.Blue;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultStrikethroughColor()
    pdfViewer.StrikethroughAnnotationSettings.StrikethroughColor=System.Windows.Media.Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default opacity of the strikethrough annotation

The strikethrough opacity value is 1 by default. However, you can change the default opacity of the strikethrough programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultStrikethroughOpacity()
{
    pdfViewer.StrikethroughAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultStrikethroughOpacity()
    pdfViewer.StrikethroughAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## Change the default author and subject of the strikethrough annotation

You can change the default author and subject of the strikethrough annotation programmatically as shown in the following code example.

{% tabs %}
{% highlight C# %}

private void ChangeDefaultStrikethroughDetails()
{
    pdfviewer.StrikethroughAnnotationSettings.Author = "your name";
    pdfviewer.StrikethroughAnnotationSettings.Subject = "your subject";
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub ChangeDefaultStrikethroughDetails()
    pdfviewer.StrikethroughAnnotationSettings.Author = "your name"
    pdfviewer.StrikethroughAnnotationSettings.Subject = "your subject"
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing strikethrough annotations

Strikethrough annotation supports adding notes along with it, also it allows editing its color and opacity. To use these options, select the included/existing strikethrough annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

### Open Pop-up notes

We can add notes to the strikethrough annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected strikethrough annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-2.png)

### Properties

Selecting properties from the context menu will display the Strikethrough Properties window, which would consist of two tabs

*	Appearance
*	General 

#### Appearance tab

The color and opacity of the strikethrough annotation can be edited using Appearance tab of StrikeOut Properties window.

##### Editing color of the annotation

The color of the selected strikethrough annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the strikethrough annotation.

The following image illustrates how to change the color of the strikethrough annotation included.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-3.png)

The following image illustrates the change in color of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-4.png)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected strikethrough annotation. You can also modify the opacity of the selected strikethrough annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-5.png)

The following image illustrates the change in opacity of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-6.png)

#### General tab

We can add/edit the default Author and Subject of the included strikethrough annotation using General tab of the strikethrough Properties window.

The following image illustrates the change in Author and Subject of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-8.png)

## Notification when the strikethrough has changed

The [TextMarkupAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_TextMarkupAnnotationChanged) event occurs when a strikethrough annotation is added, removed or modified. The [TextMarkupAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html) provides the information such as the [type](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextMarkupAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_TextMarkupAnnotationChangedEventArgs_Type) of the annotation, the [action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) performed, and the annotation properties.

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