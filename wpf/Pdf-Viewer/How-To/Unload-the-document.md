---
layout: post
title: Unload the document in WPF Pdf Viewer | Syncfusion
description: Learn how the Syncfusion WPF PDF Viewer control automatically unloads the current document when loading a new one, eliminating the need for manual unloading.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Unload the document in Pdf Viewer

PDF Viewer allows you to unload the document with the  [Unload](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload) method of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes.The Unload method is used only for unloading the document. The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

private void button1_Click(object sender, RoutedEventArgs e)
{
      //Unload the document
      pdfviewer.Unload();
}

{% endhighlight %}
{% highlight VB %}

Private Sub button1_Click(sender As Object, e As RoutedEventArgs)
     'Unload the document
    pdfviewer.Unload()
End Sub

{% endhighlight %}
{% endtabs %}

The [Unload(Boolean)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload_System_Boolean_) method of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes includes an optional Boolean parameter to control the disposal of the loaded document. When this parameter is set to true, the method fully disposes of the loaded document. By default, the parameter is set to false.

{% tabs %}
{% highlight c# %}

private void button1_Click(object sender, RoutedEventArgs e)
{
      //Unload the document
      pdfviewer.Unload(true);
}

{% endhighlight %}
{% highlight VB %}

Private Sub button1_Click(sender As Object, e As RoutedEventArgs)
     'Unload the document
    pdfviewer.Unload(true)
End Sub

{% endhighlight %}
{% endtabs %}

N>* In PdfViewerControl, it is recommended not to manually unload the document externally.
N>* The control internally handles the document unloading process.

