---
layout: post
title: File Link Annotation in PDF Viewer WPF | Syncfusion
description: PDF Viewer provides support to view and click file link annotations in PDF document.
platform: wpf
control: PDF Viewer
documentation: ug
---

# File link annotation in WPF Pdf Viewer

PDF viewer supports file link annotations, which means that if you open a PDF document that contain file link annotations, you can click them to get linked file path details through its event.

## How to retrieve the clicked external linked file path from PDF viewer?

You can get the external linked file path from `Settings` property in `FileLinkAnnotationClickedEventArgs` which is passed as a parameter of the `FileLinkAnnotationClicked` event. `FileLinkAnnotationClicked` event will trigger when the file link rectangle region in the PDF document is clicked.

You can get external linked file path, rectangle region bounds and page number in the PDF viewer. Please refer the below example for more details.

{% tabs %}
{% highlight C# %}
public MainWindow()
{
    InitializeComponent();
    pdfViewer.Load("../../Annotations.pdf");
    pdfViewer.FileLinkAnnotationClicked += PdfViewer_FileLinkAnnotationClicked;
}

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
