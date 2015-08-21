---
layout: post
title: Exporting-PDF 
description: exporting pdf 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting PDF

## Exporting PDFs as Raster Images

Essential PDF Viewer allows selected pages to be exported as raster images. Exporting can be done using the ExportAsImage method. This option helps to convert a PDF into an image.

{% highlight C# %}

Bitmap img = pdfViewer1.ExportAsImage(0);



// Save the image.

img.Save("Sample.png", ImageFormat.Png);

{% endhighlight %}

{% highlight vbnet %}

Dim img As Bitmap = pdfViewer1.ExportAsImage(0)



' Save the image.

img.Save("Sample.png", ImageFormat.Png)

{% endhighlight %}

You can also specify the page range instead of converting each page.

{% highlight C# %}

Bitmap[] img = pdfViewer1.ExportAsImage(0, 3);
{% endhighlight %}


{% highlight vbnet %}

Dim img() As Bitmap = pdfViewer1.ExportAsImage(0, 3)
{% endhighlight %}

### Exporting PDFs as Vector Images

Exporting PDFs as vector images can be done using the ExportAsMetafile method. The following code sample demonstrates how a PDF document can be exported as a metafile.

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

You can also specify the page range instead of converting each page individually.

{% highlight C# %}

Metafile[] img = pdfViewer1.ExportAsMetafile(0, 3);

{% endhighlight %}

{% highlight vbnet %}

Dim img() As Metafile = pdfViewer1.ExportAsMetafile(0, 3)

{% endhighlight %}