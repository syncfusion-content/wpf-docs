---
layout: post
title: Unload the document in WPF Pdf Viewer | Syncfusion
description: Learn how the Syncfusion WPF PDF Viewer control automatically unloads the current document when loading a new one, eliminating the need for manual unloading.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Unload the document in Pdf Viewer

PDF Viewer allows you to unload the document with the  [Unload](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Unload) method of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes. The following code sample illustrates the same.

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
    pdfviewer.Unload();
End Sub

{% endhighlight %}
{% endtabs %}

N>* In PdfViewerControl, there is no need to manually unload the current document before loading a new one. 
N>* The control automatically unloads the previous document after the new one has finished loading. This built-in functionality ensures seamless transitions between documents without requiring additional code for manual unloading.
N>*However, if you want to explicitly unload a document,you can use the Unload method.
