---
layout: post
title: Change the Current user in PdfViewer | Syncfusion
description: Learn about how to Change the CurrentUser in Syncfusion WPF Pdf Viewer control using CurrentUser property.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the CurrentUser in WPF Pdf Viewer

The PDF Viewer allows you to change the CurrentUser. If the CurrentUser property is not set, it defaults to the system user name. When you set the CurrentUser, you will see the changes in the annotation properties when adding an annotation to the document. The following code example illustrates this:

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer = new PdfViewerControl();
//Load the PDF.
pdfViewer.Load("Sample.pdf");

//Changing the CurrentUser of document
pdfViewer.CurrentUser = "set the name here";
{% endhighlight %}



{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer As New PdfViewerControl()
'Load the PDF.
pdfViewer.Load("Sample.pdf")

'Changing the CurrentUser of document
pdfViewer.CurrentUser = "set the name here";

{% endhighlight %}
{% endtabs %}
