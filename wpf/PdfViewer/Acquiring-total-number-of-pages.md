---
layout: post
title: Acquiring-total-number-of-pages 
description: acquiring total number of pages 
platform: wpf
control: PDF Viewer
documentation: ug
---

### Acquiring total number of pages

PDF Viewer provides the total number of the pages in the PDF document that is being loaded into the PDF Viewer. This value can be acquired with the help of PageCount property in the PDF Viewer control, the following code example illustrates the same.

[C#]

// Acquiring the total number of pages in the document being loaded  

int pageCount = pdfviewer1.PageCount;





[VB.NET]

'Acquiring the total number of pages in the document being loaded 

Dim pageCount As Integer = pdfviewer1.PageCount

