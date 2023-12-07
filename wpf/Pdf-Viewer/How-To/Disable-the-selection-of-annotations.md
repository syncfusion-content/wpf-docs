---
layout: post
title: Disable the selection of annotations in WPF Pdf Viewer | Syncfusion
description: Learn about disabling the selection of annotations support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable the selection of annotations

PDFViewer allows you to enable or disable the selection of annotations using the `Constraints` API programmatically. The following code snippet illustrates disabling the selection of the freetext annotations.

{% tabs %}
{% highlight c# %}

// Disables the selection of the Freetext annotations.
pdfViewer.FreeTextAnnotationSettings.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}

{% highlight vbnet %}

'Disables the selection of the Freetext annotations.
pdfViewer.FreeTextAnnotationSettings.Constraints = Not AnnotationConstraints.Selectable

{% endhighlight %}
{% endtabs %}

N>* Similarly, you can disable the selection for all other annotations.
N>* If you disable/enable it with a button click, The changes will only be reflected in the newly added annotation.
