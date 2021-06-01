---
layout: post
title: Toggle visibility of the tool bar in WPF Pdf Viewer | Syncfusion
description: Learn about Toggle visibility of the tool bar support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
 documentation: ug
---

# Toggle visibility of the tool bar in WPF Pdf Viewer

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer using the [ShowToolbar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowToolbar) property. The following code example hides the default toolbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer = new PdfViewerControl();

//Load the PDF.
pdfViewer.Load("Sample.pdf");

// Hiding the default toolbar of the PDF Viewer
pdfviewer.ShowToolbar = false;
{% endhighlight %}
{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer As New PdfViewerControl()

'Load the PDF.
pdfViewer.Load("Sample.pdf")

' Hiding the default toolbar of the PDF Viewer
pdfViewer.ShowToolbar = False

{% endhighlight %}
{% endtabs %}

## Hide the vertical toolbar

You can hide the vertical toolbar which is present in the left side of PDF Viewer by disabling all the items present in the toolbar. Refer to the following code to hide the vertical toolbar.

{% tabs %}
{% highlight c# %}
private void HideVerticalToolbar() 
{ 
	// Hides the thumbnail icon. 
	pdfViewer.ThumbnailSettings.IsVisible = false; 

	// Hides the bookmark icon. 
	pdfViewer.IsBookmarkEnabled = false; 

	// Hides the layer icon. 
	pdfViewer.EnableLayers = false; 

	// Hides the organize page icon. 
	pdfViewer.PageOrganizerSettings.IsIconVisible = false; 

	// Hides the redaction icon. 
	pdfViewer.EnableRedactionTool = false;   

	// Hides the form icon. 
	pdfViewer.FormSettings.IsIconVisible = false;
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub HideVerticalToolbar()
    pdfViewer.ThumbnailSettings.IsVisible = False
    pdfViewer.IsBookmarkEnabled = False
    pdfViewer.EnableLayers = False
    pdfViewer.PageOrganizerSettings.IsIconVisible = False
    pdfViewer.EnableRedactionTool = False
    pdfViewer.FormSettings.IsIconVisible = False
End Sub
{% endhighlight %}
{% endtabs %}
