---
layout: post
title: How to open an Excel file from Stream | XlsIO | WPF | Syncfusion
description:  How to open an Excel file from Stream?
platform: wpf
control: Xlsio
documentation: ug
---

# How to open an Excel file from Stream?

XlsIO provides support for opening a template spreadsheet that is stored as a stream. The following code example illustrates this.

{% tabs %} 
 
{% highlight C# %}
  
//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
//Opens a File from a Stream.
FileStream fs = new FileStream("Sample.xls", FileMode.Open, FileAccess.ReadWrite, FileShare.ReadWrite);
fs.Seek(0, SeekOrigin.Begin);
IWorkbook workbook = application.Workbooks.Open(fs);
 
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

 

'Opens a File from a Stream.

Dim fs As FileStream = New FileStream("Sample.xls", FileMode.Open, FileAccess.ReadWrite, FileShare.ReadWrite)

fs.Seek(0, SeekOrigin.Begin)

Dim workbook As IWorkbook = application.Workbooks.Open(fs)

 

Dim fileName As String = "Output.xlsx"

workbook.SaveAs(fileName)

 

' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

{% endhighlight %}

{% endtabs %}
