---
layout: post
title: How to use Named Ranges with XlsIO | XlsIO | WPF | Syncfusion
description:  How to use Named Ranges with XlsIO
platform: wpf
control: Xlsio
documentation: ug
---

# How to use Named Ranges with XlsIO

The NamedRanges collection belongs to the workbook and not to the worksheet. When you define two named ranges with the same name then the named range that is defined last replaces the previous named range.
{% tabs %} 
{% highlight C# %}
 
//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet mySheet = workbook.Worksheets[0];
 
//Loops through the Named Ranges in a spreadsheet.
foreach (IName name in mySheet.Names)
{
MessageBox.Show(name.Name.ToString());
}
//There is already a named range called "One". Change the address that it points to.
mySheet.Names["One"].RefersToRange = mySheet.Range["B6"];
 
//Named ranges are added to the workbook collection in both the methods mentioned.
//Adds the named Range to the workbook.
workbook.Names.Add("TestRangeBook", mySheet.Range["A5"]);
 
//Adds the named Range to the workbook. Internally named range is added to the workbook names coll.
mySheet.Names.Add("TestRangeSheet", mySheet.Range["A5"]);
 
//References from the sheet.
mySheet.Range["TestRangeSheet"].Number = 100;
 
string fileName = "Output.xlsx";
workbook.Version = ExcelVersion.Excel2010;
 
workbook.SaveAs(fileName);
 
// Closes the workbook.
workbook.Close();
excelengine.Dispose(); 
 
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