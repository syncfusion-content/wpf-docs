---
layout: post
title: Navigating through the pages | PDF Viewer | Wpf | Syncfusion
description: Navigate through the pages or to a desired location in a PDF file programmatically using Syncfusion PDF Viewer WPF.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Navigating through the pages

PDF Viewer allows you to navigate through the pages of the PDF document using the [GotoPage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~GotoPage.html) method. The following code example illustrates the navigation to page 2 of the PDF document.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");


//Navigate to page 2

pdfviewer1.GotoPage(2);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

'Navigate to page 2

pdfviewer1.GotoPage(2)

{% endhighlight %}
{% endtabs %}

## Navigate to the horizontal and vertical offset
You can now scroll to the given horizontal and vertical offset of the PDF document programmatically using the [ScrollTo](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ScrollTo(Double,Double).html) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl.html). Refer to the following code to scroll the PDF document to the horizontal and vertical offset of 160 and 400 respectively.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.
PdfViewerControl pdfViewer1 = new PdfViewerControl();

//Load the PDF.
pdfViewer1.Load("Sample.pdf");

//Navigate to the horizontal and vertical offset of 160 and 400 respectively
pdfViewer1.ScrollTo (160, 400);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.
Private pdfViewer1 As New PdfViewerControl()

'Load the PDF.
pdfViewer1.Load("Sample.pdf")

'Navigate to the horizontal and vertical offset of 160 and 400 respectively
pdfViewer1.ScrollTo (160, 400)

{% endhighlight %}
{% endtabs %}