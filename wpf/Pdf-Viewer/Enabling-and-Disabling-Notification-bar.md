---
layout: post
title: Enable and Disable Notification bar in WPF Pdf Viewer | Syncfusion
description: Learn about Enable and Disable Notification bar support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
 documentation: ug
---

# Enable and Disable Notification bar in WPF Pdf Viewer

Notification bar is a part of the PDF Viewer that is used to display when an unexpected error occurs in the PDF Viewer control. You can suppress the display of the Notification bar by setting the [EnableNotificationBar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_EnableNotificationBar) property to false. The following code example illustrate the same.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= false;
{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= False

{% endhighlight %}
{% endtabs %}
