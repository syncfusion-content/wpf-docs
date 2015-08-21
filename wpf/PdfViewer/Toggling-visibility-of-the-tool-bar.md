---
layout: post
title: Toggling-visibility-of-the-tool-bar
description: toggling visibility of the tool bar
platform: wpf
control: PDF Viewer
documentation: ug
---

# Toggling visibility of the tool bar

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer. The following code example hides the default toolbar in the PDF Viewer control.

{% highlight c# %}

// Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = false;
{% endhighlight %}




{% highlight vbnet %}

' Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = False

{% endhighlight %}