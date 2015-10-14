---
layout: post
title: How to format the text within a cell | XlsIO | WPF | Syncfusion
description:  How to format the text within a cell
platform: wpf
control: Xlsio
documentation: ug
---

# How to format the text within a cell

The text within a cell can be formatted by using the RichText functionality of XlsIO. The following code example illustrates this.

{% tabs %}
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Inserts Rich Text.
IRange range = sheet.Range["A1"];
range.Text = "RichText";
IRichTextString rtf = range.RichText;
 
//Formats first 4 characters.
IFont redFont = workbook.CreateFont();
redFont.Bold = true;
redFont.Italic = true;
redFont.RGBColor = Color.Red;
rtf.SetFont(0, 3, redFont);
 
//Formats last 4 characters.
IFont blueFont = workbook.CreateFont();
blueFont.Bold = true;
blueFont.Italic = true;
blueFont.RGBColor = Color.Blue;
rtf.SetFont(4, 7, blueFont);
 
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
 
'Inserts Rich Text.
Dim range As Syncfusion.XlsIO.IRange = sheet.Range("A1")
range.Text = "RichText"
Dim rtf As Syncfusion.XlsIO.IRichTextString = range.RichText
 
'Formats first 4 characters.
Dim redFont As Syncfusion.XlsIO.IFont = workbook.CreateFont()
redFont.Bold = True
redFont.Italic = True
redFont.RGBColor = Color.Red
rtf.SetFont(0, 3, redFont)
 
'Formats last 4 characters.
Dim blueFont As Syncfusion.XlsIO.IFont = workbook.CreateFont()
blueFont.Bold = True
blueFont.Italic = True
blueFont.RGBColor = Color.Blue
rtf.SetFont(4, 7, blueFont)
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
'Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}
