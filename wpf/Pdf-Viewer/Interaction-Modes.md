---
layout: post
title: Working with Interaction Modes | PDF Viewer | WPF | Syncfusion
description: This section describes about how to work with various interaction modes that are supported in PDF viewer.
platform: WPF
control: PDF Viewer
documentation: UG
---

# Working with Interaction Modes

The PDF Viewer supports following cursor modes for easy interaction with the PDF documents: 

* Selection mode 
* Panning mode

## Selection mode

In this mode, the text selection can be performed in the PDF document loaded in the PDF Viewer. It is the default mode of the control and allows users to select and copy text from the PDF files. This is helpful for copying and sharing text content. Refer to the following code to enable the selection mode in `PdfViewerControl`.

{% tabs %}

{% highlight C# %}

PdfViewerControl pdfViewerControl = new PdfViewerControl(); 
pdfViewerControl.CursorMode = PdfViewerCursorMode.SelectTool;
pdfViewerControl.Load("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewerControl As PdfViewerControl = New PdfViewerControl()
pdfViewerControl.CursorMode = PdfViewerCursorMode.SelectTool
pdfViewerControl.Load("Sample.pdf")

{% endhighlight %}

{% endtabs %}


## Panning mode

In this mode, the dragging and scrolling of the pages can be performed in any direction using mouse and touch interactions, but the text selection cannot be performed. Refer to the following code to enable the panning mode in `PdfViewerControl`.

{% tabs %}

{% highlight C# %}

PdfViewerControl pdfViewerControl = new PdfViewerControl();
pdfViewerControl.CursorMode = PdfViewerCursorMode.HandTool;
pdfViewerControl.Load("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewerControl As PdfViewerControl = New PdfViewerControl()
pdfViewerControl.CursorMode = PdfViewerCursorMode.HandTool
pdfViewerControl.Load("Sample.pdf")

{% endhighlight %}

{% endtabs %}