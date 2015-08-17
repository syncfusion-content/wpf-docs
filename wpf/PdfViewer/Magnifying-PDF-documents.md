---
layout: post
title: Magnifying-PDF-documents 
description: magnifying pdf documents
platform: wpf
control: PDF Viewer
documentation: ug
---

### Magnifying PDF documents

PDF Viewer allows you to magnify the PDF document that is being displayed. The following code examples can be used to perform this action.

[C#]

//Magnify the document to 150%

pdfviewer1.ZoomTo(150);



[VB.NET]

'Magnify the document to 150%

pdfviewer1.ZoomTo(150)



The magnification can also be set by updating the Zoom property of the PDF Viewer.

[C#]

//Magnify the document to 150%

pdfviewer1.Zoom = 250;



[VB.NET]

'Magnify the document to 150%

pdfviewer1.Zoom = 250



Current magnification percentage of the PDF Viewer can be acquired with the use of the property ZoomPercentage

[C#]

//Acquire current zoom percentage

int currentZoomPercentage = pdfviewer1.ZoomPercentage;



[VB.NET]

' Acquire current zoom percentage 

Dim currentZoomPercentage As Integer = pdfviewer1.ZoomPercentage



Zoom mode of the PDF viewer can be set using the following code example.

[C#]

//Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth;



[VB.NET]

'Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth

