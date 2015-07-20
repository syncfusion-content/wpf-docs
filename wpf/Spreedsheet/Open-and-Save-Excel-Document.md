---
layout: post
title: Open-and-Save-Excel-Document
description: open and save excel document
platform: wpf
control: Spreadsheet
documentation: ug
---

# Open and Save Excel Document

You can open and save the Excel document that is compatible with following Excel versions:

* Excel 97 (.xls)
* Excel 2000 (.xls)
* Excel 2002 (.xls)
* Excel 2003 (.xls)
* Excel 2007 (.xlsx)
* Excel 2010 (.xlsx)



## Open Excel Document

You can open the Excel document using the one of the following override methods:

The following code illustrates how to open Spreadsheet control with file stream:



<table>
<tr>
<td colspan = "2">
[C#]spreadsheet.ImportFromExcel(stream);</td></tr>
<tr>
<td>
 [VB]spreadsheet.ImportFromExcel(stream)</td></tr>
</table>


The following code illustrates how to open Spreadsheet control with file stream and ExcelOpenType:



<table>
<tr>
<td>
[C#]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic);</td></tr>
<tr>
<td>
 [VB]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic)</td></tr>
</table>


The following code illustrates how to open Spreadsheet control with file stream and Excel Version:



<table>
<tr>
<td>
[C#]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010);</td></tr>
<tr>
<td>
 [VB]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)</td></tr>
</table>


The following code illustrates how to open Spreadsheet control with file stream, ExcelOpenType and Excel Version:



<table>
<tr>
<td>
[C#]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic, Syncfusion.XlsIO.ExcelVersion.Excel2010);</td></tr>
<tr>
<td>
 [VB]spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)</td></tr>
</table>


Using Command 

You can also open the Excel document by using the ImportFromExcelCommand_._ When you execute the ImportFromExcelCommand it will open the Open dialog box. Using that dialog you can open the Excel document. 



{ ![](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img1.png) | markdownify }
{:.image }




The following code illustrates how to bind the ImportFromExcelCommand__to a button: 



[XAML]

&lt;Button Command="{Binding Path= ImportFromExcelCommand}"/&gt;



## Save Excel Documents

To save the current Workbook, call the _SaveAs_ method as given in the following code:



<table>
<tr>
<td>
[C#]spreadControl.SaveAs();</td></tr>
<tr>
<td>
 [VB]spreadControl.SaveAs()</td></tr>
</table>


Save As dialog box will open. Save the document at the required location.  



{ ![](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img2.png) | markdownify }
{:.image }




Using Command

You can save the Excel document using the ExportToExcelCommand_._ When you execute the ExportToExcelCommand_,_ it will open the SaveAs__dialog box. Save the content of the Spreadsheet control as Excel document.

The following code illustrates how to bind the ExportToExcelCommand__to a button: 



[XAML]

&lt;Button Command="{Binding Path= ExportToExcelCommand}"/&gt;



