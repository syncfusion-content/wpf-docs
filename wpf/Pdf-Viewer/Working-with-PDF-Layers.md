---
layout: post
title: Working with PDF Layers in WPF Pdf Viewer control | Syncfusion<sup>&reg;</sup>;
description: Learn about Working with PDF Layers support in Syncfusion<sup>&reg;</sup>; Essential Studio&reg; WPF Pdf Viewer control, its elements and more.
platform: WPF
control: PDF Viewer
documentation: UG
---

# Working with PDF Layers in WPF Pdf Viewer

The layer support in PDF viewer allows users to toggle the visibility of individual and group of layers in the PDF document to view, print, save, and export as image.

## Toggling the visibility of a PDF layer

To toggle the visibility of PDF layers individually, click the eye icon associated with each layer in the layers pane. 

![WPF PDF Viewer Toggle the visibility of PDF layer](Layers_images/wpf-pdf-viewer-toggle-the-visibility-of-pdf-layer.png)

## Toggling the visibility of the group of layers

To toggle the visibility of a group of PDF layers, click the eye icon associated with parent layer in the layers pane.  

![WPF PDF Viewer Toggle the visibility of the group of layer](Layers_images/wpf-pdf-viewer-toggle-the-visibility-of-the-group-of-layer.png)

## Programmatically Toggle the Visibility of a PDF Layer

The WPF PDFViewer allows the user to toggle the visibility of a PDF [Layer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.Layer.html) using its [IsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.Layer.html#Syncfusion_Windows_PdfViewer_Layer_IsVisible) property. When this property is set to false, the layer becomes invisible, and when this property is set to true, the layer becomes visible. The following code sample explains how to use the [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) to retrieve the [Layers](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_Layers) collection and use the [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.Layer.html#Syncfusion_Windows_PdfViewer_Layer_Name) of a PDF layer to toggle its visibility.

{% tabs %}
{% highlight C# %}

//Retrieve a PDF document's layers collection using the PdfDocumentView. 
LayerCollection layers = pdfDocumentView.Layers;  
//Get a layer by its name.              
for (int i = 0; i < layers.Count; i++) 
{ 
    if (layers[i].Name == "Layer2") 
    { 
        //Toggle the visibility of a Layer.  
        if (layers[i].IsVisible) 
           layers[i].IsVisible = false; 
        else 
           layers[i].IsVisible = true; 
    } 
} 

{% endhighlight %}


{% highlight vbnet %}

'Retrieve a PDF document's layers collection using the PdfDocumentView. 
Dim layers As LayerCollection = pdfDocumentView.Layers 
'Get a layer by its name. 
For i As Integer = 0 To layers.Count - 1 
    If layers(i).Name = "Layer2" Then 
      'Toggle the visibility of a Layer. 
       If layers(i).IsVisible Then 
           layers(i).IsVisible = False 
       Else 
           layers(i).IsVisible = True 
       End If 
     End If 
Next

{% endhighlight %}
{% endtabs %}

Similarly, it can be achieved in the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) by accessing the [Layers](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Layers) collection.  

N> The sample project for toggling a PDF Layer is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-PDFViewer-Examples/tree/master/Layers/ToggleLayers) link. 

## Disabling the layers

You can disable the display of the layers present in the PDF document by setting the EnableLayers property to false. Refer to the following code example.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("PdfLayers.pdf");
    pdfViewer.Load(pdf);
    pdfViewer.EnableLayers = false;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument("PdfLayers.pdf")
    pdfViewer.Load(pdf) 
    pdfViewer.EnableLayers = false;
End Sub

{% endhighlight %}
{% endtabs %}


You can also achieve the same in XAML using the DependencyProperty illustrated as follows.


{% highlight xaml %}

<syncfusion:PdfViewerControl x:Name="pdfViewer" EnableLayers="False" />

{% endhighlight %}

N> By default, the layer feature is enabled in PDF viewer.


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.