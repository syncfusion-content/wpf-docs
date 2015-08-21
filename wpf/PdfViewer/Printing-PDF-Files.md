---
layout: post
title: Printing-PDF-Files 
description: printing pdf files 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Printing PDF Files 

PDF Viewer allows printing loaded PDFs using the Print button in the toolbar. The following Print dialog opens upon triggering the Print button.

![](Concept-and-Features_images/Concept-and-Features_img1.png)



## Silent Printing

The PrintDocument property of PdfViewerControl returns System.Drawing.Printing.PrintDocument that helps to complete printing using PrintDialog. This type of printing can be used when trying to print the PDF document with the custom printer settings. The following code sample demonstrates this:

{% highlight c# %}

PrintDialog dialog = new PrintDialog();

dialog.AllowPrintToFile = true;         

dialog.Document = viewer.PrintDocument;

dialog.Document.Print();
{% endhighlight %}


{% highlight vbnet %}

Dim dialog As New PrintDialog()

dialog.AllowPrintToFile = True

dialog.Document = viewer.PrintDocument

dialog.Document.Print()

{% endhighlight %}

When you prefer to perform Silent printing with the default printer settings, then using Print method in the PDF Viewer control is the best approach. The following code example illustrates the same.

{% highlight c# %}

// Printing document using Print method

pdfviewer1.Print();


{% endhighlight %}


{% highlight vbnet %}

' Printing document using Print method

pdfviewer1.Print()

{% endhighlight %}