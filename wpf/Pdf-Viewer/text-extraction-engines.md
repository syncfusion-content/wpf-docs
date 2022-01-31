---
layout: post
title: Text Extraction Engines in WPF Pdf Viewer control | Syncfusion
description: Learn about Text Extraction Engines supported in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Text Extraction Engines in WPF Pdf Viewer

Syncfusion WPF PDF Viewer extracts text information from PDF files through two different engines for performing text search, text selection, creating text markups and more.

* PDFium (Google Chrome’s text extraction engine)
* SfPdf (Syncfusion’s own text extraction engine)

Before version 19.4.0.48, we used our own text extraction engine (SfPdf) to perform text-based operations in the PDF pages. We have updated our default text extraction engine to PDFium from version 19.4.0.48. The PDFium text extraction engine is recommended for improved performance. However, you may still use our old text extraction engine by setting the `TextExtractionEngine` property to `SfPdf`. Refer to the following code snippet to apply the same.

{% tabs %}
{% highlight c# %}

pdfViewer.TextExtractionEngine = PdfTextExtractionEngine.SfPdf;

{% endhighlight %}
{% highlight vbnet %}