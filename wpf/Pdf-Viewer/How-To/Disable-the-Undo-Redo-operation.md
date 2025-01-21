---
layout: post
title: Disable the Undo Redo operation in PdfViewer | Syncfusion&reg;
description: Learn about how to Disable the Undo Redo operation in Syncfusion<sup>&reg;</sup>; WPF Pdf Viewer control using UndoRedoSettings.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable the Undo Redo operation 

To disable the Undo Redo operation, set the Limit property of UndoRedoSettings to zero. By default, this value is set to 100. Reducing the value to zero will disable the Undo Redo functionality. The following code example demonstrates how to set the Limit value:

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer = new PdfViewerControl();
//Set Limit property as zero
pdfViewer.UndoRedoSettings.Limit = 0;
//Load the PDF.
pdfViewer.Load("Sample.pdf");


{% endhighlight %}



{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer As New PdfViewerControl()
'Set Limit property as zero
pdfViewer.UndoRedoSettings.Limit = 0
'Load the PDF.
pdfViewer.Load("Sample.pdf")


{% endhighlight %}
{% endtabs %}