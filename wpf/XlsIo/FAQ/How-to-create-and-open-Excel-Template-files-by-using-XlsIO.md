---
layout: post
title: How to create and open Excel Template files by using XlsIO | XlsIO | WPF | Syncfusion
description:  How to create and open Excel Template files by using XlsIO
platform: wpf
control: Xlsio
documentation: ug
---

# How to create and open Excel Template files by using XlsIO

You can create either XLT or XLTX Excel Template files by saving a file with the ExcelSaveType property of the SaveAs method. The ExcelSaveType property must be set to SaveAsTemplate to create a template file of the existing file. The following code example illustrates this.

{% tabs %}
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Saves as XLT.
workbook.Version = ExcelVersion.Excel97to2003;
workbook.SaveAs("Sample.xlt", ExcelSaveType.SaveAsTemplate);
 
//Saves as XLTX.
workbook.Version = ExcelVersion.Excel2007;
workbook.SaveAs("Sample.xltx", ExcelSaveType.SaveAsTemplate);
  {% endhighlight %}    


{% highlight vbnet %}

 'Step 1: Instantiates the spreadsheet creation engine.
Dim excelEngine As ExcelEngine = New ExcelEngine
 
'Step 2: Instantiates the excel application object.
Dim application As IApplication = excelEngine.Excel
 
Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)
 
'Accesses via index.
Dim sheet As IWorkbook = workbook.Worksheets(0)
 
'Saves as XLT.
workbook.Version = ExcelVersion.Excel97to2003
workbook.SaveAs("Sample.xlt", ExcelSaveType.SaveAsTemplate)
 
'Saves as XLTX.
workbook.Version = ExcelVersion.Excel2007
workbook.SaveAs("Sample.xltx", ExcelSaveType.SaveAsTemplate)

{% endhighlight %}
{% endtabs %}
## Opening Excel Template Files

An Excel Template file is opened in the same way a document is opened. The following code example illustrates how to open a template file.
{% tabs %}
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
//Opens an Excel Template.
IWorkbook workbook = application.Workbooks.Open(fileName, ExcelOpenType.Automatic);
 
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
 
'Opens an Excel Template.
workbook = application.Workbooks.Open(fileName, ExcelOpenType.Automatic)
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}   

{% endtabs %}
     