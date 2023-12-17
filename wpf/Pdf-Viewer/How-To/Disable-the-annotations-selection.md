---
layout: post
title: Disable the annotations selection in WPF Pdf Viewer | Syncfusion
description: Learn about disabling the selection of annotations support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable the annotations selection

PDF Viewer allows you to enable or disable the annotations selection using the `Constraints` property programmatically. The following code snippet illustrates disabling the selection of the exsisting and newly added freetext annotations in the PdfViewer.

{% tabs %}
{% highlight c# %}
// Trigger the DocumentLoaded event of the PdfViewerControl.
pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;

private void PdfViewer_DocumentLoaded(object sender, EventArgs args)
{
    // Disable the selection of the free text annotations.
    pdfViewer.FreeTextAnnotationSettings.Constraints = ~AnnotationConstraints.Selectable;
}

{% endhighlight %}

{% highlight vbnet %}

' Trigger the DocumentLoaded event of the PdfViewerControl.
AddHandler pdfViewer.DocumentLoaded, AddressOf PdfViewer_DocumentLoaded

Private Sub PdfViewer_DocumentLoaded(ByVal sender As Object, ByVal args As EventArgs)
    ' Disable the selection of the free text annotations.
    pdfViewer.FreeTextAnnotationSettings.Constraints = Not AnnotationConstraints.Selectable
End Sub

{% endhighlight %}
{% endtabs %}

N>* Similarly, you can disable the selection for all other annotations.
N>* If you disable/enable the annotations selection after the document is loaded, the changes will only be reflected in the newly added annotations.
