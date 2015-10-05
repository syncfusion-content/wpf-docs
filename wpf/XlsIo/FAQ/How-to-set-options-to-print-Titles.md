---
layout: post
title: How to set options to print Titles | XlsIO | WPF | Syncfusion
description:  How to set options to print Titles
platform: wpf
control: Xlsio
documentation: ug
---

# How to set options to print Titles

## Printing Title Rows

The following code example illustrates printing the Title Rows.
{% tabs %}
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Prints Rows 1 to 3.
sheet.PageSetup.PrintTitleRows = "$A$1:$IV$3";
 
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
 
'Prints Rows 1 to 3.
sheet.PageSetup.PrintTitleRows = "$A$1:$IV$3"
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}
## Printing the Title Columns

The following code example illustrates printing the Title Columns.
{% tabs %}
{% highlight C# %}
 
 //Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Prints Columns 1 to 3.
sheet.PageSetup.PrintTitleColumns = "$A$1:$C$65536";
 
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
 
'Prints Columns 1 to 3.
sheet.PageSetup.PrintTitleColumns = "$A$1:$C$65536"
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}
For information on Print settings, refer to the section [Print Settings](http://docs.syncfusion.com/windowsforms).