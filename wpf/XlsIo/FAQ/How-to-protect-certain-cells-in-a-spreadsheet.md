---
layout: post
title: How to protect certain cells in a spreadsheet | XlsIO | WPF | Syncfusion
description:  How to protect certain cells in a spreadsheet
platform: wpf
control: Xlsio
documentation: ug
---

# How to protect certain cells in a spreadsheet

All the cells in an Excel spreadsheet have a Locked property that determines if the cell is editable when the worksheet is protected. All the cells are set to Locked, by default. So, when a worksheet is protected, all the cells in the worksheet get protected, by default. However, there is often a need to protect only certain cells in a worksheet. In this scenario, you need to protect a worksheet and set the IsLocked property to false for the cells that need to be made editable.

{% tabs %} 
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheetOne = workbook.Worksheets[0];
 
// Sample data.
sheetOne.Range["A1:K20"].Text = "Locked";
 
// A1:A10 will not be protected.
sheetOne.Range["A1:A10"].CellStyle.Locked = false;
sheetOne.Range["A1:A10"].Text = "UnLocked";
sheetOne.Protect("syncfusion", ExcelSheetProtection.FormattingColumns);
 
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
 
'Sample data.
sheetOne.Range("A1:K20").Text = "Locked"
 
'A1:A10 is not protected.
sheetOne.Range("A1:A10").CellStyle.Locked = False
sheetOne.Range("A1:A10").Text = "UnLocked"
sheetOne.Protect("syncfusion", ExcelSheetProtection.FormattingColumns)
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
' Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}

N> Locking/Unlocking cells in an unprotected worksheet has no effect.