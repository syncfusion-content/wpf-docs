---
layout: post
title: How to suppress the summary rows and columns by using XlsIO | XlsIO | WPF | Syncfusion
description:  How to suppress the summary rows and columns by using XlsIO
platform: wpf
control: Xlsio
documentation: ug
---

# How to suppress the summary rows and columns by using XlsIO

You can suppress the summary rows and columns by using the IsSummaryRowBelow and IsSummaryColumnRight properties. The following code example illustrates this.

 
{% tabs %}
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Suppresses the summary rows at the bottom.
sheet.PageSetup.IsSummaryRowBelow = false;
//Suppresses the summary columns to the right.
sheet.PageSetup.IsSummaryColumnRight = false;
 
string fileName = "Output.xlsx";
workbook.Version = ExcelVersion.Excel2010;
 
workbook.SaveAs(fileName);
 
//Closes the workbook.
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
 
'Suppresses the summary rows at the bottom.
sheet.PageSetup.IsSummaryRowBelow = False
'Suppress the summary columns to the right.
sheet.PageSetup.IsSummaryColumnRight = False
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
'Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}

{% endtabs %}