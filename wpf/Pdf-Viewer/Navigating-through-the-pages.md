---
layout: post
title: Page Navigation in WPF Pdf Viewer control | Syncfusion
description: Learn about Page Navigation support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Page Navigation in WPF Pdf Viewer

PDF Viewer allows you to navigate through the pages of the PDF document using the [GotoPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_GotoPage_System_Int32_) method. The following code example illustrates the navigation to page 2 of the PDF document.

{% tabs %}
{% highlight C# %}

//Load the PDF.
pdfViewer.Load("Sample.pdf");
//Navigate to page 2
pdfViewer.GotoPage(2);

{% endhighlight %}

{% highlight vbnet %}

'Load the PDF.
pdfViewer.Load("Sample.pdf")
'Navigate to page 2
pdfViewer.GotoPage(2)

{% endhighlight %}
{% endtabs %}

## Navigate to the horizontal and vertical offset
You can now scroll to the given horizontal and vertical offset of the PDF document programmatically using the [ScrollTo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ScrollTo_System_Double_) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). Refer to the following code to scroll the PDF document to the horizontal and vertical offset of 160 and 400 respectively.

{% tabs %}
{% highlight C# %}

//Load the PDF.
pdfViewer.Load("Sample.pdf");
//Navigate to the horizontal and vertical offset of 160 and 400 respectively
pdfViewer.ScrollTo (160, 400);

{% endhighlight %}

{% highlight vbnet %}

'Load the PDF.
pdfViewer.Load("Sample.pdf")
'Navigate to the horizontal and vertical offset of 160 and 400 respectively
pdfViewer.ScrollTo (160, 400)

{% endhighlight %}
{% endtabs %}

N> Internally, the parameters (offset values) of this method will be multiplied by current zoom factor. So, the parameters (offset values) must be specified in terms of default zoom factor of 1, or 100% zoom.

{% tabs %}
{% highlight C# %}

// If the current zoom percentage is not 100, the parameter values must be divided by the zoom factor.
pdfViewer.ScrollTo (160d / ((double)pdfViewer.ZoomPercentage / 100d), 400d / ((double)pdfViewer.ZoomPercentage / 100d));

{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.