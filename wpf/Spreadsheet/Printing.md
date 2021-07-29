---
layout: post
title: Printing in WPF Spreadsheet control | Syncfusion
description: Learn here all about Printing support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Printing in WPF Spreadsheet (SfSpreadsheet)

SfSpreadsheet control allows you to print the data in the workbook with the help of PDF Conversion. To provide the printing support in SfSpreadsheet, you need to convert the workbook into PDF document using ExcelToPdfConverter.

For Conversion of Excel Workbook in SfSpreadsheet to PDF document, use [Convert](https://help.syncfusion.com/cr/wpf/Syncfusion.ExcelToPdfConverter.ExcelToPdfConverter.html#Syncfusion_ExcelToPdfConverter_ExcelToPdfConverter_Convert) method of [ExcelToPdfConverter](http://help.syncfusion.com/cr/wpf/Syncfusion.ExcelToPdfConverter.ExcelToPdfConverter.html).

For viewing the PDF document, you can use [PdfViewerControl](http://help.syncfusion.com/wpf/pdfviewer/getting-started) to load the saved PDF stream.

{% tabs %}
{% highlight c# %}
//Create the pdf viewer for load the document.
PdfViewerControl pdfViewer = new PdfViewerControl();

//Create Memory Stream to save pdf document
MemoryStream pdfStream = new MemoryStream();
ExcelToPdfConverter converter = new ExcelToPdfConverter (spreadsheet.Workbook);  

//Initialize the ExcelToPdfConverter Settings
ExcelToPdfConverterSettings settings = new ExcelToPdfConverterSettings(); 
settings.LayoutOptions = LayoutOptions.NoScaling;
{% endhighlight %}
{% endtabs %}

For print preview you can load the PDF stream into viewer and for direct printing use `Print` method in PdfViewerControl  which is available under the namespace “Syncfusion.PdfViewer.Wpf”

{% tabs %}
{% highlight c# %}
//Initialize the PdfDocument
PdfDocument pdfDoc = new PdfDocument ();

//Assign the PdfDocument to the templateDocument property of ExcelToPdfConverterSettings  
settings.TemplateDocument = pdfDoc;
settings.DisplayGridLines = GridLinesDisplayStyle.Invisible;

//Convert Excel Document into PDF document
pdfDoc = converter.Convert(settings);

//Save the PDF file     
pdfDoc.Save(pdfStream);

//Load the document to pdf viewer
pdfViewer.Load(pdfStream);

//Print the doc
pdfViewer.Print(true);
{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.