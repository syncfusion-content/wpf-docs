---
layout: post
title: Viewing PDF Files | PDF Viewer | WPF | Syncfusion
description: Viewing PDF files section explains about loading and displaying PDF files from various sources such as from disk, as stream and loading encrypted PDF files. 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Viewing PDF Files 

A PDF can be loaded into the PDF Viewer either through the File Open dialog available in the toolbar or through the [Load](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~Load(String).html) method. It also requests passwords to open encrypted documents.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Template.pdf");

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Template.pdf")

{% endhighlight %}
{% endtabs %}

You can load an encrypted document by using the overload in the [Load](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~Load(String,String).html) method.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Template.pdf", "password");
{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Template.pdf", "password")

{% endhighlight %}
{% endtabs %}

You can also load the PDF document by setting its path to the [ItemSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ItemSource.html) property
{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1. ItemSource="Template.pdf";
{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1. ItemSource = "Template.pdf"

{% endhighlight %}
{% endtabs %}