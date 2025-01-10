---
layout: post
title: Unload the document in WPF Pdf Viewer | Syncfusion®
description: Learn how the Syncfusion® WPF PDF Viewer control automatically unloads the current document when loading a new one, eliminating the need for manual unloading.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Unload the document in Pdf Viewer

The WPF PDF Viewer also allows a user to Unload the PDF document using [Unload()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload) API of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes.
A user can dispose the PDF document by passing the Boolean parameter as ‘true’ to the [Unload(Boolean)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload_System_Boolean_) API. The below code illustrates how to dispose the PDF document programmatically.

{% tabs %}
{% highlight c# %}

private void UnloadButton_Click(object sender, RoutedEventArgs e)
{
      //Unload the PDF document
      pdfviewer.Unload(true);
}

{% endhighlight %}
{% highlight VB %}

Private Sub UnloadButton_Click(sender As Object, e As RoutedEventArgs)
     'Unload the PDF document
    pdfviewer.Unload(true)
End Sub

{% endhighlight %}
{% endtabs %}

N>In PdfViewerControl, it is recommended not to unload the PDF document externally when loading a new PDF document, as the control internally handles the unloading process.

