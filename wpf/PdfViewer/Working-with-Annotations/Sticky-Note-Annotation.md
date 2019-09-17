---
layout: post
title: Sticky note Annotation in PDF Viewer WPF | Syncfusion
description: Adding, modifying and deleting sticky note annotation in PDF document using Syncfusion PDF Viewer WPF.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Sticky note annotation

PDF viewer allows the user to include sticky note annotation in the PDF document and provides options to edit or remove the existing sticky note annotation in the PDF document.

The following code shows how to switch to sticky note annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.StickyNote;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.StickyNote
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the sticky note annotation being included in the PDF Document.

   ![Sticky note Annotation](Annotation-images\Sticky-Note-Annotation-1.png)

## How to set the color of the sticky note annotation?

The color of the sticky note annotation included can be customized at the time of inclusion itself. The following code shows how to set color of the sticky note annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StickyNoteAnnotationSettings.Color = Colors.Red;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StickyNoteAnnotationSettings.Color = Colors.Red
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the opacity of the sticky note annotation?

The opacity of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value of the included sticky note annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StickyNoteAnnotationSettings.Opacity = 0.5F;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StickyNoteAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the appearance of the sticky note annotation?

The appearance of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set the default appearance of the included sticky note annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StickyNoteAnnotationSettings.Icon = Syncfusion.Pdf.Interactive.PdfPopupIcon.Key;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StickyNoteAnnotationSettings.Icon = Syncfusion.Pdf.Interactive.PdfPopupIcon.Key
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the text of the sticky note annotation?

The text of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set the default text of the included sticky note annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StickyNoteAnnotationSettings.Text = "Sticky Note";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StickyNoteAnnotationSettings.Text = "Sticky Note"
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the sticky note annotation?

The author and subject fields of the sticky note annotation can be added for the sticky note annotation to be added to the PDF document. The following code shows how to set default author and subject of the included sticky note annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StickyNoteAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.StickyNoteAnnotationSettings.Subject = "Sticky Note Annotation"; 
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StickyNoteAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.StickyNoteAnnotationSettings.Subject = "Sticky Note Annotation"   
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing sticky note annotations

Sticky note annotation supports adding notes along with it, also it allows editing its color, appearance and opacity. To use these options, select the included/existing sticky note annotation and click right using mouse, over the selected annotation, a popup context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

### Open Pop-up notes

We can add notes to the sticky note annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected sticky note annotation. The added notes will be saved along with the PDF document and if there are any existing notes, it will be displayed in here.

  ![Open popup note](Annotation-images\Sticky-Note-Annotation-2.png)

N> We can also add notes to the sticky note annotation by double tapping on the sticky note annotation.
  
### Properties

Selecting properties from the context menu will display the Sticky note Properties window, which would consist of two tabs

* Appearance
* General 

### Appearance tab

The color, appearance and opacity of the sticky note annotation can be edited using Appearance tab of Sticky Note Properties window.

#### Editing color of the annotation

The color of the selected sticky note annotation will be displayed in the color row in the Appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the sticky note annotation.

The following image illustrates how to change the color of the sticky note annotation included.

  ![Before applying sticky note color](Annotation-images\Sticky-Note-Annotation-3.png)

The following image illustrates the change in the color of the included sticky note annotation.

  ![After applied sticky note color](Annotation-images\Sticky-Note-Annotation-4.png)

#### Changing appearance of the annotation

The appearance of the annotation can be changed by selecting an icon which is listed in the Appearance tab.

The following image illustrates how to change the appearance of the sticky note annotation included.

  ![Before applying sticky note appearance](Annotation-images\Sticky-Note-Annotation-5.png)

The following image illustrates the change in the appearance of the included sticky note annotation.

  ![After applied sticky note appearance](Annotation-images\Sticky-Note-Annotation-6.png)

#### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected sticky note annotation. You can also modify the opacity of the selected sticky note annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included sticky note annotation.

  ![Before applying sticky note opacity](Annotation-images\Sticky-Note-Annotation-7.png)

The following image illustrates the change in the opacity of the included sticky note annotation.

  ![After applied sticky note opacity](Annotation-images\Sticky-Note-Annotation-8.png)

### General tab

We can add/edit the default Author and Subject to the included sticky note annotation using General tab of the Sticky Note Properties window.

The following image illustrates the change in Author and Subject of the included sticky note annotation.

  ![General Tab](Annotation-images\Sticky-Note-Annotation-9.png)

### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

 ![Delete sticky note annotation](Annotation-images\Sticky-Note-Annotation-10.png)
 
## Display tooltip of the annotation

When you place the mouse pointer over the annotation the tooltip will be displayed. The tooltip contains the author name and the text of the annotation.
 
 ![Display tooltip of the sticky note annotation](Annotation-images\Sticky-Note-Annotation-11.png)
 
## Keyboard shortcuts

The below keyboard shortcuts are available to customize the annotation in the PDF document.

*	Delete key – Deletes the selected annotation from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.
