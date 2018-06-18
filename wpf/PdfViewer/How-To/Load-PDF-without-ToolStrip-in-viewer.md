---
layout: post
title: Load PDF without ToolStrip in viewer| PDF Viewer | Wpf | Syncfusion
description: load pdf without toolstrip in viewer
platform: wpf
control: PDF Viewer
documentation: ug
---

# Load PDF without ToolStrip in viewer

In order to view PDF without the tools strip, make use of [PdfDocumentView](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control instead of PdfViewerControl. Other features and options are similar to PdfViewerControl.

{% tabs %}
{% highlight c# %}

PdfDocumentView pdfDocumentView1 = new PdfDocumentView();

pdfDocumentView1.Load(@"Template.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim pdfDocumentView1 As New PdfDocumentView()

pdfDocumentView1.Load("Template.pdf")

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the PDF document in PdfDocumentView.

![](Load-PDF-without-ToolStrip-in-viewer_images/Load-PDF-without-ToolStrip-in-viewer_img1.png)



