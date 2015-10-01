---
layout: post
title: Toggling-visibility-of-the-scroll-bar 
description: toggling visibility of the scroll bar 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggling visibility of the scroll bar

PDF Viewer supports showing and hiding scrollbar, when you feel to use the PDF Viewer only with the touch support, you can hide the default scrollbars of the PDF Viewer. The following code example hides the scrollbar in the PDF Viewer control.

{% tabs %}
{% highlight c# %}

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = false;


{% endhighlight %}


{% highlight vbnet %}

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = False

{% endhighlight %}
{% endtabs %}