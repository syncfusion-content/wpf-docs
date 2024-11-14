---
layout: post
title: Unload the document in WPF Pdf Viewer | Syncfusion
description: Learn about Unload the document in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Unload the document

The [Unload](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) allows you to unload the pdf document.The following code snippet illustrates unload the pdf document in the PdfViewer.

{% tabs %}
{%highlight c#%}

pdfviewer.Unload();

{%endhighlight%}

{%highlight vb%}

pdfviewer.Unload()

{%endhighlight%}
{% endtabs %}

N>* In PdfViewerControl, there’s no need to manually unload the current document before loading a new one, as the control automatically unloads the previous document after the new one has finished loading.
