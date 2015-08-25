---
layout: post
title: Pages
description: pages
platform: wpf
control: PDF
documentation: ug
---

# Pages

PdfPage is a class that represents the page of the PDF document where you can include all the visual elements of a PDF document like text, shapes, annotations, formfield, etc. Essential PDF provides complete control of the page that includes modifying the page settings such as size, orientation, adding or removing pages, and importing pages from one document to another. 

## Page settings	

Essential PDF supports various page setting options to control the page display. They are as follows.

* Page orientation
* Page size
* Page layout
* Page mode
* Page scale
* Page transition

Some of the page sizes supported is as follows:

* A0 to A9
* B0 to B5
* ArchA to ArchE
* Half Letter
* Ledger
* Letter
* Legal
* Note
* Letter11x17

The following code sample illustrate the various page settings.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Sets landscape page orientation.

document.PageSettings.Orientation = PdfPageOrientation.Landscape;

// Sets the page size.

document.PageSettings.Size = PdfPageSize.A3;

//Adds a page to the document.

PdfPage page = document.Pages.Add();        

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 20);

//Draws the text.

graphics.DrawString("Hello World!!!", font, PdfBrushes.Black, new PointF(0, 0));

//Saves the document.

document.Save("Output.pdf");

//Closes the document.

document.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Sets landscape page orientation.

document.PageSettings.Orientation = PdfPageOrientation.Landscape

'Sets page size.

document.PageSettings.Size = PdfPageSize.A3

'Adds a page to the document.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Sets the font.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 20)

'Draws the text.

graphics.DrawString("Hello World!!!", font, PdfBrushes.Black, New PointF(0, 0))

'Saves the document.

document.Save("Output.pdf")

'Closes the document.

document.Close(True)
{% endhighlight %}

## Add a Page

Add method of the PdfPage Collection class allows you to add an empty page in a PDF document. Pages can be added to any part of the document using the Essential PDF APIs.

The following code sample explains you on how to add a page in a PDF file. The Add() method of the PdfPageCollection class adds the page at the end.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, fontSize);

//Draws the text.

graphics.DrawString("Hello world!", font, brush, new PointF(20, 20));

//Saves the document.

document.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As PdfDocument = New PdfDocument()

'Adds a page to the document.

Dim page As PdfPage = document.Pages.Add() 

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black) 

'Sets the font.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, fontSize)

'Draws the text.

graphics.DrawString("Hello world!", font, brush,new PointF(20,20)) 

'Saves the document.

document.Save("Sample.pdf")

{% endhighlight %}

You can add new pages to an existing document in the front, middle, or at the end.

The following code sample illustrates how to insert a new page by specifying the index.

{% highlight c# %}



//Loads the PDF document.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Input.pdf");

//Adds page to the existing PDF document.

PdfPage page = loadedDocument.Pages.Insert(1) as PdfPage;

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 20);

//Draws the text in the inserted page.

graphics.DrawString("Page 2", font, PdfBrushes.Black, PointF.Empty);

//Saves and closes the PDF document.

loadedDocument.Save("Output.pdf");

loadedDocument.Close();

{% endhighlight %}

{% highlight vbnet %}



'Loads the PDF document.

Dim loadedDocument As New PdfLoadedDocument("Input.pdf")

'Adds page to the existing PDF document.

Dim page As PdfPage = TryCast(loadedDocument.Pages.Insert(1), PdfPage)

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Sets the font.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 20)

'Draws the text in the inserted page.

graphics.DrawString("Page 2", font, PdfBrushes.Black, PointF.Empty)

'Saves and closes the PDF document.

loadedDocument.Save("Output.pdf")

loadedDocument.Close()
{% endhighlight %}

Removing a page

You can also remove pages from an existing PDF document by using following methods of the PdfLoadedPageCollection class.

* Remove -  This method allows you to remove the specified page
* RemoveAt -  This method allows you to remove the page at the specified index

The following code sample illustrates how to remove an existing page from the PDF document.

{% highlight c# %}



PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Sample.pdf");

//Removes the page by passing the PDF page.

loadedDocument.Pages.Remove(loadedDocument.Pages[1]);

//Removes the page by specifying the page index.

loadedDocument.Pages.RemoveAt(2);

//Saves the document.

loadedDocument.Save("Output.pdf");

//Closes the document.

loadedDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}



Dim loadedDocument As PdfLoadedDocument = New PdfLoadedDocument("Sample.pdf")

'Removes the page by passing the PDF page.

loadedDocument.Pages.Remove(loadedDocument.Pages(1))

'Removes the page by specifying the page index.

loadedDocument.Pages.RemoveAt(2)

'Saves the document.

loadedDocument.Save("Sample.pdf")

'Closes the document.

loadedDocument.Close(True)
{% endhighlight %}

## Import pages

Essential PDF allows you to import a page or import a range of pages from one document to the other. The following code sample illustrates how to import a page to the existing document.

{% highlight c# %}



//Loads the PDF document.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Input.pdf");  

//Creates a new PDF document.

PdfDocument document = new PdfDocument();

int startIndex = 0;

int endIndex = loadedDocument.Pages.Count - 1;

//Imports all the pages to the new PDF document.

document.ImportPageRange(loadedDocument, startIndex, endIndex);

//Saves the document.

document.Save("Output.pdf");

//Closes both document instances.

loadedDocument.Close();

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Loads the PDF document.

Dim loadedDocument As New PdfLoadedDocument("Input.pdf")

'Creates a new PDF document.

Dim document As New PdfDocument()

Dim startIndex As Integer = 0

Dim endIndex As Integer = loadedDocument.Pages.Count - 1

'Imports all the pages to the new PDF document.

document.ImportPageRange(loadedDocument, startIndex, endIndex)

'Saves the document.

document.Save("Output.pdf")

'Closes both document instances.

loadedDocument.Close()

document.Close()

{% endhighlight %}

The following code sample illustrates how to import a page to the existing document using ImportPagemethod.

{% highlight c# %}



//Loads the PDF document.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Input.pdf");

//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Imports all the pages to the new PDF document.

document.ImportPage(loadedDocument,0);

//Saves the document.

document.Save("Output.pdf");

//Closes both document instances.

loadedDocument.Close();

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Loads the PDF document.

Dim loadedDocument As New PdfLoadedDocument("Input.pdf")

'Creates a new PDF document.

Dim document As New PdfDocument()

'Imports all the pages to the new PDF document.

document.ImportPage(loadedDocument, 0)

'Saves the document.

document.Save("Output.pdf")

'Closes both document instances.

loadedDocument.Close()

document.Close()
{% endhighlight %}


Implementation Note

Importing is done by converting the page content into PdfTemplate object that is, the new page does not inherit the possible complex layer structure, so that, only one default layer can be seen and something can be placed beneath that layer. However, you can not manipulate the "old" layers as they do not exist.

This conversion is performed in order to avoid an incomplete page, harming further output. 

Restrictions

* The bookmark tree might not appear like the original document if just part of it is copied, as it is hard to recreate the tree with parts of the bookmark.
* Some of the contents are usually imported from the original document to the final document during saving process. Hence, the original document should be closed only after the final document is saved.



N> To import the document asynchronously for Windows Store apps, refer the_ [Asynchronous Support](http://help.syncfusion.com/ug/windows%20forms/pdf/documents/asynchronoussupport.htm) _section.

## TextElement

### Drawing Text

PDF provides higher-level facilities that permit an application to describe, select, and render glyphs conveniently and efficiently.  Drawing Text in a PDF document is made simpler and similar to .NET GDI API. This section demonstrates you on how a string is drawn in a PDF page by using Essential PDF.

The DrawString method draws the text string at the specified location with the selected Brush and Font.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument doc = new PdfDocument();

//Adds a page to the document.

PdfPage page = doc.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, fontSize);

//Draws the text.

graphics.DrawString("Hello world!", font, brush, new PointF(20, 20));

//Saves the document.

doc.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim doc As PdfDocument = New PdfDocument()

'Adds a page to the document.

Dim page As PdfPage = doc.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

'Sets the font.

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, fontSize)

'Draws the text.

graphics.DrawString("Hello world!", font, brush,new PointF(20,20))

'Saves the document.

doc.Save("Sample.pdf")

{% endhighlight %}

