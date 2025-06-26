---
layout: post
title: Select and Copy Text from PDF using WPF PDF Viewer | Syncfusion&reg;
description: Learn about Select and Copy Text support in Syncfusion&reg; Essential Studio&reg; WPF Pdf Viewer control.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Select and Copy Text in PDF files using WPF PDF Viewer

In PDF Viewer, text can be selected by clicking the mouse left button and dragging the mouse pointer over the text in any direction.

N> From version 19.4.0.48, we have updated our default text extraction engine to PDFium for extracting text information from PDF documents. Based on the text information, we select text in the PDF documents. Please refer to the [link](https://help.syncfusion.com/wpf/pdf-viewer/text-extraction-engines) for more details.

## Detecting the completion of text selection

When the text selection is completed, the [TextSelectionCompleted](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_TextSelectionCompleted) event will be raised. Refer to the following code snippet for wiring the event.

{% tabs %}
{% highlight c# %}

pdfViewer.TextSelectionCompleted += PdfViewer_TextSelectionCompleted;

{% endhighlight %}
{% endtabs %}

The selected text can be retrieved as string from the [TextSelectionCompletedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.TextSelectionCompletedEventArgs.html) of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_TextSelectionCompleted(object sender, TextSelectionCompletedEventArgs args) 
{
      //Get the whole selected text 
      string selectedText = args.SelectedText;
      //Get the selected text and its rectangular bounds for each page separately if the selection is made on multiple pages 
      Dictionary<int, Dictionary<string, Rectangle>> selectedTextInformation = args.SelectedTextInformation; 
}

{% endhighlight %}
{% endtabs %}

## Copying the selected text

The selected text can be copied by clicking the copy from the context menu, which appears when clicking the right mouse button after the text is selected.

![WPF PDF Viewer Copying the Selected Text](Select_and_copy_text_images/wpf-pdf-viewer-copying-the-selected-text.png)

The selected text can also be copied using the keyboard shortcut `Ctrl + C`.

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.