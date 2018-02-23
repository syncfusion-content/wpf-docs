---
layout: post
title: Exporting PDF | PDF Viewer | Wpf | Syncfusion
description: exporting pdf 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting PDF

## Exporting PDFs as Raster Images

Essential PDF Viewer allows selected pages to be exported as raster images. Exporting can be done using the ExportAsImage method. This option helps to convert a PDF into an image.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Template.pdf");

Bitmap img = pdfViewer1.ExportAsImage(0);



// Save the image.

img.Save("Sample.png", ImageFormat.Png);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Template.pdf")

Dim img As Bitmap = pdfViewer1.ExportAsImage(0)



' Save the image.

img.Save("Sample.png", ImageFormat.Png)

{% endhighlight %}
{% endtabs %}

You can also specify the page range instead of converting each page.

{% tabs %}
{% highlight C# %}

Bitmap[] img = pdfViewer1.ExportAsImage(0, 3);
{% endhighlight %}


{% highlight vbnet %}

Dim img() As Bitmap = pdfViewer1.ExportAsImage(0, 3)
{% endhighlight %}
{% endtabs %}

### Exporting PDFs as Vector Images

Exporting PDFs as vector images can be done using the ExportAsMetafile method. The following code sample demonstrates how a PDF document can be exported as a Metafile.

{% tabs %}
{% highlight C# %}

Metafile img = pdfViewer1.ExportAsMetafile(0);



// Save the image

img.Save("Sample.emf", ImageFormat.Emf);

{% endhighlight %}

{% highlight vbnet %}

Dim img As Metafile = pdfViewer1.ExportAsMetafile(0)



' Save the image

img.Save("Sample.emf", ImageFormat.Emf)

{% endhighlight %}
{% endtabs %}

You can also specify the page range instead of converting each page individually.

{% tabs %}
{% highlight C# %}

Metafile[] img = pdfViewer1.ExportAsMetafile(0, 3);

{% endhighlight %}

{% highlight vbnet %}

Dim img() As Metafile = pdfViewer1.ExportAsMetafile(0, 3)

{% endhighlight %}
{% endtabs %}