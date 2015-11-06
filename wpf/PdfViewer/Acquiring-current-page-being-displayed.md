---
layout: post
title: Acquiring current page being displayed| PDF Viewer | Wpf | Syncfusion
description: acquiring current page being displayed 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Acquiring current page being displayed

PDF Viewer supports acquiring the index of the page being displayed in the PDF Viewer at any moment. The following code example illustrates the same.

{% tabs %}
{% highlight C# %}

// Acquiring the number of page being displayed in the Viewer  

int pageCount = pdfviewer1.CurrentPageIndex;


{% endhighlight %}


{% highlight vbnet %}

' Acquiring the number of page being displayed in the Viewer  

Dim pageCount As Integer = pdfviewer1. CurrentPageIndex

{% endhighlight %}
{% endtabs %}