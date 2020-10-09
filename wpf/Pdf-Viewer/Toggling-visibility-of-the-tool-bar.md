---
layout: post
title: Toggling visibility of the tool bar| PDF Viewer | Wpf | Syncfusion
description: This section explains how to disable the horizontal toolbar of PDF Viewer and how to disable the vertical toolbar by hiding the items in the toolbar.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggling visibility of the tool bar

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer using the [ShowToolbar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowToolbar) property. The following code example hides the default toolbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer1 = new PdfViewerControl();

//Load the PDF.
pdfViewer1.Load("Sample.pdf");

// Hiding the default toolbar of the PDF Viewer
pdfviewer1.ShowToolbar = false;
{% endhighlight %}
{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer1 As New PdfViewerControl()

'Load the PDF.
pdfViewer1.Load("Sample.pdf")

' Hiding the default toolbar of the PDF Viewer
pdfViewer1.ShowToolbar = False

{% endhighlight %}
{% endtabs %}

## Hide the vertical toolbar

You can hide the vertical toolbar which is present in the left side of PDF Viewer by disabling all the items present in the toolbar. Refer to the following code to hide the vertical toolbar.

{% tabs %}
{% highlight c# %}
//Initialize PDF Viewer.
PdfViewerControl pdfViewer = new PdfViewerControl();

// Load the PDF document. 
pdfViewer.Load("Sample.pdf");

// Occurs when the PDF document loaded. 
pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded; 
 
private void PdfViewer_DocumentLoaded(object sender, EventArgs args) 
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
{% endtabs %}