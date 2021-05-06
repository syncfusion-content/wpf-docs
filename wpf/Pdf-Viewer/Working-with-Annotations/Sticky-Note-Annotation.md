---
layout: post
title: Sticky Note Annotation in WPF Pdf Viewer control | Syncfusion
description: Learn about Sticky Note Annotation support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Sticky Note Annotation in WPF Pdf Viewer

PDF Viewer provides an option to include, edit, or remove the sticky note annotation in a PDF document.

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

The following image shows how the sticky note annotation included in the PDF document.

   ![Sticky note Annotation](Annotation-images\Sticky-Note-Annotation-1.png)

## How to set the color of the sticky note annotation

The color of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set default color of the annotation to be included.

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

## How to set opacity of the sticky note annotation

The opacity of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value for the annotation in code behind.

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

## How to set appearance of the sticky note annotation

The appearance of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set the default appearance for the annotation in code behind.

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

## How to set the text of the sticky note annotation

The text of the sticky note annotation can be customized at the time of inclusion itself. The following code shows how to set the default text of the annotation in code behind.

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

The author and subject fields of the sticky note annotation can be added at the time of inclusion itself. The following code shows how to set default author and subject of the annotation in code behind.

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

## Working with existing sticky note annotations

Sticky note annotation supports adding notes along with it, also it allows editing its color, appearance, and opacity. To use these options, select the existing sticky note annotation and right-click using mouse over the selected annotation, a popup context menu will appear with the following options:

* Open Pop-up note
* Properties
* Delete

### Open Pop-up notes

You can add notes to the sticky note annotation by choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected sticky note annotation. The added notes will be saved along with the PDF document and if there are any existing notes, it will be displayed here.

  ![Open popup note](Annotation-images\Sticky-Note-Annotation-2.png)

N> You can also add notes to the sticky note annotation by double tapping on the sticky note annotation.
  
### Properties

Selecting properties from the context menu will display the Sticky Note Properties window that consists of two tabs:

* Appearance
* General 

### Appearance tab

The color, appearance, and opacity of the sticky note annotation can be edited using Appearance tab of Sticky Note Properties window.

#### Editing color of the annotation

The color of the selected sticky note annotation will be displayed in the color row in the Appearance tab. Selecting the Color will display the color palette control, choosing a color from the color palette and clicking OK will apply the color to the sticky note annotation.

The following image illustrates how to change the color of the sticky note annotation.

  ![Before applying sticky note color](Annotation-images\Sticky-Note-Annotation-3.png)

The following image illustrates the change in the color of the sticky note annotation.

  ![After applied sticky note color](Annotation-images\Sticky-Note-Annotation-4.png)

#### Changing appearance of the annotation

The appearance of the annotation can be changed by selecting an icon listed in the Appearance tab.

The following image illustrates how to change the appearance of the sticky note annotation included.

  ![Before applying sticky note appearance](Annotation-images\Sticky-Note-Annotation-5.png)

The following image illustrates the changes in the appearance of the annotation.

  ![After applied sticky note appearance](Annotation-images\Sticky-Note-Annotation-6.png)

#### Editing opacity of the annotation

The slider displayed in the Appearance tab allows you to modify the opacity of the selected sticky note annotation. You can also modify the opacity of the annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the sticky note annotation.

  ![Before applying sticky note opacity](Annotation-images\Sticky-Note-Annotation-7.png)

The following image illustrates the change in the opacity of the sticky note annotation.

  ![After applied sticky note opacity](Annotation-images\Sticky-Note-Annotation-8.png)

### General tab

You can add/edit the default Author and Subject to the sticky note annotation using General tab of the Sticky Note Properties window.

The following image illustrates how to change  Author and Subject of the sticky note annotation.

  ![General Tab](Annotation-images\Sticky-Note-Annotation-9.png)

### Deleting an annotation

Select the delete option from the context menu, which will be displayed by right-clicking the selected annotation to delete the respective annotation from the PDF document.

The following image illustrates how to delete the annotation from the PDF document.

 ![Delete sticky note annotation](Annotation-images\Sticky-Note-Annotation-10.png)
 
## Display tooltip of the annotation

When you place the mouse pointer over the annotation, the tooltip will be displayed. The tooltip contains the author name and text of the annotation.
 
 ![Display tooltip of the sticky note annotation](Annotation-images\Sticky-Note-Annotation-11.png)
 
## Keyboard shortcuts

The following keyboard shortcuts are available to customize the annotation in the PDF document:

*	Delete key: Deletes the selected annotation from the PDF document.
*	Ctrl + Z: Performs undo functionality for recently performed operations.
*	Ctrl + Y: Performs redo functionality for recently performed operations.

## Events

The PdfViewerControl notifies through events, when `AnnotationChangedAction` such us adding, deleting, select, deselect, moving and resizing made in annotations. It also provides the annotations common information such as page index, bounds and action type performed in respective annotation. 

### StickyNoteAnnotationChanged Event

The `StickyNoteAnnotationChanged` event occurs when the `Action` performed in sticky note annotation. It provides the common information and annotation properties which are available in `Settings` through the `StickyNoteAnnotationChangedEventArgs`. The user can modify the annotation properties through ‘Settings`.

The following code shows how to write the StickyNoteAnnotationChanged event in PdfViewerControl

{% tabs %}
{% highlight C# %}

private void PdfViewer_StickyNoteAnnotationChanged(object sender, StickyNoteAnnotationChangedEventArgs e)
{
    //COMMON PROPERTIES
    //AnnotationChangedAction to identify action performed for annotation 
    AnnotationChangedAction action = e.Action;

    //Page index in which this shape annotation was modified 
    int pageNumber = e.PageNumber;

    //Annotation's previous position and current position 
    RectangleF currentBound = e.NewBounds;
    RectangleF previousBound = e.NewBounds;

    PdfViewerStickyNoteSettings settings = e.Settings;
    //Annotation's properties which can be modify 
    string author = settings.Author;
    string subject = settings.Subject;
    string Text = settings.Text;
    float opacity = settings.Opacity;
    System.Windows.Media.Color color = settings.Color;
    PdfPopupIcon pdfPopupIcon = settings.Icon;

}

{% endhighlight %}
{% endtabs %}
