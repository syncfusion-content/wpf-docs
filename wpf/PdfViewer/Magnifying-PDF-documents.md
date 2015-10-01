---
layout: post
title: Magnifying-PDF-documents 
description: magnifying pdf documents
platform: wpf
control: PDF Viewer
documentation: ug
---

# Magnifying PDF documents

PDF Viewer allows you to magnify the PDF document that is being displayed. The following code examples can be used to perform this action.

{% tabs %}
{% highlight c# %}

//Magnify the document to 150%

pdfviewer1.ZoomTo(150);
{% endhighlight %}


{% highlight vbnet %}

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