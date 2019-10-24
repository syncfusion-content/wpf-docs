---
layout: post
title: View the PDF stream in viewer| PDF Viewer | Wpf | Syncfusion
description: view the pdf stream in viewer
platform: wpf
control: PDF Viewer
documentation: ug
---

# View the PDF stream in viewer

PDF files as stream can be viewed in Essential PDF Viewer using the overload available in the [Load](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~Load(Stream).html) method. Use the following code example to load the PDF streams in viewer:

{% tabs %}
{% highlight c# %}

FileStream stream = new FileStream("Template.pdf", FileMode.Open);

//Initialize PDF Viewer

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF

pdfViewer1.Load(stream);
{% endhighlight %}


{% highlight vbnet %}

Dim stream As New FileStream("Template.pdf", FileMode.Open)



'Initialize PDF Viewer

Dim pdfViewer1 As New PdfViewerControl()



'Load the PDF

pdfViewer1.Load(stream)

{% endhighlight %}
{% endtabs %}

