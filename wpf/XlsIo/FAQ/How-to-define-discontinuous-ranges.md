---
layout: post
title: How to define discontinuous ranges | XlsIO | WPF | Syncfusion
description:  How to define discontinuous ranges
platform: wpf
control: Xlsio
documentation: ug
---

# How to define discontinuous ranges

You can set a discontinuous range by adding different ranges to the Range collection. The following code example illustrates this.

{% tabs %}
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Creates Range collection.
IRanges rangesOne = sheet.CreateRangesCollection();
 
//Adds different ranges to the Range collection.
rangesOne.Add(sheet.Range["D2:D3"]);
rangesOne.Add(sheet.Range["D10:D11"]);
 
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
 
'Accesses via index.
Dim sheet As IWorkbook = workbook.Worksheets(0)
 
'Creates Range collection.
Dim rangesOne As Syncfusion.XlsIO.IRanges = sheet.CreateRangesCollection()
 
'Adds different ranges to the Range collection.
rangesOne.Add(sheet.Range("D2:D3"))
rangesOne.Add(sheet.Range("D10:D11"))
 
string fileName = "Output.xlsx"
workbook.Version = ExcelVersion.Excel2010
 
workbook.SaveAs(fileName)
 
//Closes the workbook.
workbook.Close()
excelEngine.Dispose() 
  
{% endhighlight %}
{% endtabs %}
