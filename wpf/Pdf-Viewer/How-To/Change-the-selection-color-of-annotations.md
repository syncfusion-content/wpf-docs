---
layout: post
title: Change the Selection color of the annotations in WPF Pdf Viewer | Syncfusion
description: Learn about Change the Selection color of the annotations support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Change the Selection color of the annotations

PdfViewer allows you to change the selection color of both the locked and unlocked annotations with the `SelectorSettings` API of the PdfViewerControl and PdfDocumentView classes. The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

// Stroke color changes the selection color of the unlocked annotation.
pdfViewer.SelectorSettings.StrokeColor = Color.FromArgb(255,255,0,0);
// Locked Stroke color changes the selection color of the locked annotation.
pdfViewer.SelectorSettings.LockedStrokeColor = Color.FromArgb(255, 0, 255, 0);

{% endhighlight %}

{% highlight vbnet %}

' Stroke color changes the selection color of the unlocked annotation.
pdfViewer.SelectorSettings.StrokeColor = Color.FromArgb(255, 255, 0, 0)
' Locked Stroke color changes the selection color of the locked annotation.
pdfViewer.SelectorSettings.LockedStrokeColor = Color.FromArgb(255, 0, 255, 0)

{% endhighlight %}
{% endtabs %}
