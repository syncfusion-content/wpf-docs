---
layout: post
title: Handwritten Signature in PDF Viewer WPF | Syncfusion
description: Adding, modifying and deleting handwritten signature in PDF document using Syncfusion PDF Viewer WPF.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Handwritten Signature

PDF viewer WPF allows the user to include handwritten signature in the PDF document and provides options to edit or remove the included handwritten signature in the PDF document.

The following code shows how to switch to handwritten signature mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.HandwrittenSignature; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.HandwrittenSignature
End Sub

{% endhighlight %}
{% endtabs %}

Moving to `HandwrittenSignature` mode will open the signature pad, requesting the user to draw the signature. Clicking on apply will add the signature in the PDF Document, this can then be resized and moved to appropriate location.

 ![Handwritten Signature](Handwritten-Signature_images\Handwritten-Signature-1.png)

## How to set the opacity of the handwritten signature?

The opacity of the handwritten signature can be customized at the time of inclusion itself. The following code shows how to set opacity value of the handwritten signature to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.Opacity = 0.5F;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the color of the handwritten signature?

The color of the handwritten signature can be customized at the time of inclusion itself.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.Color = Colors.Green; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.Color = Colors.Green
End Sub

{% endhighlight %}
{% endtabs %}

## How to flatten handwritten signature on save?

The included handwritten signature can be flattened in the PDF document when saving it, setting `FlattenSignatureOnSave` Boolean to true in `HandwrittenSignatureSettings` will do this. 

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.FlattenSignatureOnSave = true; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.FlattenSignatureOnSave = true
End Sub

{% endhighlight %}
{% endtabs %}

N> If the handwritten signature is not flattened, it will be saved as ink annotation in the PDF document. 

## Working with included handwritten signatures

The PDF viewer allows editing the color and opacity of the Handwritten signature included in the document in the UI.. To perform this, select the included handwritten signature and click right using mouse, over the selected handwritten signature, a pop-up context menu will appear with the following options,

*	Properties
*	Delete

## Properties

Selecting properties from the context menu will display the Handwritten Signature Properties window, which would have Appearance tab.

## Appearance tab

The color, opacity of the handwritten signature can be edited using Appearance tab of Handwritten Signature Properties window. 

### Editing color of the signature

The color of the selected handwritten signature will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette, choosing a color from the color palette and clicking OK will apply the color to the handwritten signature.

The following image illustrates how to change the color of the handwritten signature.

![Edit color of the signature](Handwritten-Signature_images\Handwritten-Signature-2.png)

### Editing opacity of the signature

The slider displayed in the Appearance tab allows modifying opacity of the selected handwritten signature. You can also modify the opacity of the selected handwritten signature by giving numeric value in the opacity text box.

![Edit opacity of the signature](Handwritten-Signature_images\Handwritten-Signature-3.png)

## Deleting a signature

Selecting delete option from the context menu which is displayed when clicking right on the selected signature would delete the respective signature from the PDF document.

![Delete a signature](Handwritten-Signature_images\Handwritten-Signature-4.png)

## Keyboard shortcuts

The below keyboard shortcuts are available to customize the handwritten signature in the PDF document.

*	Delete key – Deletes the selected signature from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.
