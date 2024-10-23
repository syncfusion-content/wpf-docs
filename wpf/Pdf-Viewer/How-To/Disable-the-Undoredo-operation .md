---
layout: post
title: Disable the Undoredo Operation in PdfViewer | Syncfusion
description: Learn about how to Disable the Undo/redo Operation in Syncfusion WPF Pdf Viewer control using Limit property of UndoRedoSettings.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable the Undoredo Operation in PdfViewer

The PDF Viewer allows you to Disable the Undoredo Operation. If the Limit property of UndoRedoSettings is not set, it defaults value will be limited to 100.By reducing the value of this property to zero will disable the undoredo function of PdfViewer. The following code example illustrates how to set the CurrentUser:

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer = new PdfViewerControl();
//Disable the Undoredo Operation of document
pdfViewer.UndoRedoSettings.Limit = 0;
//Load the PDF.
pdfViewer.Load("Sample.pdf");


{% endhighlight %}



{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer As New PdfViewerControl()
'Disable the Undoredo Operation of document
pdfViewer.UndoRedoSettings.Limit = 0;
'Load the PDF.
pdfViewer.Load("Sample.pdf")


{% endhighlight %}
{% endtabs %}