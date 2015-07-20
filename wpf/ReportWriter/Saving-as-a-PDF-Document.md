---
layout: post
title: Saving-as-a-PDF-Document
description: saving as a pdf document 
platform: wpf
control: Report Writer
documentation: ug
---

# Saving as a PDF Document 

The RDL report generated using the Report Designer can be exported as a PDF document using the following code.

[C#]

//Instantiate the report writer with the parameter "ReportPath" and 

“ReportDataSource” Collection

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);

reportWriter.Save("Sample.pdf", WriterFormat.PDF);



[VB]

'Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

Dim reportWriter As New ReportWriter (reportpath, dataSources)

reportWriter.Save("Sample.pdf", WriterFormat.PDF);



