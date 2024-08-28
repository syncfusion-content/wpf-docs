---
layout: post
title: Change the CurrentUser of annotations in Pdf Viewer | Syncfusion
description: Learn about Change the CurrentUser of annotations in Syncfusion WPF Pdf Viewer control.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the CurrentUser of annotations in WPF Pdf Viewer

PDF Viewer allows you to change the CurrentUser of annotations. The following code example illustrates the same.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer1 = new PdfViewerControl();
//Load the PDF.
pdfViewer1.Load("Sample.pdf");

//Changing the CurrentUser of document
pdfViewer1.CurrentUser = "set the name here";
{% endhighlight %}



{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer1 As New PdfViewerControl()
'Load the PDF.
pdfViewer1.Load("Sample.pdf")

'Changing the CurrentUser of document
pdfViewer1.CurrentUser = "set the name here";

{% endhighlight %}
{% endtabs %}
