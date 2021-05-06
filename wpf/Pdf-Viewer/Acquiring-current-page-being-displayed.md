---
layout: post
title: Acquire current page being displayed in WPF Pdf Viewer control | Syncfusion
description: Learn about Acquire current page being displayed support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Acquire current page being displayed in WPF Pdf Viewer

PDF Viewer supports acquiring the index of the page being displayed in the PDF Viewer at any moment using the [CurrentPageIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_CurrentPageIndex) property. The following code example illustrates the same.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Acquiring the number of page being displayed in the Viewer  

int pageCount = pdfviewer1.CurrentPageIndex;


{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

' Acquiring the number of page being displayed in the Viewer  

Dim pageCount As Integer = pdfviewer1. CurrentPageIndex

{% endhighlight %}
{% endtabs %}
