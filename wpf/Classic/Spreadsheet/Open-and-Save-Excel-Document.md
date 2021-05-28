---
layout: post
title: Open and Save Excel Document in WPF Spreadsheet Control | Syncfusion
description: Learn here all about Open and Save Excel Document support in Syncfusion WPF SpreadsheetControl (Classic) control and more.
platform: wpf
control: Spreadsheet
 documentation: ug
---

# Open and Save Excel Document in WPF SpreadsheetControl (Classic)

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

{% tabs %}

{% highlight c# %}

spreadsheet.ImportFromExcel(stream);

{% endhighlight %}

{% highlight vbnet %}

 spreadsheet.ImportFromExcel(stream)
 
{% endhighlight %}

{% endtabs %}

The following code illustrates how to open Spreadsheet control with file stream and ExcelOpenType:

{% tabs %}

{% highlight c# %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic);

{% endhighlight %}

{% highlight vbnet %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic)

{% endhighlight %}

{% endtabs %}

The following code illustrates how to open Spreadsheet control with file stream and Excel Version:

{% tabs %}

{% highlight c# %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010);

{% endhighlight %}

{% highlight vbnet %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)

{% endhighlight %}

{% endtabs %}

The following code illustrates how to open Spreadsheet control with file stream, ExcelOpenType and Excel Version:

{% tabs %}

{% highlight c# %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelOpenType.Automatic, Syncfusion.XlsIO.ExcelVersion.Excel2010);

{% endhighlight %}

{% highlight vbnet %}

spreadsheet.ImportFromExcel(stream, Syncfusion.XlsIO.ExcelVersion.Excel2010)

{% endhighlight %}

{% endtabs %}

### Using Command 

You can also open the Excel document by using the ImportFromExcelCommand. When you execute the ImportFromExcelCommand it will open the Open dialog box. Using that dialog you can open the Excel document. 

![Open-and-Save-Excel-Document_img1](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img1.png)

The following code illustrates how to bind the ImportFromExcelCommand__to a button: 

{% highlight xaml %}

<Button Command="{Binding Path= ImportFromExcelCommand}"/>

{% endhighlight %}

## Save Excel Documents

To save the current Workbook, call the _SaveAs_ method as given in the following code:

{% tabs %}

{% highlight c# %}

spreadControl.SaveAs();

{% endhighlight %}

{% highlight vbnet %}

spreadControl.SaveAs()

{% endhighlight %}

{% endtabs %}

Save As dialog box will open. Save the document at the required location.  

![Open-and-Save-Excel-Document_img2](Open-and-Save-Excel-Document_images/Open-and-Save-Excel-Document_img2.png)

### Using Command

You can save the Excel document using the ExportToExcelCommand. When you execute the ExportToExcelCommand, it will open the SaveAs dialog box. Save the content of the Spreadsheet control as Excel document.

The following code illustrates how to bind the ExportToExcelCommand to a button: 

{% highlight xaml %}

<Button Command="{Binding Path= ExportToExcelCommand}"/>

{% endhighlight %}
