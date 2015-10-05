---
layout: post
title: Working-with-Header-and-footer-template
description: working with header and footer template
platform: wpf
control: PDF
documentation: ug
---

# Working with Header and footer template

Headers and footers can be placed in the pages of the PDF document.

Refer the following procedure to place a header:

1. Create a template object for the header. PdfPageTemplateElement class can be used for creating a template object.

2. Assign the created template header to PDF document header.

The same procedure can be followed to create footer. Page numbers on the footer of a document are set by using automatic fields.

You can dock the header or footer to any position.

The following code example illustrates you on how to create a Header and Footer.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document

PdfPage pdfPage = pdfDocument.Pages.Add();

//Creates a header and draws the image.

RectangleF rect = new RectangleF(0, 0, pdfDocument.Pages[0].GetClientSize().Width, 50);

PdfPageTemplateElement header = new PdfPageTemplateElement(rect);

PdfImage img = new PdfBitmap(@"Logo.png");

//Draws the image in the Header.

header.Graphics.DrawImage(img, new PointF(0, 0), new SizeF(100, 50));

//Adds the header at the top.

pdfDocument.Template.Top = header;

//Footer.

//Creates a Template that can be used as footer.

//Creates a page template.

PdfPageTemplateElement footer = new PdfPageTemplateElement(rect);

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 7);

PdfBrush brush = new PdfSolidBrush(Color.Black);

//Creates page number field.

PdfPageNumberField pageNumber = new PdfPageNumberField(font, brush);

//Creates page count field.

PdfPageCountField count = new PdfPageCountField(font, brush);

//Adds the fields in composite fields.

PdfCompositeField compositeField = new PdfCompositeField(font, brush, "Page {0} of {1}", pageNumber, count);

compositeField.Bounds = footer.Bounds;

//Draws the composite field in footer.

compositeField.Draw(footer.Graphics, new PointF(470, 40));

//Adds the footer template at the bottom.

pdfDocument.Template.Bottom = footer;

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a header and draws the image.

Dim rect As New RectangleF(0, 0, pdfDocument.Pages(0).GetClientSize().Width, 50)

Dim header As New PdfPageTemplateElement(rect)

Dim img As PdfImage = New PdfBitmap("Logo.jpg")

'Draws the image in the Header.

header.Graphics.DrawImage(img, New PointF(0, 0), New SizeF(100, 50))

'Adds the header at the top.

pdfDocument.Template.Top = header

'Footer.

'Creates a Template that can be used as footer.

'Creates a page template.

Dim footer As New PdfPageTemplateElement(rect)

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 7)

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

'Creates page number field.

Dim pageNumber As New PdfPageNumberField(font, brush)

'Creates page count field.

Dim count As New PdfPageCountField(font, brush)

'Adds the fields in composite fields.

Dim compositeField As New PdfCompositeField(font, brush, "Page {0} of {1}", pageNumber, count)

compositeField.Bounds = footer.Bounds

'Draws the composite field in footer.

compositeField.Draw(footer.Graphics, New PointF(470, 40))

'Adds the footer template at the bottom.

pdfDocument.Template.Bottom = footer

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

