---
layout: post
title: Unload the document in WPF Pdf Viewer | Syncfusion
description: Learn how the Syncfusion WPF PDF Viewer control automatically unloads the current document when loading a new one, eliminating the need for manual unloading.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Unload the document in Pdf Viewer

PDF Viewer allows you to unload the PDF document with the  [Unload(Boolean)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload_System_Boolean_) method of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes.This method includes an optional Boolean parameter to control the disposal of the loaded document.When the parameter is set to true, the method fully disposes of the loaded document, releasing all associated memory and resources. By default, the parameter is set to false, which unloads the document without disposing of it completely, allowing it to be reused if needed.The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

private void button1_Click(object sender, RoutedEventArgs e)
{
      //Unload the PDF document
      pdfviewer.Unload(true);
}

{% endhighlight %}
{% highlight VB %}

Private Sub button1_Click(sender As Object, e As RoutedEventArgs)
     'Unload the PDF document
    pdfviewer.Unload(true)
End Sub

{% endhighlight %}
{% endtabs %}

N>* In PdfViewerControl, it is recommended not to unload the PDF document externally when loading a new PDF document, as the control internally handles the unloading process.

