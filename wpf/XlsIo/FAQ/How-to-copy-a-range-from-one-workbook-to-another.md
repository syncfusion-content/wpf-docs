---
layout: post
title: How to copy a range from one workbook to another | XlsIO | WPF | Syncfusion
description:  How to copy a range from one workbook to another
platform: wpf
control: Xlsio
documentation: ug
---

# How to copy a range from one workbook to another

The Range and CopyTo methods include overloads for copying the Source Worksheet range to the Destination Worksheet range. The following code example illustrates how to copy a range from one workbook to another workbook.

{% tabs %} 
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook sourceWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorkbook destinationWorkbook = application.Workbooks.Open("Sample1.xlsx", ExcelOpenType.Automatic);
 
IWorksheet SourceWorksheet = SourceWorkbook.Worksheets[0];
 
//The first worksheet object in the worksheets collection in the Destination Workbook is accessed.
IWorksheet DestinationWorksheet = DestinationWorkbook.Worksheets[0];
 
//Assigns an object to the range of cells (90 rows) both for source and destination.
IRange source = SourceWorksheet.Range[1, 1, 90, 100];
IRange des = DestinationWorksheet.Range[1, 1, 90, 100];
 
//Copies (90 rows) from Source to Destination worksheet.
source.CopyTo(des);
 
string fileName = "Output.xlsx";
destinationWorkbook.SaveAs(fileName);
 
// Closes the workbook.
destinationWorkbook.Close();
excelEngine.Dispose();        
    
{% endhighlight %}    


{% highlight vbnet %}
  
'Step 1: Instantiates the spreadsheet creation engine.
Dim excelEngine As ExcelEngine = New ExcelEngine
 
'Step 2: Instantiates the excel application object.
Dim application As IApplication = excelEngine.Excel
 
Dim sourceWorkbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)
 
Dim destinationWorkbook As IWorkbook = application.Workbooks.Open("sample1.xlsx", ExcelOpenType.Automatic)
 
'The first worksheet object in the worksheets collection in the Source Workbook is accessed.
Dim SourceWorksheet As Syncfusion.XlsIO.IWorksheet = SourceWorkbook.Worksheets(0)
 
'The first worksheet object in the worksheets collection in the Destination Workbook is accessed.
Dim DestinationWorksheet As Syncfusion.XlsIO.IWorksheet = DestinationWorkbook.Worksheets(0)
 
'Assigns an object to the range of cells (90 rows) both for source and destination.
Dim source As Syncfusion.XlsIO.IRange = SourceWorksheet.Range(1, 1, 90, 100)
Dim des As Syncfusion.XlsIO.IRange = DestinationWorksheet.Range(1, 1, 90, 100)
 
'Copies (90 rows) from Source to Destination worksheet.
source.CopyTo(des)
 
Dim fileName As String = "Output.xlsx"
destinationWorkbook.SaveAs(fileName)
 
' Closes the workbook.
destinationWorkbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}