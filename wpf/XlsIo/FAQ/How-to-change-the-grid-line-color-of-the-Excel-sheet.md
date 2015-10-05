---
layout: post
title: How to change the grid line color of the Excel sheet | XlsIO | WPF | Syncfusion
description:  How to change the grid line color of the Excel sheet
platform: wpf
control: Xlsio
documentation: ug
---

# How to change the grid line color of the Excel sheet

You can change the grid line color of the Excel worksheet by using the ExcelKnownColors property. The following code example illustrates this.

 
{% tabs %} 
{% highlight C# %}
 
//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
sheet.GridLineColor = ExcelKnownColors.Blue;
 
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
 
sheet.GridLineColor = ExcelKnownColors.Blue
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
'Closes the workbook.
workbook.Close()
excelEngine.Dispose()
{% endhighlight %}
{% endtabs %}