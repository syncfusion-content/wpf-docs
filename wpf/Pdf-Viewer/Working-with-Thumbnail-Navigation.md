---
layout: post
title: Thumbnail Navigation in WPF Pdf Viewer control | Syncfusion
description: Learn about Thumbnail Navigation support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Thumbnail Navigation in WPF Pdf Viewer

The thumbnail navigation support in PDF viewer allows users to view a miniature preview of the PDF pages for fast scrolling and easy navigation purpose.

![WPF PDF Viewer Thumbnail Navigation](Thumbnail_images\wpf-pdf-viewer-thumbnail-navigation.png)

## Displaying page thumbnails

Page thumbnails are displayed by clicking the thumbnail icon in the left pane. To display thumbnails pane from code behind,  use the following code example.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
  	pdfviewer.ThumbnailSettings.IsExpanded = true;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
	pdfviewer.ThumbnailSettings.IsExpanded = true
End Sub

{% endhighlight %}
{% endtabs %}

## Enlarging and reducing size of page thumbnails 

Page thumbnails size is enlarged and reduced using the zoom out and zoom in buttons in the Page Thumbnails pane, and also using the magnification slider. 

![WPF PDF Viewer Resizing the Thumbnail Navigation](Thumbnail_images\wpf-pdf-viewer-resizing-the-thumbnail-navigation.png)

## Disabling thumbnails 

Thumbnails are disabled by setting the `IsVisible` property of ThumbnailSettings in the PDF viewer control to false.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
  	pdfviewer.ThumbnailSettings.IsVisible = false;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
	pdfviewer.ThumbnailSettings.IsVisible = false
End Sub

{% endhighlight %}
{% endtabs %}
