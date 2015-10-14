---
layout: post
title: How to unfreeze the rows and columns in XlsIO | XlsIO | WPF | Syncfusion
description:  How to unfreeze the rows and columns in XlsIO
platform: wpf
control: Xlsio
documentation: ug
---

# How to unfreeze the rows and columns in XlsIO

You can unfreeze rows and columns in XlsIO by using the RemovePanes method. The following code example illustrates this.

{% tabs %} 
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Sets the FreezePanes.
sheet.Range[8, 1].FreezePanes();
sheet.RemovePanes();
 
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
 
'Sets the FreezePanes.
sheet.Range(8, 1).FreezePanes()
sheet.RemovePanes()
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()
{% endhighlight %}

{% endtabs %}