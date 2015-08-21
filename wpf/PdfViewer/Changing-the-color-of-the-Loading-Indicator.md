---
layout: post
title: Changing-the-color-of-the-Loading-Indicator 
description: changing the color of the loading indicator 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Changing the color of the Loading Indicator

PDF Viewer allows you to change the color of the loading indicator displayed when loading the PDF document. The following code example illustrates the same.

{% highlight C# %}

// Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0);
{% endhighlight %}



{% highlight vbnet %}

'Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0)

{% endhighlight %}
