---
layout: post
title: Navigating through the pages | PDF Viewer | Wpf | Syncfusion
description: navigating through the pages
platform: wpf
control: PDF Viewer
documentation: ug
---

# Navigating through the pages

PDF Viewer allows you to navigate through the pages of the PDF document using the [GotoPage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~GotoPage.html) method. The following code example illustrates the navigation to page 2 of the PDF document.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");


//Navigate to page 2

pdfviewer1.GotoPage(2);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Navigate to page 2

pdfviewer1.GotoPage(2)

{% endhighlight %}
{% endtabs %}