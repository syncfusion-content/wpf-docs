---
layout: post
title: How to merge several Excel files to a single file | XlsIO | WPF | Syncfusion
description:  How to merge several Excel files to a single file
platform: wpf
control: Xlsio
documentation: ug
---

# How to merge several Excel files to a single file

XlsIO provides support to merge several Excel files to a single file. The following code example illustrates how to do this.

{% tabs %} 
{% highlight C# %}

 //Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorkbook destinationWorkbook=application.Workbooks.Create();
IWorksheet sheet = workbook.Worksheets[0];
 
//Merges worksheets.
destinationWorkbook.Worksheets.AddCopy(sourceWorkbook.Worksheets);
 
string fileName = "Output.xlsx";
workbook.Version = ExcelVersion.Excel2010;
 
workbook.SaveAs(fileName);
 
// Closes the workbook.
workbook.Close();
excelEngine.Dispose(); 
{% endhighlight %}    


{% highlight vbnet %}
 
 
'Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine

 

'Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel

 

Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)

 

Dim destinationWorkbook As IWorkbook = application.Workbooks.Create(1);

' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)

 

'Merges worksheets.

destinationWorkbook.Worksheets.AddCopy(sourceWorkbook.Worksheets)

 

Dim fileName As String = "Output.xlsx"

workbook.SaveAs(fileName)

 

' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}

