---
layout: post
title: How to lock an annotation in WPF pdf viewer | Syncfusion
description: Learn about how to enable or disable lock option for an annotation programmatically or UI using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Locking annotations in WPF PDF Viewer

The WPF PDF Viewer provides a support to enable or disable lock option for the annotation in a pdf document. When an annotation is locked, it cannot be moved, resized, and removed.

## Lock an annotation from code behind

The annotation can be locked either by default settings or by annotation changed events using the `IsLocked` API.

### Default settings

To lock an annotation, set the `IsLocked` value in annotation settings as true. The following code sample illustrates how to lock all annotations by default.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
 {
   PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf"); 

   //Loads the PDF document
   pdfviewer.Load(pdf);
   
   //Sets the value to lock all annotations 
   pdfviewer.PolygonAnnotationSettings.IsLocked = true;
   pdfviewer.PolylineAnnotationSettings.IsLocked = true;
   pdfviewer.CircleAnnotationSettings.IsLocked = true;
   pdfviewer.RectangleAnnotationSettings.IsLocked = true;
   pdfviewer.LineAnnotationSettings.IsLocked = true;
   pdfviewer.ArrowAnnotationSettings.IsLocked = true;
   pdfviewer.StickyNoteAnnotationSettings.IsLocked = true;
   pdfviewer.StampAnnotationSettings.IsLocked = true;
   pdfviewer.InkAnnotationSettings.IsLocked = true;
   pdfviewer.FreeTextAnnotationSettings.IsLocked = true;
   pdfviewer.HighlightAnnotationSettings.IsLocked = true;
   pdfviewer.UnderlineAnnotationSettings.IsLocked = true;
   pdfviewer.StrikethroughAnnotationSettings.IsLocked = true;

}

{% endhighlight %}
{% endtabs %}

### Annotation changed event

To lock an annotation by annotation changed event, set the value of `IsLocked` in the annotation changed event as true. The following code sample illustrates how to lock sticky note annotation by using the annotation changed event while adding an annotation.

{% tabs %}
{% highlight C# %}

//Wires the event handler for ` StickyNoteAnnotationChanged` event 
pdfviewer.StickyNoteAnnotationChanged += Pdfviewer_StickyNoteAnnotationChanged;

private void Pdfviewer_StickyNoteAnnotationChanged(object sender, StickyNoteAnnotationChangedEventArgs e)
 {

  if (e.Action == AnnotationChangedAction.Add)
   {

    //Sets the value to lock the annotation
    e.Settings.IsLocked = true;

   }
 }

{% endhighlight %}
{% endtabs %}

N> Similarly, you can implement it for all other annotations in code behind.

## Lock an annotation in UI

The check box control labeled as “Locked” will appear in the annotation properties window, allowing us to enable or disable lock option for the selected annotation.

The following image shows how to enable lock option for sticky note annotation in UI.

![Locking Annotations using WPF PDF Viewer](Annotation-images\Lock-Annotation-1.png)
	 
N> Similarly, you can set it for all other annotations in UI.


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.