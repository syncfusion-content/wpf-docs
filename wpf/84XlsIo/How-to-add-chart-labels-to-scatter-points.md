---
layout: post
title: How-to-add-chart-labels-to-scatter-points
description:  how to add chart labels to scatter points
platform: wpf
control: XlsIO	
documentation: ug
---

###  How to add chart labels to scatter points

The following code example illustrates adding chart labels to the scatter points of the chart.

[C#]



//Step 1: Instantiates the spreadsheet creation engine.
ExcelEngine excelEngine = new ExcelEngine();

//Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;

application.DefaultVersion = ExcelVersion.Excel2010;



IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



//Gets the chart from the charts collection.
IChart chart = sheet.Charts[0];

//Gets the first series from the Series collection.
IChartSerie serieOne = chart.Series[0];        

//Sets the Series name to the Data Labels through Data Points.
serieOne.DataPoints[0].DataLabels.IsSeriesName = true;

//Sets the Value to the Data Labels through Data Points.
serieOne.DataPoints[0].DataLabels.IsValue = true;

string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



//Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB]



'Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



'Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



Dim workbook As IWorkbook = application.Workbooks.Open("sample.xlsx", ExcelOpenType.Automatic)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Gets the chart from the charts collection.
Dim chart As IChart = sheet.Charts(0)

'Gets the first series from the Series collection.
Dim serieOne As IChartSerie = chart.Series(0)


'Sets the Series name to the Data Labels through Data Points.
serieOne.DataPoints(0).DataLabels.IsSeriesName = True

'Sets the Value to the Data Labels through Data Points.
serieOne.DataPoints(0).DataLabels.IsValue = True



Dim fileName As String = "Output.xlsx"

workbook.SaveAs(fileName)



'Closes the workbook.

workbook.Close()

excelEngine.Dispose()



