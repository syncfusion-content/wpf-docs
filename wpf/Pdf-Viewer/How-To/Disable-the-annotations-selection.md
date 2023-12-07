---
layout: post
title: Disable the annotations selection in WPF Pdf Viewer | Syncfusion
description: Learn about disabling the selection of annotations support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Disable the annotations selection

PDF Viewer allows you to enable or disable the annotations selection using the `Constraints` property programmatically. The following code snippet illustrates disabling the selection of the freetext annotations.

{% tabs %}
{% highlight c# %}

// Disable the selection of the free text annotations.
pdfViewer.FreeTextAnnotationSettings.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}

{% highlight vbnet %}

'Disable the selection of the free text annotations.
pdfViewer.FreeTextAnnotationSettings.Constraints = Not AnnotationConstraints.Selectable

{% endhighlight %}
{% endtabs %}

N>* Similarly, you can disable the selection for all other annotations.
N>* If you disable/enable the selection through a button, The changes will only be reflected to the annotations added after the button click.
