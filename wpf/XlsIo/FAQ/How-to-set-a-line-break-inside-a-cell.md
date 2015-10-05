---
layout: post
title: How to set a line break inside a cell | XlsIO | WPF | Syncfusion
description:  How to set a line break inside a cell
platform: wpf
control: Xlsio
documentation: ug
---

# How to set a line break inside a cell

In order to set a line break inside a cell, you have to enable Text Wrapping for the cell and then break the text. The following code example illustrates this.
{% tabs %}
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Saves the line break inside the cell.
sheet.Range["A1"].CellStyle.WrapText = true;
sheet.Range["A1"].Text = String.Format("Hello\nworld");
 
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
Dim sheetOne As IWorkbook = workbook.Worksheets(0)
 
'Saves the line break inside the cell.
sheet.Range("A1").CellStyle.WrapText = True
sheet.Range("A1").Text = String.Format("Hello" & Constants.vbLf & "world")
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
'Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}

{% endtabs %}