---
layout: post
title: Compression
description: compression
platform: wpf
control: PDF
documentation: ug
---

# Compression

Compression is the process of reducing the size of data in order to save space or transmission time.

For data transmission, compression can be performed on any of the following depending on a number of factors:

* Just the data content, or
* Entire transmission unit.

### Content compression

Content compression involves following:

* Removing all extra space characters.
* Inserting a single repeat character to indicate a string of repeated characters.
* Substituting smaller bit strings for frequently occurring characters.

Advantages of Content compression

* Reduces a text file upto 50 percent of its original size.
N> Compression is performed by a program that uses a formula or algorithm, which determines how to compress or decompress the data. This algorithm is one of the critical factors that determines compression quality and is elaborated below. 

### Controlling the Compression Levels 

Essential PDF controls the compression level of document by using the PdfCompressionLevel class with the help of the LZW and zlib/deflate compression algorithms. Both LZW and Flate algorithms compress either binary data or ASCII text and always produces the binary data.

The following compression levels are supported by Essential PDF:

* None-Packs without compression
* BestSpeed-Performs high speed compression; reduction of data size is lesser
* BelowNormal-Performs compression that is rated between Normal and BestSpeed compressions
* Normal-Performs compression at normal speed; normal reduction of data size
* AboveNormal-Performs enhanced compression compared to the normal compression; time consumption exceeds the normal compression
* Best-Performs the best compression; time consuming

### PDF Compliance

PDF elements are standardized under ISO for several constituencies. This section deals with the following standards that are supported by Essential PDF.

* PDF/A-This topic demonstrates PDF/A-1b standard that is used for archiving in environments like corporate, government, and library.
* PDF/X-This topic discusses the PDF/X-1a standard that is mainly available for standardizing printing and graphics.

## PDF/A-1b


The PDF/A formats specified in the ISO 19005 standards strive to provide a mechanism for representing electronic documents. These documents are represented in a manner that preserves their visual appearance over time, independent of the tools and systems used for creating, storing, or rendering the files. A key element to this reproducibility is the requirement for PDF/A documents to be 100 percent self-contained.

All the necessary information for displaying the document in the same manner every time is embedded in the file. This includes all visible content like text, raster images, vector graphics, fonts, and color information. The standard is based on PDF 1.4, and imposes some restrictions regarding the use of color, fonts, annotations, and other elements. 

* ISO 19005-1 Level B conformance (PDF/A-1b) ensures that the visual appearance of a document is preserved over long term. PDF/A-1b ensures that the document looks the same, when it is processed sometime in the future.

Creating a PDF/A-1b document is very simple. You must set PdfConformanceLevel to PdfA1B while creating an instance to the PDF document. PDF/A standard imposes some restrictions regarding the usage of color, fonts, annotations, and other elements. These restrictions are:

* The use of JavaScript is forbidden.
* Attaching any file to a PDF document is forbidden.
* Hyperlinking to a non-PDF file is forbidden.
* Security features are forbidden.
* Use of Form Fields is forbidden.
* Text containing HTML tags is forbidden.
* Supports the use of TrueType fonts only, does not support Type1 font.
* Supports the use of RGB color, does not support CMYK color.

### Validating PDF/A1-b

Adobe Acrobat Preflight tool is used to verify the compliance of a PDF document with the PDF/A standard.

You can verify the compliance of a PDF file by using the Preflight tool. Using the menu options select Advanced > Preflight > PDF/A compliance > Verify compliance with PDF/A-1b.

The following code example illustrates you on how to create PDF/A-1b compliant output:


{% highlight c# %}

//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument(PdfConformanceLevel.Pdf_A1B);

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics g = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f,FontStyle.Regular,12, false, true);

//Draws the text.

g.DrawString("Hello world!", font, brush, new PointF(20, 20));

document.Save("Output.pdf");

document.Close();

{% endhighlight %}




{% highlight vbnet %}

'Creates a new document with PDF/A standard.

Dim document As New PdfDocument(PdfConformanceLevel.Pdf_A1B)

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim g As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

g.DrawString("Hello world!", font, brush, New PointF(20, 20))

document.Save("Output.pdf")

document.Close()

{% endhighlight %}



## PDF/X-1a

PDF/X is a subset of the Adobe Portable Document Format (PDF) specification that exhibits best practices in graphic arts file exchange. PDF/X-1a restricts the content in the PDF document that does not directly serve the purpose of high-quality print production output, such as annotations, Java Actions, and embedded multimedia.

PDF/X-1a also eliminates the most common errors in file preparation. Sending the document as a PDF/X-1a file guarantees that font errors do not occur. This is because a file declared as complying with the PDF/X-1a standard meets the following requirements:

* All fonts and images must be embedded.
* All elements must be encoded as CMYK.

The following code example illustrates how to create PDF/A-1b compliant output:



{% highlight c# %}

//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument(PdfConformanceLevel.Pdf_X1A2001);

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics g = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f,FontStyle.Regular,12, false, true);

//Draws the text.

g.DrawString("Hello world!", font, brush, new PointF(20, 20));

document.Save("Output.pdf");

document.Close();

{% endhighlight %}




{% highlight vbnet %}

'Creates a new document with PDF/A standard.

Dim document As New PdfDocument(PdfConformanceLevel.Pdf_X1A2001)

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim g As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

g.DrawString("Hello world!", font, brush, New PointF(20, 20))

document.Save("Output.pdf")

document.Close()

{% endhighlight %}

