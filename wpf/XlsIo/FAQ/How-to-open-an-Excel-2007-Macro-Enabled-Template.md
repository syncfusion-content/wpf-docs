---
layout: post
title: How to open an Excel 2007 Macro Enabled Template | XlsIO | WPF | Syncfusion
description:  How to open an Excel 2007 Macro Enabled Template
platform: wpf
control: Xlsio
documentation: ug
---

# How to open an Excel 2007 Macro Enabled Template

XlsIO now provides support to open and save an Excel 2013 Macro Enabled Template to XLSM (Excel 2013 Macro Enabled Document) format. The following code example illustrates this.

{% tabs %}
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
// Opens an existing XLTM file.
IWorkbook workbook = application.Workbooks.Open(@"Template.xltm", ExcelOpenType.Automatic);
 
// Saves the file as XLSM.
workbook.Version = ExcelVersion.Excel2013;
workbook.SaveAs("Sample.xlsm", ExcelSaveType.SaveAsTemplate);
 {% endhighlight %}    


{% highlight vbnet %}

'Step 1: Instantiates the spreadsheet creation engine.
Dim excelEngine As ExcelEngine = New ExcelEngine
 
'Step 2: Instantiates the excel application object.
Dim application As IApplication = excelEngine.Excel
 
'Opens an existing XLTM file.
workbook = application.Workbooks.Open("MacroTemplate.xltm", ExcelOpenType.Automatic)
 
'Saves the file as XLSM.
workbook.Version = ExcelVersion.Excel2013
workbook.SaveAs("Sample.xlsm", ExcelSaveType.SaveAsTemplate)
 
{% endhighlight %}
{% endtabs %}

N> You need to change the Excel Version, if you want to save to another version.