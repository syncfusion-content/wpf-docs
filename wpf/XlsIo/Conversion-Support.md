---
layout: post
title: Conversion Support | XlsIO | WPF | Syncfusion
description: conversion support
platform: wpf
control: Xlsio
documentation: ug
---

# Conversion Support

Essential XlsIO supports converting workbook and worksheets into a Pdf document, an image. It also supports converting Excel charts into images. The following sections explains these.

## Export Excel to PDF 

Essential XlsIO allows exporting an Excel document into PDF format. Use the Convert method of the ExcelToPdfConverter class to convert the Excel spreadsheet and save the PDF output. 

N> You need to have both Essential PDF and Essential XlsIO installed in your system since Syncfusion.ExceltoPDFConverter.Base.dll is conditionally shipped when both XlsIO.Base and Pdf.Base is installed.
{% tabs %}
{% highlight C# %} 

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



//Opens the Excel Document to Convert.

ExcelToPdfConverter converter = new ExcelToPdfConverter(workbook);



//Intializes the PDFDocument.

PdfDocument pdfDoc = new PdfDocument();



//Intializes the ExcelToPdfconverterSettings.

ExcelToPdfConverterSettings settings = new ExcelToPdfConverterSettings();



//Converts Excel Document into PDF document.

pdfDoc = converter.Convert(settings);



//Saves the pdf file.

pdfDoc.Save("ExceltoPDF.pdf");


 {% endhighlight %}


{% highlight vbnet %} 

'Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



'Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)



'Opens the Excel Document to Convert.

Dim converter As ExcelToPdfConverter = New ExcelToPdfConverter(workbook)



'Intializes the PDFDocument.

Dim pdfDoc As PdfDocument = New PdfDocument()



'Intializes the ExcelToPdfconverterSettings.

Dim settings As ExcelToPdfConverterSettings = New ExcelToPdfConverterSettings()



'Converts Excel Document into PDF document.

pdfDoc = converter.Convert(settings)



'Saves the pdf file.

pdfDoc.Save("ExceltoPDF.pdf")

{% endhighlight %}
{% endtabs %}

###Supported Elements

This feature provides support for the following elements:

* Styles
* Character formatting
* Headers  and footers
* Images
* Text boxes
* Hyperlinks
* Document properties
* Comments
* Encryption
* TableStyle Support
* Text Rotations
* Excel Page Setup Options
* Unicode Support
* Background Images
* Printing Titles when Converting the Excel to PDF
* Page Break Support
* Print Area Support
* Print Order Support
* Unicode in Headers and Footers​

###Styles

This feature supports almost all the styles supported by Excel 2007.

###Character formatting

This feature supports almost all character formatting. The supported character formatting features are:

* Character fonts 
* Font size
* Font styles (bold, italic, underline, and strikethrough) 
* Subscript and superscript 
* Text highlighting 
* Indents, tabs, and spaces 
* Line spacing 
* Left, right, and center justification
* Line breaks within the cell

##Headers and Footers 

Page headers and footers are supported and can contain images, text, and page number fields. 

###Images 

The images present in the document are supported along with their corresponding positions and sizes. 

Known Limitation-Images placed inside a shape is not preserved in the generated PDF document. 

###Text Box 

The text value present in the text box is rendered as text at its actual position in the generated PDF document. 

###Hyperlinks

The hyperlinks present in the Excel documents is also preserved in the generated PDF document.

###Document Properties 

Document properties present in the Excel documents is also preserved in the generated PDF document. 

###Table Styles Support

Built-In Table styles present in the Excel documents is also preserved in the generated PDF document.

###Text Rotations

Rotated text present in the Excel sheet cell is preserved in the generated PDF document.

##Excel sheet Page Setup options

The Page setup option of the input Excel sheet is preserved in the generated PDF document. The following are the Excel page setup options that are preserved.

* Orientation
* Center On Page

###Unicode Support

The other language and unicode present in the input Excel document is preserved in the generated PDF document.

###Background Images

The Background image present in the Excel document is preserved in the generated PDF document.


N> The image gets tiled based on the size of the output pdf document.



###Comments

Comments present in the Excel document cells is also preserved in the generated PDF document. 

###Encryption

An encrypted Excel document is also preserved and generated as an encrypted PDF document by passing the password for the encrypted Excel document.

###Unsupported Elements 

The following list contains unsupported elements that presently is not preserved in the generated PDF document. 

* Grouping columns
* OLE Objects
* Text rotations
* Background images

##Printing Titles when Converting the Excel to PDF 

Title rows and columns in the Excel sheet can be printed on the PDF page by using this feature. By setting the print titles for rows and columns in the Excel sheet, the same gets reflected in the PDF when converting the Excel to PDF.

###Page Break Support

Manually inserted page breaks that are available in the Excel document is included while laying out the PDF document.nPrint Order Support.

###Print Order Support

The Print order enabled in the Excel document is considered while laying out the PDF page. The following are the page order options that are supported:

* Down Then Over
* Over Then Down

N> It considers the Print Area and Page breaks while laying out, based on Print Order.

###Print Area Support

Print Area available in the Excel document is considered while laying out the PDF document. Both, Row Index Only [1: 20] and Column Index Only [A: D] support have also been included in Unicode in Headers and Footers.

###Unicode in Headers and Footers

The other language and unicode present in the headers and footers is preserved in the generated PDF document.

For More Information refer to: AutoFilters, Validating Data, Template Markers, Grouping and Ungrouping, Print Settings.

## Convert Worksheet to Image 

Essential XlsIO can convert a worksheet to an image of type bitmap or metafile based on the input range of rows and columns with all basic formats preserved. The sheet can be converted and saved to disk or stream. The converted image can be inserted in a pdf by using Essential PDF.


{% tabs %}

{% highlight C# %} 


//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



// Converts as bitmap.

Image img = sheet.ConvertToImage(1, 1, 10, 20);

img.Save("Sample.png", ImageFormat.Png);



// Converts to MetaFile.

Image img = sheet.ConvertToImage(1, 1, 10, 20, ImageType.Metafile, null);

img.Save("Sample.emf", ImageFormat.Emf);



// Converts and saves as stream.

MemoryStream stream = new MemoryStream();

sheet.ConvertToImage(1, 1, 10, 20, ImageType.Metafile, stream);



//Saves the workbook to disk.
workbook.SaveAs("Sample.xlsx");

//Closes the workbook.
workbook.Close();

//No exception will be thrown if there are unsaved workbooks.
excelEngine.ThrowNotSavedOnDestroy = false;

excelEngine.Dispose();


 {% endhighlight %} 


{% highlight vbnet %} 

'Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



'Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)



'Converts as bitmap.

Dim img As Image = sheet.ConvertToImage(1, 1, 10, 20)

img.Save("Sample.png", ImageFormat.Png)



'Converts to Metafile.

Dim img As Image = sheet.ConvertToImage(1, 1, 10, 20, ImageType.Metafile, Nothing)

img.Save("Sample.emf", ImageFormat.Emf)



'Converts and saves as stream.

Dim stream As MemoryStream = New MemoryStream()

sheet.ConvertToImage(1, 1, 10, 20, ImageType.Metafile, stream)



'Saves the workbook to disk.
workbook.SaveAs("Sample.xlsx")

'Closes the workbook.
workbook.Close()

//No exception will be thrown if there are unsaved workbooks.
excelEngine.ThrowNotSavedOnDestroy = False

excelEngine.Dispose()

{% endhighlight %} 
{% endtabs %}

![](Conversion-Support_images/Conversion-Support_img4.jpeg)



Essential XlsIO can convert a worksheet based on the input range of the rows and columns that does not support the following elements:



* Subscript/Superscript
* RTF
* Shrink to fit
* Shapes (except TextBox shape and Image)
* Charts and Chart Worksheet
* Complex conditional formatting
* Gradient fill is partially supported


## Convert Chart to Image 


N> This section is applicable only to the Windows Forms and WPF platforms of XlsIO.
N>
N> For Windows Forms platform, you must add additional references to the following DLLs: PresentationFramework.dll and PresentationCore.dll.



Essential XlsIO provides support to convert a Chart in Microsoft Excel to an image. This can be done by using the ExcelChartToImageConverter class. To render a Chart in Excel as an image, you must add references to the following DLLs in your application:

* Syncfusion.ExcelChartToImageConverter.Wpf.dll
* Syncfusion.SfChart.Wpf.dll
* Syncfusion.Shared.Wpf.dll
* Syncfusion.XlsIO.Base.dll
* Syncfusion.Compression.Base.dll
* Syncfusion.Core.dll

The following code example illustrates converting an Excel Chart to an image.


{% tabs %}

{% highlight C# %} 


//Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



//Step 2: Instantiates the Excel application object.

IApplication application = excelEngine.Excel;



//Step 3: Instantiates the ChartToImageConverter.

ChartToImageConverter chartToImageConverter = new ChartToImageConverter();



//Step 4: Assigns the ChartToImageConverter instance to XlsIO.

application.ChartToImageConverter = chartToImageConverter;



//Step 5: Tuning Chart Image Quality.

application.ChartToImageConverter.ScalingMode = ScalingMode.Best;



//Opens the Workbook and assigns the worksheet to IWorksheet.

IWorkbook workbook = application.Workbooks.Open("input.xlsx");

IWorksheet worksheet = workbook.Worksheets[0];



//Assigns the worksheet to IChart.

IChart chart = worksheet.Charts[0];



//Creates the memory stream for chart image.

MemoryStream stream = new MemoryStream();



//Saves the chart as image.

chart.SaveAsImage(stream);

Image image = Image.FromStream(stream);



//Saves image stream to file.

image.Save("output.png");



//Closes the workbook and disposing the Excel Engine.

workbook.Close();

excelEngine.Dispose();

{% endhighlight %} 

{% highlight vbnet %} 

'Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As New ExcelEngine()



'Step 2: Instantiates the Excel application object.

Dim application As IApplication = excelEngine.Excel



'Step 3: Instantiates the ChartToImageConverter.

Dim ChartToImageConverter As chartToImageConverter = New ChartToImageConverter()



'Step 4: Assigns the ChartToImageConverter instance to XlsIO.

application.ChartToImageConverter = chartToImageConverter



'Step 5: Tuning Chart Image Quality.

application.ChartToImageConverter.ScalingMode = ScalingMode.Best



'Opens the Workbook and assigns the worksheet to IWorksheet.

Dim workbook As IWorkbook = application.Workbooks.Open("input.xlsx")

Dim worksheet As IWorksheet = workbook.Worksheets(0)



'Assigns the worksheet to IChart.

Dim chart As IChart = worksheet.Charts(0)



'Creates the memory stream for chart image.

Dim stream As New MemoryStream()



'Saves the chart as image.

chart.SaveAsImage(stream)

Dim image__1 As Image = Image.FromStream(stream)



'Saves image stream to file.

image__1.Save("output.png")



'Closes the workbook and disposes the Excel Engine.

workbook.Close()

excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}

The following screenshot shows an Excel Chart converted to an image.



![](Conversion-Support_images/Conversion-Support_img6.jpeg)



