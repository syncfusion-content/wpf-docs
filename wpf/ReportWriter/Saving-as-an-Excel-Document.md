---
layout: post
title: Saving-as-an-Excel-Document
description: saving as an excel document
platform: wpf
control: Report Writer
documentation: ug
---

# Saving as an Excel Document

The RDL report generated using the Report Designer can be exported as an Excel document using the following code example. 



[C#]

//Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);

reportWriter.Save("Sample.xls", WriterFormat.Excel);



[VB]

'Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

Dim reportWriter As New ReportWriter (reportPath, dataSources)

reportWriter.Save("Sample.xls", WriterFormat.Excel);



