---
layout: post
title: Split-Documents
description: split documents
platform: wpf
control: PDF
documentation: ug
---

# Split Documents

Splitting operation is used to generate a set of PDF documents, each of which is made of one page from the base document. Each new document is saved with a unique name that is generated from the pattern specified. 

The pattern should be in .NET format (for example: "myfile {0:000}.pdf") or just a pdf name. In latter case, the unique name have numbers before ".pdf".

{% highlight c# %}



//Loads document.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Input.pdf");

//Sets pattern.

const string destFilePattern = "Output" + "split{0:00}.pdf";

//Splits document.

loadedDocument.Split(destFilePattern);

{% endhighlight %}

{% highlight vbnet %}



'Loads document.

Dim loadedDocument As New PdfLoadedDocument("Input.pdf")

'Sets pattern.

Const destFilePattern As String = "Output" + "split{0:00}.pdf"

'Splits document.

loadedDocument.Split(destFilePattern)

 {% endhighlight %}

> Note: Splitting algorithm uses Import Page methods, so the result would be similar to it.

Essential PDF also allows you to split pages as per your wish. The following code example illustrates this.

{% highlight c# %}



//Loads an existing document, which needs to be split.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Input.pdf");

//Creates a PDF document.

PdfDocument document1 = new PdfDocument();

PdfDocument document2 = new PdfDocument();

//Adds page 9 into PDF document1.

document1.ImportPage(loadedDocument, 9);

//Adds page 10 into PDF document1.

document1.ImportPage(loadedDocument, 10);

//Adds page 5 into PDF document2.

document2.ImportPage(loadedDocument, 5);

//Adds page 6 into PDF document2.

document2.ImportPage(loadedDocument, 6);

//Saves PDF document1.

document1.Save("Document1.pdf");

//Saves PDF document1.

document2.Save("Document2.pdf");

document1.Close(true);

document2.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Loads an existing document, which needs to be split.

Dim loadedDocument As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")

'Creates a PDF document.

Dim document1 As PdfDocument = New PdfDocument()

Dim document2 As PdfDocument = New PdfDocument()

'Adds page 9 into pdf document1.

document1.ImportPage(loadedDocument, 9)

'Adds page 10 into pdf document1.

document1.ImportPage(loadedDocument, 10)

'Adds page 5 into pdf document2.

document2.ImportPage(loadedDocument, 5)

'Adds page 6 into pdf document2.

document2.ImportPage(loadedDocument, 6)

'Saves PDF document1.

document1.Save("Document1.pdf")

'Saves PDF document1.

document2.Save("Document2.pdf")

document1.Close(True)

document2.Close(True)

{% endhighlight %}

