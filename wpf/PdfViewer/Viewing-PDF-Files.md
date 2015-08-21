---
layout: post
title: Viewing-PDF-Files 
description: viewing pdf files 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Viewing PDF Files 

A PDF can be loaded into the PDF Viewer either through the File Open dialog available in the toolbar or through the Load method. It also requests passwords to open encrypted documents.

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

You can load an encrypted document by using the overload in the Load method.

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

You can also load the PDF document by setting its path to the ItemSource property

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