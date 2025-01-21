---
layout: post
title: Change annotation selection color in WPF Pdf Viewer | Syncfusion&reg;
description: Learn about Change the Selection color of the annotations support in Syncfusion<sup>&reg;</sup>; WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the Selection color of the annotations

PDF Viewer allows you to change the selection color of both the locked and unlocked annotations with the `SelectorSettings` property of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) classes. The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

// Change the selected stroke color of an unlocked annotation.
pdfViewer.SelectorSettings.StrokeColor = Color.FromArgb(255,255,0,0);
// Change the selected stroke color of a locked annotation.
pdfViewer.SelectorSettings.LockedStrokeColor = Color.FromArgb(255, 0, 255, 0);

{% endhighlight %}

{% highlight vbnet %}

' Change the selected stroke color of an unlocked annotation.
pdfViewer.SelectorSettings.StrokeColor = Color.FromArgb(255, 255, 0, 0)
' Change the selected stroke color of a locked annotation.
pdfViewer.SelectorSettings.LockedStrokeColor = Color.FromArgb(255, 0, 255, 0)

{% endhighlight %}
{% endtabs %}
