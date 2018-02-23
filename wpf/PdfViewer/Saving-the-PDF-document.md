---
layout: post
title: Saving the PDF document | PDF Viewer | Wpf | Syncfusion
description: saving the pdf document
platform: wpf
control: PDF Viewer
documentation: ug
---

# Saving the PDF document

PDF Viewer also allows you to save the PDF document that is being displayed in the PDF Viewer. The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");


//Acquire the document loaded into the PDF Viewer

PdfLoadedDocument lDoc = pdfviewer1.LoadedDocument;



//Save the document

lDoc.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Acquire the document loaded into the PDF Viewer

Dim lDoc As PdfLoadedDocument = pdfviewer1.LoadedDocument



'Save the document

lDoc.Save("Sample.pdf")

{% endhighlight %}
{% endtabs %}