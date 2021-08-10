---
layout: post
title: Interaction Modes in WPF Pdf Viewer control | Syncfusion
description: Learn about Interaction Modes support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: WPF
control: PDF Viewer
documentation: UG
---

# Interaction Modes in WPF Pdf Viewer

The PDF Viewer supports following cursor modes for easy interaction with the PDF documents: 

* Selection mode 
* Panning mode
* Marquee zoom mode

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

## Marquee zoom mode

In this mode, you can zoom a particular area of a PDF document by dragging the area using the zoom tool or keyboard actions. You can marquee a section by left click and drag using your mouse. By pressing the `Ctrl` key, you can decrease the zoom level. Refer to the following code to enable the marquee zoom mode in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}

{% highlight C# %}

PdfViewerControl pdfViewerControl = new PdfViewerControl();
pdfViewerControl.CursorMode = PdfViewerCursorMode.MarqueeZoom;
pdfViewerControl.Load("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewerControl As PdfViewerControl = New PdfViewerControl()
pdfViewerControl.CursorMode = PdfViewerCursorMode.MarqueeZoom
pdfViewerControl.Load("Sample.pdf")

{% endhighlight %}

{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.