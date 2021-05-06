---
layout: post
title: TextMarkup Annotations in WPF Pdf Viewer control | Syncfusion
description: Learn about TextMarkup Annotations support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# TextMarkup Annotations in WPF Pdf Viewer

PDF viewer WPF includes the following text markup annotations,

*	Highlight annotation
*	Underline annotation
*	Strikethrough annotation

## Highlight Annotation

PDF viewer WPF allows the user to include highlight annotation into the PDF document and provides options to edit or remove the existing highlight annotation in the PDF document.

The following code shows how to switch to highlight annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Highlight;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Highlight
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the highlight annotation being included in the PDF Document.

 ![highlight annotation](Annotation-images\Highlight-Annotation-1.png)

## How to set the color of the highlight annotation?

The following code shows how to set default color of the included highlight annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HighlightAnnotationSettings.HighlightColor= Colors.Green;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HighlightAnnotationSettings.HighlightColor= Colors.Green
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the opacity of the highlight annotation?

The following code shows how to set default opacity value of the included highlight annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HighlightAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HighlightAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the highlight annotation?

The following code shows how to set default Author and subject of the included highlight annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HighlightAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.HighlightAnnotationSettings.Subject = "Highlight annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HighlightAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.HighlightAnnotationSettings.Subject = "Highlight annotation"    
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

### Appearance tab

The color and opacity of the highlight annotation can be edited using Appearance tab of Highlight Properties window.

#### Editing color of the annotation

The color of the selected highlight annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the highlight annotation.

The following image illustrates how to change the color of the highlight annotation included.

![highlight annotation](Annotation-images\Highlight-Annotation-3.png)

The following image illustrates the change in the color of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-4.png)

#### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected highlight annotation. You can also modify the opacity of the selected highlight annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-5.png)

The following image illustrates the change in the opacity of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-6.png)

### General tab

We can add/edit the default Author and Subject to the included highlight annotation using General tab of the Highlight Properties window.

The following image illustrates the change in Author and Subject of the included highlight annotation.

![highlight annotation](Annotation-images\Highlight-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![highlight annotation](Annotation-images\Highlight-Annotation-8.png)


## Underline Annotation

PDF viewer WPF allows the user to include underline annotation into the PDF document and provides options to edit or remove the existing underline annotation in the PDF document.

The following code shows how to switch to underline annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Underline;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Underline
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the underline annotation being included in the PDF Document.

 ![underline annotation](Annotation-images\Underline-Annotation-1.png)

## How to set the color of the underline annotation?

The following code shows how to set default color of the included underline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.UnderlineAnnotationSettings.UnderlineColor = Colors.Blue;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.UnderlineAnnotationSettings.UnderlineColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the opacity of the underline annotation?

The following code shows how to set default opacity value of the included underline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.UnderlineAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.UnderlineAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the underline annotation?

The author and subject fields of the underline annotation can be added for the underline annotation to be added to the PDF document. The following code shows how to set default Author and subject of the included underline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.UnderlineAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.UnderlineAnnotationSettings.Subject = "Underline annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.UnderlineAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.UnderlineAnnotationSettings.Subject = "Underline annotation"
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

### Appearance tab

The color and opacity of the underline annotation can be edited using Appearance tab of Underline Properties window.

#### Editing color of the annotation

The color of the selected underline annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the underline annotation.

The following image illustrates how to change the color of the underline annotation included.

![underline annotation](Annotation-images\Underline-Annotation-3.png)

The following image illustrated the change in color of the included underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-4.png)

#### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected underline annotation. You can also modify the opacity of the selected underline annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-5.png)

The following image illustrates the change in opacity of the included underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-6.png)

### General tab

We can add/edit the default Author and Subject to the included underline annotation using General tab of the Underline Properties window.

The following image illustrates the change in Author and Subject of the included Underline annotation.

![underline annotation](Annotation-images\Underline-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![underline annotation](Annotation-images\Underline-Annotation-8.png)


## Strikethrough Annotation

PDF viewer WPF allows the user to include strikethrough annotation into the PDF document and provides options to edit or remove the existing strikethrough annotation in the PDF document.

The following code shows how to switch to strikethrough annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Strikethrough;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Strikethrough
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the strikethrough annotation being included in the PDF Document.

 ![strikethrough annotation](Annotation-images\Strikethrough-Annotation-1.png)

## How to set the color of the strikethrough annotation?

The following code shows how to set default color of the included strikethrough annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StrikethroughAnnotationSettings. StrikethroughColor=Colors.Blue;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StrikethroughAnnotationSettings. StrikethroughColor=Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the opacity of the strikethrough annotation?

The following code shows how to set default opacity value of the included strikethrough annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StrikethroughAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StrikethroughAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the strikethrough annotation?

The author and subject fields of the strikethrough annotation can be added for the strikethrough annotation to be added to the PDF document.
The following code shows how to set default Author and subject of the included strikethrough annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StrikethroughAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.StrikethroughAnnotationSettings.Subject = "Strikethrough annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StrikethroughAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.StrikethroughAnnotationSettings.Subject = "Strikethrough annotation"
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

### Appearance tab

The color and opacity of the strikethrough annotation can be edited using Appearance tab of StrikeOut Properties window.

#### Editing color of the annotation

The color of the selected strikethrough annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the strikethrough annotation.

The following image illustrates how to change the color of the strikethrough annotation included.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-3.png)

The following image illustrates the change in color of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-4.png)

#### Editing opacity of the annotation


The slider displayed in the Appearance tab will allow us to modify the opacity of the selected strikethrough annotation. You can also modify the opacity of the selected strikethrough annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-5.png)

The following image illustrates the change in opacity of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-6.png)

### General tab

We can add/edit the default Author and Subject of the included strikethrough annotation using General tab of the Underline Properties window.

The following image illustrates the change in Author and Subject of the included Strikethrough annotation.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-7.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![strikethrough annotation](Annotation-images\Strikethrough-Annotation-8.png)

### Keyboard shortcuts

The below keyboard shortcuts are available to customize the annotation in the PDF document.

*	Delete key – Deletes the selected annotation from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.

## Events

The PdfViewerControl notifies through events, when `AnnotationChangedAction` such us adding, deleting, select, deselect, moving and resizing made in annotations. It also provides the annotations common information such as page index, bounds and action type performed in respective annotation. 

### TextMarkupAnnotationChanged Event

The `TextMarkupAnnotationChanged` event occurs when the `Action` performed in text markup annotation. It provides the common information, `Type` and annotation properties which are available in `Settings` through the `TextMarkupAnnotationChangedEventArgs`. The user can modify the annotation properties through ‘Settings`.

The following code shows how to write the TextMarkupAnnotationChanged event in PdfViewerControl

{% tabs %}
{% highlight C# %}

private void PdfViewer_TextMarkupAnnotationChanged(object sender, TextMarkupAnnotationChangedEventArgs e)
{
    //COMMON PROPERTIES
    //AnnotationChangedAction to identify action performed for annotation 
    AnnotationChangedAction action = e.Action;

    //Page index in which this shape annotation was modified 
    int pageNumber = e.PageNumber;

    //Annotation's previous position and current position 
    RectangleF currentBound = e.NewBounds;
    RectangleF previousBound = e.NewBounds;

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
