---
layout: post
title: Magnifying PDF documents | PDF Viewer | Wpf | Syncfusion
description: magnifying pdf documents. This article describes how the PDF viewer is used to magnify the PDF document.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Magnifying PDF documents

PDF Viewer allows you to magnify the PDF document that is being displayed using t\he [ZoomTo](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ZoomTo.html) method. The following code examples can be used to perform this action.

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

//Magnify the document to 150%

pdfviewer1.ZoomTo(150);
{% endhighlight %}


{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Magnify the document to 150%

pdfviewer1.ZoomTo(150)

{% endhighlight %}
{% endtabs %}

The magnification can also be set by updating the Zoom property of the PDF Viewer.
{% tabs %}
{% highlight c# %}

//Magnify the document to 150%

pdfviewer1.Zoom = 250;

{% endhighlight %}

{% highlight vbnet %}

'Magnify the document to 150%

pdfviewer1.Zoom = 250

{% endhighlight %}
{% endtabs %}

Current magnification percentage of the PDF Viewer can be acquired with the use of the property ZoomPercentage
{% tabs %}
{% highlight c# %}

//Acquire current zoom percentage

int currentZoomPercentage = pdfviewer1.ZoomPercentage;

{% endhighlight %}

{% highlight vbnet %}

' Acquire current zoom percentage 

Dim currentZoomPercentage As Integer = pdfviewer1.ZoomPercentage

{% endhighlight %}
{% endtabs %}

Zoom mode of the PDF viewer can be set using the following code example.
{% tabs %}
{% highlight c# %}

//Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth;
{% endhighlight %}


{% highlight vbnet %}

'Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth

{% endhighlight %}
{% endtabs %}