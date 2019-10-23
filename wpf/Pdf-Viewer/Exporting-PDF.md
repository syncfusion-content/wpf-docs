---
layout: post
title: Exporting PDF | PDF Viewer | Wpf | Syncfusion
description: Convert pages of a PDF file into JPG, PNG, TIFF, and BMP formats using PDF Viewer WPF. The scaler exportation comes with the customization of dimension and DPI. 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting PDF

## Exporting PDFs as Raster Images

Essential PDF Viewer allows selected pages to be exported as raster images. Exporting can be done using the [ExportAsImage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ExportAsImage(Int32).html) method. This option helps to convert a PDF into an image.

{% tabs %}
{% highlight C# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Sample.pdf");

Bitmap img = pdfViewer1.ExportAsImage(0);



// Save the image.

img.Save("Sample.png", ImageFormat.Png);

{% endhighlight %}

{% highlight vbnet %}

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Sample.pdf")

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