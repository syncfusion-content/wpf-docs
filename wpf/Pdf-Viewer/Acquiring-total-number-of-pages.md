---
layout: post
title: Acquire total number of pages in WPF Pdf Viewer control | Syncfusion
description: Learn about Acquire total number of pages support in Syncfusion WPF Pdf Viewer control, its elements and more details.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Acquire total number of pages in WPF Pdf Viewer

PDF Viewer provides the total number of the pages in the PDF document that is being loaded into the PDF Viewer. This value can be acquired with the help of [PageCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageCount) property in the PDF Viewer control, the following code example illustrates the same.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Acquiring the total number of pages in the document being loaded  

int pageCount = pdfviewer1.PageCount;


{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Acquiring the total number of pages in the document being loaded 

Dim pageCount As Integer = pdfviewer1.PageCount
{% endhighlight %}
{% endtabs %}
