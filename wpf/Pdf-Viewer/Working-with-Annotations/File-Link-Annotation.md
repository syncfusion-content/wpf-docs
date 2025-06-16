---
layout: post
title: File Link Annotation in WPF Pdf Viewer control | Syncfusion&reg;
description: Learn about File Link Annotation support in Syncfusion&reg; Essential Studio&reg; WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# File Link Annotation in WPF Pdf Viewer

The PDF viewer supports file link annotations, which means that if you open a PDF document that contains file link annotations, you can click them to get the details of file linked with the annotation, through its clicked event. You can open the file externally from the application, using the details of the file obtained from the event.

## How to obtain the details of the of the annotation and the file linked with the annotation?

The [FileLinkAnnotationClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_FileLinkAnnotationClicked) event will be raised when you click the annotation in PDF pages. Refer to the following code example to wire the `FileLinkAnnotationClicked` event with the PDF Viewer.

{% tabs %}
{% highlight C# %}

pdfViewer.FileLinkAnnotationClicked += PdfViewer_FileLinkAnnotationClicked;
	
{% endhighlight %}
{% endtabs %}

Using the [FileLinkAnnotationClickedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FileLinkAnnotationClickedEventArgs.html) you can obtain the page number, bounds of the annotation through the [PageNumber](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FileLinkAnnotationClickedEventArgs.html#Syncfusion_Windows_PdfViewer_FileLinkAnnotationClickedEventArgs_PageNumber) and [Bounds](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FileLinkAnnotationClickedEventArgs.html#Syncfusion_Windows_PdfViewer_FileLinkAnnotationClickedEventArgs_Bounds) properties respectively.

Similarly, you can obtain the details of the file linked with the annotation using the [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FileLinkAnnotationClickedEventArgs.html#Syncfusion_Windows_PdfViewer_FileLinkAnnotationClickedEventArgs_Settings) property in the [FileLinkAnnotationClickedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FileLinkAnnotationClickedEventArgs.html). Refer to the following code example to obtain the details of the of the annotation and the file linked with the annotation

{% tabs %}
{% highlight C# %}
private void PdfViewer_FileLinkAnnotationClicked(object sender, FileLinkAnnotationClickedEventArgs e)
{
    //Page index in which this file link annotation was clicked 
    int pageNumber = e.PageNumber;
    //Annotation's region.
    RectangleF bounds = e.Bounds;
    FileLinkAnnotationSettings settings = e.Settings;
    //External file path which was linked. 
    string filePath = settings.FileName;
}
{% endhighlight %}
{% endtabs %}

## How to open the file externally from the application level?

You can open the file externally from the application level, by passing the `FileName` as parameter in the Process.Start method.

{% tabs %}
{% highlight C# %}
private void PdfViewer_FileLinkAnnotationClicked(object sender, FileLinkAnnotationClickedEventArgs e)
{
    string filePath = settings.FileName;
    Process.Start(filePath);
}

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.