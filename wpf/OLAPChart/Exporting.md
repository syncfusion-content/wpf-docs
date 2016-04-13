---
layout: post
title: Exporting| OLAP Chart | Wpf | Syncfusion
description: Exporting
platform: wpf
control: OLAP Chart
documentation: ug
---

# Exporting

OLAP Chart can be exported into various image and document formats. The following topics illustrate this in detail:

* Exporting as an Image
* Exporting to Word Document
* Exporting to PDF Document

A sample, which demonstrates the Chart Export feature, is available in the following installation. location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Export and Print\Exporting Chart Demo

## Exporting as an Image

An OLAP Chart can be copied to the clipboard or exported as an image. It can be exported in any one of the following image formats:

* Bitmap (.bmp)
* JPG
* PNG
* XPS
* GIF
* TIFF
* WDP

A sample, which demonstrates this feature, is available in the following sample installation location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Export and Print\Exporting Chart Demo

## Exporting to Word Document

Essential BI OLAP Chart for WPF supports exporting an OLAP Chart into an Microsoft Word Document. It can also be exported into a Template Word Document file at a position specified by a marker.

The following methods are used to export an OLAP Chart to an Microsoft Word Document:

### Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th></tr>
<tr>
<td>
ExportIntoNewDoc(string filename)</td><td>
Exports a chart into a new Word Document file with the specified file name. It takes the file name as the parameter.</td></tr>
<tr>
<td>
ExportIntoTemplateDoc(string filename)</td><td>
Exports a chart into an existing Word Document file in the default marker string location. If the default marker string is not found, then the insertion will take place at the end of the document file. It takes the existing document file name as the parameter.</td></tr>
<tr>
<td>
ExportIntoTemplateDoc(string filename, string marker)</td><td>
Exports a chart into an existing Word Document file in the given marker string location.</td></tr>
<tr>
<td>
ExportIntoTemplateDoc(WordDocument document)</td><td>
Exports a chart into an existing instance of a Word Document in the default marker string location. If the marker string is not found, then exporting will be done at the end of the document's instance. It takes the existing document instance as the parameter.</td></tr>
<tr>
<td>
ExportIntoTemplateDoc(WordDocument document, string Marker)</td><td>
Exports a chart into an existing instance of a Word Document in the marker string location. It takes the document instance and the marker string as the parameters.</td></tr>
</table>
The following code examples illustrate how to export an OLAP Chart to an Microsoft Word Document:


 {% highlight c# %}
 
    

    // Export the OLAP Chart into a new Word Document.
    this.olapchart1.ExportintoNewDoc(@"..\..\OutputDocument\Document.doc");

    // Export the OLAP Chart into a new Word Document file in the default marker string location.
    this.olapchart1.ExportIntoTemplateDoc(@"..\..\OutputDocument\Document.doc");

    // Export the OLAP Chart into an existing Word Document file in the given marker string location.
    this.olapchart1.ExportIntoTemplateDoc(@"..\..\OutputDocument\Document.doc", 

    "MarkerString1");



 {% endhighlight %}


 {% highlight vbnet %}
  
    
    

    ' Export the OLAP Chart into a new Word Document.
    Me.olapchart1.ExportintoNewDoc("..\..\OutputDocument\Document.doc")

    ' Export the OLAP Chart into a new Word Document file in the default marker string location.
    Me.olapchart1.ExportIntoTemplateDoc("..\..\OutputDocument\Document.doc")

    ' Export the OLAP Chart into an existing Word Document file in the given marker string location.
    Me.olapchart1.ExportIntoTemplateDoc("..\..\OutputDocument\Document.doc",

    "MarkerString1")

 {% endhighlight %}


![](Core-Features_images/Core-Features_img44.png)


A sample, which demonstrates this feature, is available in the following sample installation location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Export and Print\Exporting Chart Demo



## Exporting to a PDF Document

An OLAP Chart exported into a Word Document can also be inserted into a PDF document created by using the Back Office studio. The ExportIntoNewPDF method is used for this purpose. The following code example illustrates how to set this method:

 {% highlight c# %}
 
    

    this.olapchart1.ExportIntoNewPdf(@"..\..\TemplateDocument\PdfDocument.pdf");

 {% endhighlight %}




 {% highlight vbnet %}
  
    

    Me.olapchart1.ExportIntoNewPdf("..\..\TemplateDocument\PdfDocument.pdf")

 {% endhighlight %}








![](Core-Features_images/Core-Features_img45.png)


A sample, which demonstrates this feature, is available in the following sample installation location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Export and Print\Exporting Chart Demo
