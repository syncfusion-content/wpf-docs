---
layout: post
title: How to copy and paste the values of the cells that contain only formulas | XlsIO | WPF | Syncfusion
description:  How to copy and paste the values of the cells that contain only formulas
platform: wpf
control: Xlsio
documentation: ug
---

# How to copy and paste the values of the cells that contain only formulas

You can copy and paste the values of the cells that contain only formulas by setting ExcelCopyRangeOptions of the CopyTo method to None. The following code example illustrates this.

{% tabs %} 

{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
IRange src = sheet.Range["A3"];
IRange dest = sheet.Range["B1"];
src.CopyTo(dest, ExcelCopyRangeOptions.None);
 
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

 

' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)

 

Dim src As IRange = sheet.Range("A3")

Dim dest As IRange = sheet.Range("B1")

src.CopyTo(dest, ExcelCopyRangeOptions.None)

 

Dim fileName As String = "Output.xlsx"

workbook.SaveAs(fileName)

 

' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}