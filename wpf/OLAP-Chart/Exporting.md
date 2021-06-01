---
layout: post
title: Exporting in WPF Olap Chart control | Syncfusion
description: Learn about Exporting support in Syncfusion Essential Studio WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
 documentation: ug
---

# Exporting in WPF Olap Chart

An OLAP chart can be exported to various image and document formats. The following topics illustrate this in detail:

* Exporting as an image.
* Exporting to Word document.
* Exporting to PDF document.

## Exporting as an image

The OLAP chart can be copied to the clipboard or exported as an image. It can be exported in any one of the following image formats:

* Bitmap
* JPG
* PNG
* XPS
* GIF
* TIFF
* WDP

![Exports OlapChart into image format](Exporting_images/Exporting_img1.png)

## Exporting to Word document

The OLAP chart for WPF supports exporting an OLAP chart to an Microsoft Word document. It can also be exported into a template Word document file at a position specified by a marker.

The following methods are used to export an OLAP chart to a Microsoft Word document:

### Methods

* **ExportIntoNewDoc**: Exports a chart to a new Word document file with specified file name.
* **ExportIntoTemplateDoc**: Exports a chart to an existing Word document file in the default marker string location.
* **ExportIntoTemplateDoc**: Exports a chart to an existing Word document file in the given marker string location.
* **ExportIntoTemplateDoc**: Exports a chart to an existing instance of a Word document in the default marker string location.
* **ExportIntoTemplateDoc**: Exports a chart to an existing instance of a Word document in the marker string location.

The following code sample illustrates how to export an OLAP chart to a Microsoft Word document.

{% tabs %}

{% highlight c# %}
 
// Export the OlapChart into a new Word Document.
OlapChartWordExport olapChartWordExport = new OlapChartWordExport(this.olapChart);
olapChartWordExport.ExportintoNewDoc(@"..\..\OutputDocument\Document.doc");
// Export the OlapChart into a new Word Document file in the default marker string location.
OlapChartWordExport olapChartWordExport = new OlapChartWordExport(this.olapChart);
olapChartWordExport.ExportIntoTemplateDoc(@"..\..\OutputDocument\Document.doc");
// Export the OlapChart into an existing Word Document file in the given marker string location.
OlapChartWordExport olapChartWordExport = new OlapChartWordExport(this.olapChart);
olapChartWordExport.ExportIntoTemplateDoc(@"..\..\OutputDocument\Document.doc", "MarkerString1");

{% endhighlight %}

{% highlight vbnet %}
  
' Export the OlapChart into a new Word Document.
Dim olapChartWordExport As New olapChartWordExport(Me.olapChart)
olapChartWordExport.ExportintoNewDoc("..\..\OutputDocument\Document.doc")
' Export the OlapChart into a new Word Document file in the default marker string location.
Dim olapChartWordExport As New olapChartWordExport(Me.olapChart)
olapChartWordExport.ExportIntoTemplateDoc("..\..\OutputDocument\Document.doc")
' Export the OlapChart into an existing Word Document file in the given marker string location.
Dim olapChartWordExport As New olapChartWordExport(Me.olapChart)
olapChartWordExport.ExportIntoTemplateDoc("..\..\OutputDocument\Document.doc", "MarkerString1")

{% endhighlight %}

{% endtabs %}

![Exports OlapChart into word document](Exporting_images/Exporting_img2.png)

## Exporting to a PDF document

The OLAP chart that is exported to a Word document is inserted into a PDF document. The **ExportIntoNewPDF** method is used for this purpose.

The following code sample illustrates how to set this method.

{% tabs %}

{% highlight c# %}
 
OlapChartPdfExport chartPdfExport = new OlapChartPdfExport(this.olapChart);
chartPdfExport.ExportIntoNewPdf(@"..\..\TemplateDocument\PdfDocument.pdf");

{% endhighlight %}

{% highlight vbnet %}
  
Dim chartPdfExport As New OlapChartPdfExport(Me.olapChart)
chartPdfExport.ExportIntoNewPdf("..\..\TemplateDocument\PdfDocument.pdf")

{% endhighlight %}

{% endtabs %}

![Exports OlapChart into pdf document](Exporting_images/Exporting_img3.png)

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Exporting\Exporting Chart Demo

