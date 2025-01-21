---
layout: post
title: Toggle visibility of the tool bar in WPF Pdf Viewer | Syncfusion<sup>&reg;</sup>;
description: Learn about Toggle visibility of the tool bar support in Syncfusion<sup>&reg;</sup>; WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggle visibility of the tool bar in WPF Pdf Viewer

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer using the [ShowToolbar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowToolbar) property. The following code example hides the default toolbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}
// Hide the default (top) toolbar of the PDF Viewer
pdfViewer.ShowToolbar = false;
{% endhighlight %}

{% highlight vbnet %}
' Hiding the default toolbar of the PDF Viewer
pdfViewer.ShowToolbar = False
{% endhighlight %}
{% endtabs %}

## Expand the Annotation toolbar by programmatically.

The annotation toolbar is a secondary toolbar of PDF Viewer control that contains a collection of annotation buttons. By default, this annotation toolbar will be collapsed. To expand annotation toolbar at runtime, the user can click show annotations button, which is present in the primary toolbar. In order to expand annotation toolbar at loading or by programmatically, the user can just enable the isChecked property in annotations button as true. The following code example shows how to expands the annotation toolbar by programmatically in the PDF Viewer control.

{% tabs %}
{% highlight c# %}
private void ExpandAnnotationToolbar() 
{ 
	// Get the instance of the toolbar using its template name. 
	DocumentToolbar toolbar = pdfViewer.Template.Findname("PART_Toolbar", pdfViewer) as DocumentToolbar;
	// Get the instance of the annotation button using its template name. 
	ToggleButton annotationButton = (ToggleButton)toolbar.Template.Findname("PART_Annotations", toolbar);
	// Expand the annotation toolbar. 
	annotationButton.IsChecked = true; 
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub ExpandAnnotationToolbar()
    ' Get the instance of the toolbar using its template name.
    Dim toolbar As DocumentToolbar = TryCast(pdfViewer.Template.Findname("PART_Toolbar", pdfViewer), DocumentToolbar)
	' Get the instance of the annotation button using its template name. 
	Dim annotationButton As ToggleButton = CType(toolbar.Template.Findname("PART_Annotations", toolbar), ToggleButton)
	' Expand the annotation toolbar. 
	annotationButton.IsChecked = True
End Sub
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

N> The sample project for disabling top and left toolbar is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-PDFViewer-Examples/tree/master/Toolbar/HideToolbar).
