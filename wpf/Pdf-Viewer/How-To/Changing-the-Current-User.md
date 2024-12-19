---
layout: post
title: Change the Current user in PdfViewer | Syncfusion&reg;
description: Learn about how to Change the CurrentUser in Syncfusion&reg; WPF Pdf Viewer control using CurrentUser property.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the CurrentUser in WPF Pdf Viewer

The PDF Viewer allows you to change the CurrentUser. If the CurrentUser property is not set, it defaults to the system user name. When you set the CurrentUser, the changes will be reflected in the author property of newly added annotations. The following code example illustrates how to set the CurrentUser:

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
