---
layout: post
title: How to save a file to the stream | XlsIO | WPF | Syncfusion
description:  How to save a file to the stream
platform: wpf
control: Xlsio
documentation: ug
---

# How to save a file to the stream

XlsIO provides support to save a spreadsheet to a .NET stream. The following code example illustrates this.

{% tabs %}
 
{% highlight C# %}
 
//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
//Saves the workbook to stream.
FileStream fs = new FileStream("Sample.xls", FileMode.Create, FileAccess.ReadWrite, FileShare.ReadWrite);
workbook.SaveAs(fs);
workbook.Close();

{% endhighlight %}    


{% highlight vbnet %}

 'Saves the workbook to the stream.
Dim fs As FileStream = New FileStream("Sample.xls", FileMode.Create, FileAccess.ReadWrite, FileShare.ReadWrite)
 
'Step 1: Instantiates the spreadsheet creation engine.
Dim excelEngine As ExcelEngine = New ExcelEngine
 
'Step 2: Instantiates the excel application object.
Dim application As IApplication = excelEngine.Excel
 
Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)
workbook.SaveAs(fs)
workbook.Close()

{% endhighlight %}
{% endtabs %}
