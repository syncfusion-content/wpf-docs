---
layout: post
title: Printing in SfSpreadsheet
description: How to print the workbook in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Printing

SfSpreadsheet control allows you to print the data in the workbook with the help of PDF Conversion. To provide the printing support in SfSpreadsheet, you need to convert the workbook into PDF document using ExcelToPdfConverter.

For Conversion of Excel Workbook in SfSpreadsheet to PDF document, use [Convert](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.ExcelToPDFConverter.Base~Syncfusion.ExcelToPdfConverter.ExcelToPdfConverter~Convert.html) method of [ExcelToPdfConverter](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.ExcelToPDFConverter.Base~Syncfusion.ExcelToPdfConverter.ExcelToPdfConverter.html).

For viewing the PDF document, you can use [PdfViewerControl](http://help.syncfusion.com/wpf/pdfviewer/getting-started) to load the saved PDF stream.

{% highlight c# %}

//Create the pdfviewer for load the document.

 PdfViewerControl pdfviewer = new PdfViewerControl();

//Create Memory Stream to save pdfdocument

 MemoryStream pdfstream = new MemoryStream();

 ExcelToPdfConverter converter = new ExcelToPdfConverter (spreadsheet.Workbook);  

//Intialize the ExcelToPdfConverter Settings

 ExcelToPdfConverterSettings settings = new ExcelToPdfConverterSettings(); 
	
 settings.LayoutOptions = LayoutOptions.NoScaling;

{% endhighlight %}

For print preview you can load the PDF stream into viewer and for direct printing use `Print` method in PdfViewerControl  which is available under the namespace “Syncfusion.PdfViewer.Wpf”

{% highlight c# %}

//Intialize the PdfDocument

 PdfDocument pdfDoc = new PdfDocument ();

//Assign the PdfDocument to the templateDocument property of ExcelToPdfConverterSettings  
	
 settings.TemplateDocument = pdfDoc;

 settings.DisplayGridLines = GridLinesDisplayStyle.Invisible;

//Convert Excel Document into PDF document

 pdfDoc = converter.Convert(settings);

//Save the PDF file     

 pdfDoc.Save(pdfstream);

//Load the document to pdfviewer

 pdfviewer.Load(pdfstream);

//Print the doc

 pdfviewer.Print(true);

{% endhighlight %}

