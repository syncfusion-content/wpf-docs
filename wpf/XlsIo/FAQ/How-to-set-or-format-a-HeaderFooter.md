---
layout: post
title: How to set or format a HeaderFooter | XlsIO | WPF | Syncfusion
description:  How to set or format a Header/Footer
platform: wpf
control: Xlsio
documentation: ug
---

# How to set or format a Header/Footer

The string that the header/footer takes is a script that you can use to format the header/footer. For more information on formatting the string, see <http://support.microsoft.com/?kbid=213618>.

{% tabs %}
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Formats the header.
Sheet.PageSetup.CenterHeader = @"&""Gothic,bold""Center Header Text";  
 
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
 
'Formats the header.
sheet.PageSetup.CenterHeader = @"&""Gothic,bold""Center Header Text"
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}

{% endtabs %}