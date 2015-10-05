---
layout: post
title: How to open an existing Xlsx workbook and save it as Xlsx | XlsIO | WPF | Syncfusion
description:  How to open an existing Xlsx workbook and save it as Xlsx
platform: wpf
control: Xlsio
documentation: ug
---

# How to open an existing Xlsx workbook and save it as Xlsx

You can open and save an existing Excel 2013 file to the .xlsx format by using XlsIO. The following code example illustrates this.
{% tabs %}
{% highlight C# %}

// Opens an existing Excel 2013 file.
IWorkbook workbook = excelEngine.Excel.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
// Selects the version to be saved.
workbook.Version = ExcelVersion.Excel2013;
 
// Saves it as "Excel 2007" format.
workbook.SaveAs("Sample.xlsx");

{% endhighlight %}    


{% highlight vbnet %}
  
'Opens an existing Excel 2013 file.
Dim workbook As IWorkbook = excelEngine.Excel.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)
 
'Selects the version to be saved.
workbook.Version = ExcelVersion.Excel2013
 
'Saves it as "Excel 2013" format.
workbook.SaveAs("Sample.xlsx")

{% endhighlight %}
{% endtabs %}

N> You need to change the Excel Version, if you want to save to another version.