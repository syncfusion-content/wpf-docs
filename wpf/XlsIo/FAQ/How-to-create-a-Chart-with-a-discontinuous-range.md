---
layout: post
title: How to create a Chart with a discontinuous range | XlsIO | WPF | Syncfusion
description:  How to create a Chart with a discontinuous range
platform: wpf
control: Xlsio
documentation: ug
---

# How to create a Chart with a discontinuous range

The following code example illustrates creating a chart with discontiguous data ranges.

{% tabs %} 
 
{% highlight C# %}

//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.
IApplication application = excelEngine.Excel;
application.DefaultVersion = ExcelVersion.Excel2010;
 
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);
 
IWorksheet sheet = workbook.Worksheets[0];
 
//Enters the data for the chart.
sheet.Range["A1"].Text = "Texas books Unit sales";
sheet.Range["A1:D1"].Merge();
sheet.Range["A1"].CellStyle.Font.Bold = true;
 
sheet.Range["B2"].Text = "Jan";
sheet.Range["C2"].Text = "Feb";
sheet.Range["D2"].Text = "Mar";
 
sheet.Range["A3"].Text = "Austin";
sheet.Range["A4"].Text = "Dallas";
sheet.Range["A5"].Text = "Houston";
sheet.Range["A6"].Text = "San Antonio";
 
sheet.Range["B3"].Number = 53.75;
sheet.Range["B4"].Number = 52.85;
sheet.Range["B5"].Number = 59.77;
sheet.Range["B6"].Number = 96.15;
 
sheet.Range["C3"].Number = 79.79;
sheet.Range["C4"].Number = 59.22;
sheet.Range["C5"].Number = 10.09;
sheet.Range["C6"].Number = 73.02;
 
sheet.Range["D3"].Number = 26.72;
sheet.Range["D4"].Number = 33.71;
sheet.Range["D5"].Number = 45.81;
sheet.Range["D6"].Number = 12.17;
 
sheet.Range["F1"].Number = 26.72;
sheet.Range["F2"].Number = 33.71;
 
sheet.Range["F3"].Number = 45.81;
sheet.Range["F4"].Number = 12.17;
 
//Discontiguous range.
IRanges rangesOne = sheet.CreateRangesCollection();
rangesOne.Add(sheet.Range["B3:B6"]);
rangesOne.Add(sheet.Range["F1:F2"]);
 
IRanges rangesTwo = sheet.CreateRangesCollection();
rangesTwo.Add(sheet.Range["D3:D6"]);
rangesTwo.Add(sheet.Range["F3:F4"]);
 
//Adds a New (Embedded chart) to the Worksheet.
IChartShape shape = sheet.Charts.Add();
shape.PrimaryCategoryAxis.Title = "City";
shape.PrimaryValueAxis.Title = "Sales (in Dollars)";
shape.ChartTitle = "Texas Books Unit Sales";
 
//Sets the Series Names in a Legend.
IChartSerie serieOne = shape.Series.Add();
serieOne.Name = "Jan";
serieOne.Values = rangesOne;
 
IChartSerie serietwo = shape.Series.Add();
serietwo.Name = "March";
serietwo.Values = rangesTwo;
 
//Sets the(Rows & Columns)Property for the Embedded chart.
shape.BottomRow = 40;
shape.TopRow = 10;
shape.LeftColumn = 3;
shape.RightColumn = 15;
 
string fileName = "Output.xlsx";
workbook.Version = ExcelVersion.Excel2010;
 
workbook.SaveAs(fileName);
 
//Closes the workbook.
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
 
'Enters the data for the chart.
sheet.Range("A1").Text = "Texas books Unit sales"
sheet.Range("A1:D1").Merge()
sheet.Range("A1").CellStyle.Font.Bold = True
 
sheet.Range("B2").Text = "Jan"
sheet.Range("C2").Text = "Feb"
sheet.Range("D2").Text = "Mar"
 
sheet.Range("A3").Text = "Austin"
sheet.Range("A4").Text = "Dallas"
sheet.Range("A5").Text = "Houston"
sheet.Range("A6").Text = "San Antonio"
 
sheet.Range("B3").Number = 53.75
sheet.Range("B4").Number = 52.85
sheet.Range("B5").Number = 59.77
sheet.Range("B6").Number = 96.15
 
sheet.Range("C3").Number = 79.79
sheet.Range("C4").Number = 59.22
sheet.Range("C5").Number = 10.09
sheet.Range("C6").Number = 73.02
 
sheet.Range("D3").Number = 26.72
sheet.Range("D4").Number = 33.71
sheet.Range("D5").Number = 45.81
sheet.Range("D6").Number = 12.17
 
sheet.Range("F1").Number = 26.72
sheet.Range("F2").Number = 33.71
 
sheet.Range("F3").Number = 45.81
sheet.Range("F4").Number = 12.17
 
'Discontiguous range.
Dim rangesOne As Syncfusion.XlsIO.IRanges = sheet.CreateRangesCollection()
rangesOne.Add(sheet.Range("B3:B6"))
rangesOne.Add(sheet.Range("F1:F2"))
 
Dim rangesTwo As Syncfusion.XlsIO.IRanges = sheet.CreateRangesCollection()
rangesTwo.Add(sheet.Range("D3:D6"))
rangesTwo.Add(sheet.Range("F3:F4"))
 
'Adds a New (Embedded chart) to the Worksheet.
Dim shape As Syncfusion.XlsIO.IChartShape = sheet.Charts.Add()
shape.PrimaryCategoryAxis.Title = "City"
shape.PrimaryValueAxis.Title = "Sales (in Dollars)"
shape.ChartTitle = "Texas Books Unit Sales"
 
'Sets the Series Names in a Legend.
Dim serieOne As Syncfusion.XlsIO.IChartSerie = shape.Series.Add()
serieOne.Name = "Jan"
serieOne.Values = rangesOne
 
Dim serietwo As Syncfusion.XlsIO.IChartSerie = shape.Series.Add()
serietwo.Name = "March"
serietwo.Values = rangesTwo
 
'Sets the (Rows & Columns) Property for the Embedded chart.
shape.BottomRow = 40
shape.TopRow = 10
shape.LeftColumn = 3
shape.RightColumn = 15
 
Dim fileName As String = "Output.xlsx"
workbook.SaveAs(fileName)
 
'Closes the workbook.
workbook.Close()
excelEngine.Dispose()

{% endhighlight %}
{% endtabs %}
