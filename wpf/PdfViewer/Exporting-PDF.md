---
layout: post
title: Exporting-PDF 
description: exporting pdf 
platform: wpf
control: PDF Viewer
documentation: ug
---

### Exporting PDF

#### Exporting PDFs as Raster Images

Essential PDF Viewer allows selected pages to be exported as raster images. Exporting can be done using the ExportAsImage method. This option helps to convert a PDF into an image.

[C#]

Bitmap img = pdfViewer1.ExportAsImage(0);



// Save the image.

img.Save("Sample.png", ImageFormat.Png);



[VB.NET]

Dim img As Bitmap = pdfViewer1.ExportAsImage(0)



' Save the image.

img.Save("Sample.png", ImageFormat.Png)



You can also specify the page range instead of converting each page.

[C#]

Bitmap[] img = pdfViewer1.ExportAsImage(0, 3);



[VB.NET]

Dim img() As Bitmap = pdfViewer1.ExportAsImage(0, 3)

#### Exporting PDFs as Vector Images

Exporting PDFs as vector images can be done using the ExportAsMetafile method. The following code sample demonstrates how a PDF document can be exported as a metafile.

[C#]

Metafile img = pdfViewer1.ExportAsMetafile(0);



// Save the image

img.Save("Sample.emf", ImageFormat.Emf);



[VB.NET]

Dim img As Metafile = pdfViewer1.ExportAsMetafile(0)



' Save the image

img.Save("Sample.emf", ImageFormat.Emf)



You can also specify the page range instead of converting each page individually.

[C#]

Metafile[] img = pdfViewer1.ExportAsMetafile(0, 3);



[VB.NET]

Dim img() As Metafile = pdfViewer1.ExportAsMetafile(0, 3)

