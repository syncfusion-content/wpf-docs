---
layout: post
title: Toggle visibility of the scroll bar in WPF Pdf Viewer | Syncfusion
description: Learn about Toggle visibility of the scroll bar support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggle visibility of the scroll bar in WPF Pdf Viewer

PDF Viewer supports showing and hiding scrollbar, when you feel to use the PDF Viewer only with the touch support, you can hide the default scrollbars of the PDF Viewer using the [ShowScrollbar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowScrollbar). The following code example hides the scrollbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = false;


{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = False

{% endhighlight %}
{% endtabs %}
