---
layout: post
title: Load a specific page| PDF Viewer | Wpf | Syncfusion<sup>&reg;</sup>;
description: Load a specific page in Syncfusion<sup>&reg;</sup>;Essential Studio<sup>&reg;</sup>; WPF PdfViewer Control, its elements, features, and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Load a specific page

Navigation to a specific page, through code, is possible using [GoToPageAtIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_GoToPageAtIndex_System_Int32_) method.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer1 = new PdfViewerControl();

//Load the PDF.
pdfViewer1.Load("Sample.pdf");
pdfViewer1.GoToPageAtIndex(2);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer1 As New PdfViewerControl()

'Load the PDF.
pdfViewer1.Load("Sample.pdf")
pdfViewer1.GoToPageAtIndex(2)



{% endhighlight %}
{% endtabs %}