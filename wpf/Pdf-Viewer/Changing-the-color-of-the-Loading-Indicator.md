---
layout: post
title: Change the color of the Loading Indicator in Pdf Viewer | Syncfusion
description: Learn about Change the color of the Loading Indicator support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the color of the Loading Indicator in WPF Pdf Viewer

PDF Viewer allows you to change the color of the loading indicator displayed when loading the PDF document. The following code example illustrates the same.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

// Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0);
{% endhighlight %}



{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0)

{% endhighlight %}
{% endtabs %}
