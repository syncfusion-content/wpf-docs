---
layout: post
title: Toggling visibility of the tool bar| PDF Viewer | Wpf | Syncfusion
description: toggling visibility of the tool bar
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggling visibility of the tool bar

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer using the [ShowToolbar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowToolbar) property. The following code example hides the default toolbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = false;
{% endhighlight %}




{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

' Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = False

{% endhighlight %}
{% endtabs %}