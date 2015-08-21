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

{%highlight c#%}

spreadsheet.ImportFromExcel(stream);
{%endhighlight%}

{%highlight vbnet%}

 spreadsheet.ImportFromExcel(stream)
{%endhighlight%}



The following code illustrates how to open Spreadsheet control with file stream and ExcelOpenType:

{%highlight c#%}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic);
{%endhighlight%}

{%highlight vbnet%}
spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic)
{%endhighlight%}



The following code illustrates how to open Spreadsheet control with file stream and Excel Version:


{%highlight c#%}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010);
{%endhighlight%}


{%highlight vbnet%}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)
{%endhighlight%}



The following code illustrates how to open Spreadsheet control with file stream, ExcelOpenType and Excel Version:


{%highlight c#%}


spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic, Syncfusion.XlsIO.ExcelVersion.Excel2010);

{%endhighlight%}

{%highlight vbnet%}


spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)


{%endhighlight%}



### Using Command 

You can also open the Excel document by using the ImportFromExcelCommand_._ When you execute the ImportFromExcelCommand it will open the Open dialog box. Using that dialog you can open the Excel document. 



![](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img1.png)





The following code illustrates how to bind the ImportFromExcelCommand__to a button: 

{%highlight xml%}



<Button Command="{Binding Path= ImportFromExcelCommand}"/>

{%endhighlight%}

## Save Excel Documents

To save the current Workbook, call the _SaveAs_ method as given in the following code:



{%highlight c#%}

spreadControl.SaveAs();

{%endhighlight%}

{%highlight vbnet%}


spreadControl.SaveAs()

{%endhighlight%}



Save As dialog box will open. Save the document at the required location.  



![](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img2.png)





### Using Command

You can save the Excel document using the ExportToExcelCommand_._ When you execute the ExportToExcelCommand_,_ it will open the SaveAs__dialog box. Save the content of the Spreadsheet control as Excel document.

The following code illustrates how to bind the ExportToExcelCommand__to a button: 

{%highlight xml%}



<Button Command="{Binding Path= ExportToExcelCommand}"/>

{%endhighlight%}

