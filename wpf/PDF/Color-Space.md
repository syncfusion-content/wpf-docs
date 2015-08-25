---
layout: post
title: Color-Space
description: color space
platform: wpf
control: PDF
documentation: ug
---

# Color Space

When preparing your document, you may require colors in different color spaces. You can control it in the following two ways.

* Document level and
* Graphics level
## Document Level 


The PdfDocument class has ColorSpace property that is used to choose color spaces for new pages. Color spaces can be classified into three color space families.

Essential PDF now supports the following color spaces in each family.

* Device Color Spaces
* CIE-based Color Spaces
* ICC-based Color Spaces
### Device Color Space


Device color space simply describes the range of colors that a camera can see, a printer can print, or a monitor can display. These color spaces depend upon the device in which it is displayed. In PDF document Device, color spaces are used in following types.

* DeviceGray
* DeviceRGB
* DeviceCMYK



N> This property does not convert the entire document into different color spaces. It will also not have any impact on pages that have been created before the property value had changed. It just chooses the color space for pages created after the alteration.

### CIE-based Color Spaces

CIE-based color space in the PDF document is classified as, 

* CalGray
* CalRGB
* Lab

The code sample to draw a rectangle with CalGray brush is illustrated as follows. 

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquires graphics of the page.

PdfGraphics grapx = pdfPage.Graphics;

//Creates CalGray color space.

PdfCalGrayColorSpace calGrayCS = new PdfCalGrayColorSpace();

//Updates color values.

calGrayCS.Gamma = 0.7;

calGrayCS.WhitePoint = new double[] { 0.2, 1, 0.8 };

PdfCalGrayColor red1 = new PdfCalGrayColor(calGrayCS);

red1.Gray = 0.1;

PdfBrush brush = new PdfSolidBrush(red1);

RectangleF rect = new RectangleF(0, 0, 300, 300);

//Draws using the PdfBrush,

grapx.DrawRectangle(brush, rect);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim grapx As PdfGraphics = pdfPage.Graphics

'Creates CalGray color space.

Dim calGrayCS As New PdfCalGrayColorSpace()

'Update color values.

calGrayCS.Gamma = 0.7

calGrayCS.WhitePoint = New Double() {0.2, 1, 0.8}

Dim red1 As New PdfCalGrayColor(calGrayCS)

red1.Gray = 0.1

Dim brush As PdfBrush = New PdfSolidBrush(red1)

Dim rect As New RectangleF(0, 0, 300, 300)

'Draws using the PdfBrush.

grapx.DrawRectangle(brush, rect)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

The code sample to draw a rectangle with CalRGB brush is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquiring graphics of the page.

PdfGraphics grapx = pdfPage.Graphics;

PdfCalRGBColorSpace calRgbCS = new PdfCalRGBColorSpace();

//Updates color values.

calRgbCS.Gamma = new double[] { 1.6, 1.1, 2.5 };

calRgbCS.Matrix = new double[] { 1, 0, 0, 0, 1, 0, 0, 0, 1 };

calRgbCS.WhitePoint = new double[] { 0.2, 1, 0.8 };

PdfCalRGBColor green = new PdfCalRGBColor(calRgbCS);

green.Red = 0;

green.Green = 1;

green.Blue = 0;

PdfBrush brush = new PdfSolidBrush(green);

RectangleF rect = new RectangleF(0, 0, 300, 300);

//Draws using the PdfBrush,

grapx.DrawRectangle(brush, rect);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim grapx As PdfGraphics = pdfPage.Graphics

Dim calRgbCS As New PdfCalRGBColorSpace()

' Updates color values

calRgbCS.Gamma = New Double() {1.6, 1.1, 2.5}

calRgbCS.Matrix = New Double() {1, 0, 0, 0, 1, 0, _

0, 0, 1}

calRgbCS.WhitePoint = New Double() {0.2, 1, 0.8}

Dim green As New PdfCalRGBColor(calRgbCS)

green.Red = 0

green.Green = 1

green.Blue = 0

Dim brush As PdfBrush = New PdfSolidBrush(green)

Dim rect As New RectangleF(0, 0, 300, 300)

'Draws using the PdfBrush.

grapx.DrawRectangle(brush, rect)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

The code sample to draw a rectangle with Lab brush is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquires graphics of the page.

PdfGraphics grapx = pdfPage.Graphics;

//Creates Lab color space   .

PdfLabColorSpace calGrayCS1 = new PdfLabColorSpace();

//Updates color values.

calGrayCS1.Range = new double[] { 0.2, 1, 0.8, 23.5 };

calGrayCS1.WhitePoint = new double[] { 0.2, 1, 0.8 };

PdfLabColor red2 = new PdfLabColor(calGrayCS1);

red2.L = 90;

red2.A = 0.5;

red2.B = 20;

PdfBrush brush = new PdfSolidBrush(red2);

RectangleF rect = new RectangleF(0, 0, 300, 300);

//Draws using the PdfBrush.

grapx.DrawRectangle(brush, rect);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim grapx As PdfGraphics = pdfPage.Graphics

'Creates Lab color space. 

Dim calGrayCS1 As New PdfLabColorSpace()

'Updates color values.

calGrayCS1.Range = New Double() {0.2, 1, 0.8, 23.5}

calGrayCS1.WhitePoint = New Double() {0.2, 1, 0.8}

Dim red2 As New PdfLabColor(calGrayCS1)

red2.L = 90

red2.A = 0.5

red2.B = 20

Dim brush As PdfBrush = New PdfSolidBrush(red2)

Dim rect As New RectangleF(0, 0, 300, 300)

'Draws using the PdfBrushs.

grapx.DrawRectangle(brush, rect)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

### ICC-based Color Spaces

ICC based color uses ICC color profiles to create color for brush/pen to render shape or text in the PDF document. Three type of ICC based color spaces are:

* Special color spaces
* Indexed
* Seperation

The code sample used to draw a rectangle with Indexed ICC colorspace is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquires graphics of the page.

PdfGraphics grapx = pdfPage.Graphics;

//Creates ICCBased color space.

PdfCalRGBColorSpace calRgbCS = new PdfCalRGBColorSpace();

calRgbCS.Gamma = new double[] { 7.6, 5.1, 8.5 };

calRgbCS.Matrix = new double[] { 1, 0, 0, 0, 1, 0, 0, 0, 1 };

calRgbCS.WhitePoint = new double[] { 0.7, 1, 0.8 };

//Reads the ICC profile.

FileStream fs = new FileStream(@"input.icc", FileMode.Open, FileAccess.Read);

byte[] profileData = new byte[fs.Length];

fs.Read(profileData, 0, profileData.Length);

fs.Close();

//Instantiates ICC color space.

PdfICCColorSpace IccBasedCS = new PdfICCColorSpace();

IccBasedCS.ProfileData = profileData;

IccBasedCS.AlternateColorSpace = calRgbCS;

IccBasedCS.ColorComponents = 3;

IccBasedCS.Range = new double[] { 0.0, 1.0, 0.0, 1.0, 0.0, 1.0 };

PdfICCColor red = new PdfICCColor(IccBasedCS);

red.ColorComponents = new double[] { 1, 0, 1 };

PdfBrush brush = new PdfSolidBrush(red);

RectangleF rect = new RectangleF(0, 0, 300, 300);

//Draws using the PdfBrush.

grapx.DrawRectangle(brush, rect);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim grapx As PdfGraphics = pdfPage.Graphics

'Creates ICCBased color space.

Dim calRgbCS As New PdfCalRGBColorSpace()

calRgbCS.Gamma = New Double() {7.6, 5.1, 8.5}

calRgbCS.Matrix = New Double() {1, 0, 0, 0, 1, 0, _

0, 0, 1}

calRgbCS.WhitePoint = New Double() {0.7, 1, 0.8}

'Reads the ICC profile.

Dim fs As New FileStream("input.icc", FileMode.Open, FileAccess.Read)

Dim profileData As Byte() = New Byte(fs.Length - 1) {}

fs.Read(profileData, 0, profileData.Length)

fs.Close()

'Instantiates ICC color space.

Dim IccBasedCS As New PdfICCColorSpace()

IccBasedCS.ProfileData = profileData

IccBasedCS.AlternateColorSpace = calRgbCS

IccBasedCS.ColorComponents = 3

IccBasedCS.Range = New Double() {0.0, 1.0, 0.0, 1.0, 0.0, 1.0}

Dim red As New PdfICCColor(IccBasedCS)

red.ColorComponents = New Double() {1, 0, 1}

Dim brush As PdfBrush = New PdfSolidBrush(red)

Dim rect As New RectangleF(0, 0, 300, 300)

'Draws using the PdfBrush.

grapx.DrawRectangle(brush, rect)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}
The code sample used for separation color space is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquires graphics of the page.

PdfGraphics grapx = pdfPage.Graphics;

//Creates separation color space.

PdfExponentialInterpolationFunction function = new PdfExponentialInterpolationFunction(true);

float[] numArray = new float[3] { 90f, 0.5f, 20f };

function.C1 = numArray;

PdfLabColorSpace calLabCS = new PdfLabColorSpace();

calLabCS.Range = new double[] { 0.2, 1, 0.8, 23.5 };

calLabCS.WhitePoint = new double[] { 0.2, 1, 0.8 };

//Instantiates separation color space.

PdfSeparationColorSpace colorspace = new PdfSeparationColorSpace();

colorspace.AlternateColorSpaces = calLabCS;

colorspace.TintTransform = function;

colorspace.Colorant = "PANTONE Orange 021 C";

PdfSeparationColor color = new PdfSeparationColor(colorspace);

color.Tint = 0.7;

PdfBrush brush = new PdfSolidBrush(color);

RectangleF rect = new RectangleF(0, 0, 300, 300);

//Draws using the PdfBrush

grapx.DrawRectangle(brush, rect);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim grapx As PdfGraphics = pdfPage.Graphics

'Creates separation color space.

Dim [function] As New PdfExponentialInterpolationFunction(True)

Dim numArray As Single() = New Single(2) {90.0F, 0.5F, 20.0F}

 [function].C1 = numArray

Dim calLabCS As New PdfLabColorSpace()

calLabCS.Range = New Double() {0.2, 1, 0.8, 23.5}

calLabCS.WhitePoint = New Double() {0.2, 1, 0.8}

'Instantiates separation color space.

Dim colorspace As New PdfSeparationColorSpace()

colorspace.AlternateColorSpaces = calLabCS

colorspace.TintTransform = [function]

colorspace.Colorant = "PANTONE Orange 021 C"

Dim color As New PdfSeparationColor(colorspace)

color.Tint = 0.7

Dim brush As PdfBrush = New PdfSolidBrush(color)

Dim rect As New RectangleF(0, 0, 300, 300)

'Draw using the PdfBrush.

grapx.DrawRectangle(brush, rect)

'Save the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

## Graphics Level

The PdfGraphics class has its own ColorSpace property that chooses the color space for the objects drawn next. This property alternates the document settings and enables to change the color space as many times as you wish. Save and Restore methods saves and restores the color space, along with other graphics state parameters respectively.

The code sample to use colorspace in the graphics level is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Acquires graphics of the page.

PdfGraphics graphics = pdfPage.Graphics;

PdfPen pen = new PdfPen(Color.Red);

PdfBrush brush = new PdfSolidBrush(Color.Blue);

RectangleF rectangle = new RectangleF(0, 0, 100, 100);

//Defaults color space.

graphics.DrawRectangle(pen, brush, rectangle);

graphics.Save();

//GrayScale color space.

graphics.ColorSpace = PdfColorSpace.GrayScale;

graphics.DrawRectangle(pen, brush, rectangle);

//CMYK color space.

graphics.ColorSpace = PdfColorSpace.CMYK;

graphics.DrawRectangle(pen, brush, rectangle);

graphics.Restore();

//Default color space.

graphics.DrawRectangle(pen, brush, rectangle);             

//Draws using the PdfBrush.

graphics.DrawRectangle(brush, rectangle);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Acquires graphics of the page.

Dim graphics As PdfGraphics = pdfPage.Graphics

Dim pen As New PdfPen(Color.Red)

Dim brush As PdfBrush = New PdfSolidBrush(Color.Blue)

Dim rectangle As New RectangleF(0, 0, 100, 100)

'Defaults color space.

graphics.DrawRectangle(pen, brush, rectangle)

graphics.Save()

'GrayScale color space.

graphics.ColorSpace = PdfColorSpace.GrayScale

graphics.DrawRectangle(pen, brush, rectangle)

'CMYK color space.

graphics.ColorSpace = PdfColorSpace.CMYK

graphics.DrawRectangle(pen, brush, rectangle)

graphics.Restore()

'Default color space.

graphics.DrawRectangle(pen, brush, rectangle)

'Draws using the PdfBrush.

graphics.DrawRectangle(brush, rectangle)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}


N> You can change the color space as many times as you wish, however, you cannot alternate the color space for objects that have saved before.

Barcode

Bar codes provide a simple and inexpensive method of encoding text information that can be easily read by any inexpensive electronic reader. A bar code consists of series of parallel, adjacent bars, and spaces. Predefined bar and space patterns or "symbologies" are used to encode small strings of character data into a printed symbol. 

The basic structure of a bar code consists of a leading and trailing quiet zone, a start pattern, one or more data characters, optionally one or two check characters, and a stop pattern. Essential PDF supports 1D / linear barcodes and 2D barcode.

## Code39

Code 39 character set includes the digits 0-9, the letters A-Z (upper case only), and the following symbols: space, minus (-), plus (+), period (.), dollar sign ($), slash (/), and percent (%). A special start/stop character is placed at the beginning and end of each barcode. The barcode can be of any length, although more than 25 characters begins to push the bounds. Code 39 is just about the only type of barcode in common use that does not require a checksum.

{% highlight c# %}

//Creates a new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Draws Code39 barcode.

PdfCode39Barcode barcode = new PdfCode39Barcode(); 

//Sets height of the barcode.

barcode.BarHeight = 45; 

barcode.Text = "CODE39$"; 

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the Document

doc.Save("CODE39.pdf");
{% endhighlight %}


{% highlight vbnet %}

'Creates a new PDF Document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Draws Code39 barcode.

Dim barcode As New PdfCode39Barcode()

'Sets height of the barcode.

barcode.BarHeight = 45

barcode.Text = "CODE39$"

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE39.pdf")   
{% endhighlight %}

## Code39Extended

Code 39 Extended is an extended version of Code 39 that supports the ASCII character set. So with Code 39 Extended, you can also code the 26 lower letters (a-z) and the special characters you have on your keyboard. 

The following code example illustrates you on how to draw Code39Extended barcode.

{% highlight c# %}

//Creates new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Draws Code39 Extended barcode.

PdfCode39Barcode barcode = new PdfCode39Barcode(); 

//Sets height of the barcode.

barcode.BarHeight = 45; 

barcode.Text = "CODE39Ext"; 

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE39Ext.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates new PDF Document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Draws Code39 Extended barcode. 

Dim barcode As New PdfCode39Barcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

barcode.Text = "CODE39Ext"

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE39Ext.pdf")
{% endhighlight %}

## Code11

Code 11 is used primarily for labeling telecommunications equipment. The character set includes digits from 0 to 9, a dash (-), and a start or stop code. Each character is encoded with three bars and two spaces. Of these five elements, there can be two wide and three narrow elements, or one wide and four narrow elements. 

The following code example illustrates how to draw Code 11 Barcode.

{% highlight c# %}

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Draws Code11 barcode. 

PdfCode11Barcode barcode = new PdfCode11Barcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Encodes Start Stop symbol.

barcode.EncodeStartStopSymbols = true;

barcode.Text = "012345678"; 

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE11.pdf");

{% endhighlight %}

{% highlight vbnet %}

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Draws Code11 barcode. 

Dim barcode As New PdfCode11Barcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

'Encodes Start Stop symbol.

barcode.EncodeStartStopSymbols = True

barcode.Text = "012345678"

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document

doc.Save("CODE11.pdf")
{% endhighlight %}

## Codabar

CodaBar is a variable length symbology that performs encoding of the following 20 characters: 

0123456789-$:/. +ABCD. CodaBar uses the characters, A, B, C, and D, only as start and stop characters. Codabar is used in libraries, blood banks, the overnight package delivery industry, and a variety of other information processing applications. The following code example illustrates how to draw Codabar barcode.

{% highlight c# %}

//Draws Codabar barcode. 

PdfCodabarBarcode barcode = new PdfCodabarBarcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

barcode.Text = "0123";

//Creates new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODABAR.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Codabar barcode. 

Dim barcode As New PdfCodabarBarcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

barcode.Text = "0123"

'Creates new PDF Document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODABAR.pdf")
{% endhighlight %}

## Code32

It is mainly used for coding pharmaceuticals, cosmetics, and dietetics. Code 32 is mainly used to encode pharmaceutical products in Italy and has the following structure: 

* 'A' character (ASCII 65) that is not really encoded.
* 8 digits for Pharmacode (It generally begins with “ / “ and prefixed with 0).
* 1 digit for Checksum module 10, which is automatically calculated by Barcode Professional.

The value to be encoded (that is passed to Barcode Professional) must be 8 digits pharmacode (prefixed with '0' if necessary), because the 9th digit (the checksum) is automatically calculated by Barcode Professional products.

{% highlight c# %}



//Draws Code32 barcode. 

PdfCode32Barcode barcode = new PdfCode32Barcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Shows and enables check digit.

barcode.EnableCheckDigit = true;

barcode.ShowCheckDigit = true;

barcode.Text = "01234567";

//Creates new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the Document.

doc.Save("CODE32.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Code32 barcode. 

Dim barcode As New PdfCode32Barcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

'Show and enable check digit.

barcode.EnableCheckDigit = True

barcode.ShowCheckDigit = True

barcode.Text = "01234567"

'Creates new PDF Document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

 barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE32.pdf")     
{% endhighlight %}

## Code93

Code 93 was designed to complement and improve Code 39. It can represent the full ASCII character set by using combinations of 2 characters. Code 93 is a continuous, variable-length symbology and produces denser code. 

* The Standard Mode (default implementation) can encode uppercase letters (A through Z), digits (0 through 9), and special characters like the *, -, $, %, (Space), /, and +. 
* The Full ASCII Mode or Extended Version can encode all 128 ASCII characters. 
* The asterisk (*) is not a true encodable character, but is the start and stop 'symbol' for Code 93.



{% highlight c# %}

//Draws Code93 barcode. 

PdfCode93Barcode barcode = new PdfCode93Barcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

barcode.Text = "ABC 123456789";

//Creates new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the Document.

doc.Save("CODE93.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Code93 barcode. 

Dim barcode As New PdfCode93Barcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

barcode.Text = "ABC 123456789"

'Creates new PDF Document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE93.pdf")        
{% endhighlight %}

## Code93Extended

{% highlight c# %}

//Draws Code93 Extended barcode. 

PdfCode93ExtendedBarcode barcode = new PdfCode93ExtendedBarcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = true;

barcode.Text = "(abc) 123456789";

//Creates new PDF Document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE93Ext.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Code93 Extended barcode. 

Dim barcode As New PdfCode93ExtendedBarcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

'Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = True

barcode.Text = "(abc) 123456789"

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the Document.

doc.Save("CODE93Ext.pdf")
{% endhighlight %}

## Code128

Code 128 is a variable length, high density, alphanumeric, linear bar code symbology, capable of encoding the full 128-character ASCII character set and extended character sets. This Symbology includes a checksum digit for verification, and the barcode can also be verified character-by-character for parity of each data byte. 

Code 128 Code Sets 

* Code Set A (or Chars Set A) includes all of the standard upper case U.S. alphanumeric keyboard characters and punctuation characters together with the control characters, (i.e. characters with ASCII values from 0 to 95 inclusive), and seven special characters. 
* Code Set B (or Chars Set B) includes all of the standard upper case alphanumeric keyboard characters and punctuation characters together with the lower case alphabetic characters (i.e. characters with ASCII values from 32 to 127 inclusive), and seven special characters. 
* Code Set C (or Chars Set C) includes the set of 100 digit pairs from 00 to 99 inclusive, as well as three special characters. This allows numeric data to be encoded as two data digits per symbol character, at effectively twice the density of standard data. 

Code 128 Special characters 

The last seven characters of Code Sets A and B (character values 96 - 102) and the last three characters of Code Set C (character values 100 - 102) are special non-data characters with no ASCII character equivalents that have particular significance to the bar code reading device.

## Code128A

Code Set A (or Characters Set A) includes all of the standard upper case U.S. alphanumeric keyboard characters and punctuation characters together with the control characters, (i.e. characters with ASCII values from 0 to 95 inclusive), and seven special characters. 

{% highlight c# %}



//Draws Code128A barcode. 

PdfCode128ABarcode barcode = new PdfCode128ABarcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = true;

//Enables Check digit

barcode.EnableCheckDigit = true;

//Shows Check digit.

barcode.ShowCheckDigit = true;

barcode.Text = "ABCD 12345";

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE128A.pdf");

{% endhighlight %}

{% highlight vbnet %}

'Draws Code128A barcode. 

Dim barcode As New PdfCode128ABarcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

'Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = True

'Enables Check digit.

barcode.EnableCheckDigit = True

'Shows Check digit.

barcode.ShowCheckDigit = True

barcode.Text = "ABCD 12345"

'Creates new PDF document.

 Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE128A.pdf")
{% endhighlight %}

## Code128B

Code Set B (or Characters Set B) includes all of the standard upper case alphanumeric keyboard characters and punctuation characters together with the lower case alphabetic characters (i.e. characters with ASCII values from 32 to 127 inclusive), and seven special characters. 

{% highlight c# %}



//Draws Code128B barcode. 

PdfCode128BBarcode barcode = new PdfCode128BBarcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = true;

//Enables Check digit.

barcode.EnableCheckDigit = true;

barcode.Text = "12345 abcd";

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE128B.pdf");

{% endhighlight %}

{% highlight vbnet %}

'Draws Code128B barcode. 

Dim barcode As New PdfCode128BBarcode()

'Sets height of the barcode.

barcode.BarHeight = 45

'Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = True

'Enables Check digit.

barcode.EnableCheckDigit = True

barcode.Text = "12345 abcd"

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE128B.pdf")   
{% endhighlight %}

## Code128C

Code Set C (or Characters Set C) includes the set of 100 digit pairs from 00 to 99, as well as three special characters. This allows numeric data to be encoded as two data digits per symbol character at effectively twice the density of standard data. 

{% highlight c# %}

//Draws Code128C barcode. 

PdfCode128CBarcode barcode = new PdfCode128CBarcode(); 

//Sets height of the barcode. 

barcode.BarHeight = 45;

//Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = true;

//Enables Check digit.

barcode.EnableCheckDigit = true;

barcode.Text = "001122334455";

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("CODE128C.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Code128C barcode. 

Dim barcode As New PdfCode128CBarcode()

'Sets height of the barcode. 

barcode.BarHeight = 45

'Encodes Start Stop Symbol.

barcode.EncodeStartStopSymbols = True

'Enables Check digit

barcode.EnableCheckDigit = True

barcode.Text = "001122334455"

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("CODE128C.pdf")
{% endhighlight %}

## Data Matrix

DataMatrix barcode is a two dimensional barcode that consists of a grid of dark and light dots or blocks forming square or rectangular symbol. The data encoded in the barcode can either be number or alphanumeric. The PdfDataMatrixBarcode class available in Syncfusion.Pdf.Barcode namespace sets the suitable encoding type and size for the input data. However, the size, encoding type, and dimension of individual blocks can also be set using these properties.

Use case scenario 

The DataMatrix bar codes are widely used in printed media as labels and letters. It can easily be read by a bar code reader and also by mobile phones. 

Property Table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Data Type </th></tr>
<tr>
<td>
Encoding </td><td>
Gets or sets the encoding type. </td><td>
PdfDataMatrixEncoding </td></tr>
<tr>
<td>
Size </td><td>
Gets or sets the size of the symbol. </td><td>
PdfDataMatrixSize </td></tr>
<tr>
<td>
Text </td><td>
Gets or sets the data. </td><td>
String </td></tr>
<tr>
<td>
XDimension </td><td>
Gets or sets the dimension of the blocks.</td><td>
Float </td></tr>
</table>


{% highlight c# %}



//Draws Data Matrix barcode.

PdfDataMatrixBarcode barcode = new PdfDataMatrixBarcode("Syncfusion");

//Sets XDimension.

barcode.XDimension = 3;

//Sets Encoding.

barcode.Encoding = PdfDataMatrixEncoding.ASCII;

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70 ));

//Saves the document.

doc.Save("DataMatrix.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws Data Matrix barcode.

Dim barcode As New PdfDataMatrixBarcode("Syncfusion")

'Sets XDimension.

barcode.XDimension = 3

'Sets Encoding.

barcode.Encoding = PdfDataMatrixEncoding.ASCII

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("DataMatrix.pdf")     
{% endhighlight %}

## QR Barcode

QR Barcode is a two-dimensional barcode that consists of a grid of dark and light dots or blocks that forms a square. The data encoded in the barcode can be numeric, alphanumeric, or JIS8 characters. The PdfQRBarcode class available in Syncfusion.Pdf.Barcode namespace sets the suitable version, error correction level and size for the input data. However, the version, error correction level and size of individual blocks can also be set using these properties.

{% highlight c# %}



//Draws QR Barcode.

PdfQRBarcode barcode = new PdfQRBarcode();

//Sets Error Correction Level.

barcode.ErrorCorrectionLevel = PdfErrorCorrectionLevel.High;

//Sets XDimension.

barcode.XDimension = 3;

barcode.Text = "http://www.syncfusion.com";

//Creates new PDF document.

PdfDocument doc = new PdfDocument();

//Adds new page to PDF document.

PdfPage page = doc.Pages.Add();

//Prints barcode on to the PDF. 

barcode.Draw(page, new PointF(25, 70));

//Saves the document.

doc.Save("QRBarcode.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Draws QR Barcode.

 Dim barcode As New PdfQRBarcode()

'Sets Error Correction Level.

barcode.ErrorCorrectionLevel = PdfErrorCorrectionLevel.High

'Sets XDimension

barcode.XDimension = 3

barcode.Text = "http://www.syncfusion.com"

'Creates new PDF document.

Dim doc As New PdfDocument()

'Adds new page to PDF document.

Dim page As PdfPage = doc.Pages.Add()

'Prints barcode on to the PDF. 

barcode.Draw(page, New PointF(25, 70))

'Saves the document.

doc.Save("QRBarcode.pdf")  
{% endhighlight %}

## Action

Essential PDF supports different actions triggered by different events and user interactions. There are lots of possible actions such as playing a particular sound or movie, launching an application or URI, and so on.

Essential PDF supports the following types of actions.

* PdfSoundAction that plays the specified music file.
* PdfJavaScriptAction thatexecutes specified PDF JavaScript code.
* PdfUriAction that launches the specified URI.
* PdfGoToAction that goes to the specified page of the document.
* PdfLaunchAction that launches the application or opens the document.
* PdfNamedAction that goes to the named destination: next, previous, first or last page.
* PdfSubmitAction that submits the data that is entered into the PDF form.
* PdfResetAction that resets the fields of the PDF form.

Following are the actions for Document Object:

* AfterOpen action to be performed after the document is opened.
* AfterPrint action to be performed after the document is printed.
* AfterSave action to be performed after the document is saved.
* BeforeClose action to be performed before the document is closed.
* BeforePrint action to be performed before the document is printed.
* BeforeSave action to be performed before the document is saved.

Following are the actions for Annotation Object:

* GotFocus action to be performed when the annotation gets focus.
* LostFocus action to be performed when the annotation loses focus.
* MouseEnter action to be performed when the cursor enters the active area of the annotation.
* MouseLeave action to be performed when the cursor leaves the active area of the annotation.
* MouseDown action to be performed when the mouse button is pressed inside the active area of the annotation.
* MouseUp action to be performed when the mouse button is released inside the active area of the annotation.

Following are the actions for Form Field Object:

* Calculate JavaScript action to be performed to recalculate the value of the field.
* Format JavaScript action to be performed before the field is formatted to display the value.
* Validate JavaScript action to be performed when the value of the field is changed.
* KeyPressed JavaScript action to be performed when the user types, key-stroke into a text field or combo box, or modifies the selection in a scrollable list box.
## Sound Action


Sound action plays a specified music file in the PDF document. Volume and repeat can be specified for the sound action.

{% highlight c# %}



//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument();

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

g.DrawString("Play the specified music file, when PDF document is opened", font, brush, new PointF(20, 20));

//Sets the Sound action.

PdfSoundAction soundAction = new PdfSoundAction("Startup.wav");

document.Actions.AfterOpen = soundAction;

//Saves and close the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

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

g.DrawString("Play the specified music file, when PDF document is opened", font, brush, New PointF(20, 20))

'Sets the Sound action.

Dim soundAction As New PdfSoundAction("Startup.wav")

document.Actions.AfterOpen = soundAction

'Saves and closes the PDF document.

document.Save("Output.pdf")
{% endhighlight %}

## JavaScript Action

A JavaScript action allows execution of JavaScript code embedded in the PDF document.

{% highlight c# %}



//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument();

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

g.DrawString("Alert box will pop up, when PDF document is opened", font, brush, new PointF(20, 20));

//Sets the JavaScript action.

PdfJavaScriptAction javaScriptAction = new PdfJavaScriptAction("app.alert(\"Hello World!!!\")");

document.Actions.AfterOpen = javaScriptAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

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

g.DrawString("Alert box will pop up, when PDF document is opened", font, brush, New PointF(20, 20))

'Sets the JavaScript action.

Dim javaScriptAction As New PdfJavaScriptAction("app.alert(""Hello World!!!"")")

document.Actions.AfterOpen = javaScriptAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## URI Action 

URI action allows you displaying a hypertext link in a web browser. Next property of an action is used to specify the queue of actions.

{% highlight c# %}



//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument();

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

g.DrawString("Alert box will pop up, when PDF document is opened", font, brush, new PointF(20, 20));

//Sets URI action.

PdfUriAction uriAction = new PdfUriAction("http://www.syncfusion.com");

//Sets JavaScript action.

PdfJavaScriptAction javaScriptAction = new PdfJavaScriptAction("app.alert(\"The webpage has been opened\")");

//Sets action queue.

uriAction.Next = javaScriptAction;

document.Actions.AfterOpen = uriAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

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

g.DrawString("Alert box will pop up, when PDF document is opened", font, brush, New PointF(20, 20))

'Sets URI action

Dim uriAction As New PdfUriAction("http://www.syncfusion.com")

'Sets JavaScript action.

Dim javaScriptAction As New PdfJavaScriptAction("app.alert(""The webpage has been opened"")")

'Sets action queue.

uriAction.[Next] = javaScriptAction

document.Actions.AfterOpen = uriAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## GoTo Action 

GoTo action displays the specified page in the current document. The location can be specified for the destination page. 

{% highlight c# %}



//Creates a new document.

PdfDocument document = new PdfDocument();

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f,FontStyle.Regular,12, false, true);

//Draws the text.

graphics.DrawString("Page 1", font, brush, new PointF(20, 20));

//Adds second page.

PdfPage page1 = document.Pages.Add();

page1.Graphics.DrawString("Page 2", font, brush, new PointF(0, 100));

//Sets the Javascript action.

PdfGoToAction javaScriptAction = new PdfGoToAction(page1) ;

//Sets destination location.

javaScriptAction.Destination = new PdfDestination(page1, new PointF(0,100));

document.Actions.AfterOpen = javaScriptAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

graphics.DrawString("Page 1", font, brush, New PointF(20, 20))

'Adds second page.

Dim page1 As PdfPage = document.Pages.Add()

page1.Graphics.DrawString("Page 2", font, brush, New PointF(0, 100))

'Sets the JavaScript action.

Dim javaScriptAction As New PdfGoToAction(page1)

'Sets destination location.

javaScriptAction.Destination = New PdfDestination(page1, New PointF(0, 100))

document.Actions.AfterOpen = javaScriptAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Launch Action 

Launch action allows execution of an external application or file.

{% highlight c# %}



//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument();

//Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f,FontStyle.Regular,12, false, true);

//Draws the text.

graphics.DrawString("External application document will open, when PDF document is opened", font, brush, new PointF(20, 20));

//Creates launch action to start the application.

PdfLaunchAction launchAction = new PdfLaunchAction("Essential PDF.rtf");

document.Actions.AfterOpen = launchAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

'Draws the text.

graphics.DrawString("External application document will open, when PDF document is opened", font, brush, New PointF(20, 20))

'Creates a launch action to start the application.

Dim launchAction As New PdfLaunchAction("Essential PDF.rtf")

document.Actions.AfterOpen = launchAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Named Action

Named action allows execution of predefined PDF actions. The following predefined PDF actions are available: go to next page, go to prev page, go to first page, and go to last page. 

{% highlight c# %}



//Creates a new document with PDF/A standard.

PdfDocument document = new PdfDocument();

//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);

float fontSize = 20f;

Font f = new Font("Arial", fontSize, FontStyle.Regular);

//Sets the font.

PdfFont font = new PdfTrueTypeFont(f, FontStyle.Regular, 12, false, true);

for (int i = 0; i < 10; i++)

{

 //Adds a page.

PdfPage page = document.Pages.Add();

//Creates PDF graphics for the page.

PdfGraphics graphics = page.Graphics;

//Draws the text.

graphics.DrawString("Page No : " + (i + 1).ToString(), font, brush, new PointF(20, 20));

}

//Creates launch action to start the application.

PdfNamedAction namedAction = new PdfNamedAction(PdfActionDestination.LastPage);

document.Actions.AfterOpen = namedAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a new document with PDF/A standard.

Dim document As New PdfDocument()

'Creates a solid brush.

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

Dim fontSize As Single = 20.0F

Dim f As New Font("Arial", fontSize, FontStyle.Regular)

'Sets the font.

Dim font As PdfFont = New PdfTrueTypeFont(f, FontStyle.Regular, 12, False, True)

For i As Integer = 0 To 9

'Adds a page.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF graphics for the page.

Dim graphics As PdfGraphics = page.Graphics

'Draws the text.

graphics.DrawString("Page No : " + (i + 1).ToString(), font, brush, New PointF(20, 20))

Next

'Creates launch action to start the application.

Dim namedAction As New PdfNamedAction(PdfActionDestination.LastPage)

document.Actions.AfterOpen = namedAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Submit Action

Submit action allows submission of data that is entered into the PDF form.

{% highlight c# %}



//Creates a PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page.

PdfPage page = document.Pages.Add();

Font f = new Font("Arial", 12);

PdfTrueTypeFont font = new PdfTrueTypeFont(f);

page.Graphics.DrawString("First Name", font, PdfBrushes.Red, new PointF(0, 0));

//Creates a Text box field.

PdfTextBoxField textBoxField = new PdfTextBoxField(page, "FirstName");

//Sets properties to the textbox.

textBoxField.BorderColor = new PdfColor(Color.Gray);

textBoxField.BorderStyle = PdfBorderStyle.Beveled;

textBoxField.Bounds = new RectangleF(80, 0, 100, 20);

textBoxField.ToolTip = "First Name";

//Adds the form field to the document.

document.Form.Fields.Add(textBoxField);

//Creates a Button field.

PdfButtonField submitButton = new PdfButtonField(page, "Submit data");

submitButton.Bounds = new RectangleF(100, 60, 50, 20);

submitButton.ToolTip = "Submit";

document.Form.Fields.Add(submitButton);

//Adds a new page.

page = document.Pages.Add();

//Creates instance of submit action, which submits the data of the form fields to the mentioned URL.

PdfSubmitAction submitAction = new PdfSubmitAction("http://www.syncfusion.com/Submit.aspx");

submitAction.DataFormat = SubmitDataFormat.Html;

submitButton.Actions.GotFocus = submitAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim f As New Font("Arial", 12)

Dim font As New PdfTrueTypeFont(f)

page.Graphics.DrawString("First Name", font, PdfBrushes.Red, New PointF(0, 0))

'Creates a Text box field.

Dim textBoxField As New PdfTextBoxField(page, "FirstName")

'Sets properties to the textbox.

textBoxField.BorderColor = New PdfColor(Color.Gray)

textBoxField.BorderStyle = PdfBorderStyle.Beveled

textBoxField.Bounds = New RectangleF(80, 0, 100, 20)

textBoxField.ToolTip = "First Name"

'Adds the form field to the document.

 document.Form.Fields.Add(textBoxField)

'Creates a Button field.

Dim submitButton As New PdfButtonField(page, "Submit data")

submitButton.Bounds = New RectangleF(100, 60, 50, 20)

submitButton.ToolTip = "Submit"

document.Form.Fields.Add(submitButton)

'Adds a new page.

page = document.Pages.Add()

'Creates instance of submit action, which submits the data of the form fields to the mentioned URL.

Dim submitAction As New PdfSubmitAction("http://www.syncfusion.com/Submit.aspx")

submitAction.DataFormat = SubmitDataFormat.Html

submitButton.Actions.GotFocus = submitAction

'Saves and closes the PDF document

document.Save("Output.pdf")

document.Close()
{% endhighlight %}

## Reset Action 

Reset action allows resetting of all form fields in the PDF document.

{% highlight c# %}



//Creates a PDF document.

PdfDocument document = new PdfDocument();

//Adds a new page.

PdfPage page = document.Pages.Add();

Font f = new Font("Arial", 12);

PdfTrueTypeFont font = new PdfTrueTypeFont(f);

page.Graphics.DrawString("First Name", font, PdfBrushes.Red, new PointF(0, 0));

//Creates a Text box field.

PdfTextBoxField textBoxField = new PdfTextBoxField(page, "FirstName");

//Sets properties to the textbox.

textBoxField.BorderColor = new PdfColor(Color.Gray);

textBoxField.BorderStyle = PdfBorderStyle.Beveled;

textBoxField.Bounds = new RectangleF(80, 0, 100, 20);

textBoxField.ToolTip = "First Name";

//Adds form field to the document.

document.Form.Fields.Add(textBoxField);

//Creates a Button field.

PdfButtonField submitButton = new PdfButtonField(page, "Clear");

submitButton.Bounds = new RectangleF(100, 60, 50, 20);

submitButton.ToolTip = "Clear";

document.Form.Fields.Add(submitButton);

//Adds a new page.

page = document.Pages.Add();

//Creates an instance of reset action.

PdfResetAction resetAction = new PdfResetAction();

submitButton.Actions.GotFocus = resetAction;

//Saves and closes the PDF document.

document.Save("Output.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}



'Creates a PDF document.

Dim document As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = document.Pages.Add()

Dim f As New Font("Arial", 12)

Dim font As New PdfTrueTypeFont(f)

page.Graphics.DrawString("First Name", font, PdfBrushes.Red, New PointF(0, 0))

'Creates a Text box field.

Dim textBoxField As New PdfTextBoxField(page, "FirstName")

'Sets properties to the textbox.

textBoxField.BorderColor = New PdfColor(Color.Gray)

textBoxField.BorderStyle = PdfBorderStyle.Beveled

textBoxField.Bounds = New RectangleF(80, 0, 100, 20)

textBoxField.ToolTip = "First Name"

'Adds form field to the document.

document.Form.Fields.Add(textBoxField)

'Creates a Button field.

Dim submitButton As New PdfButtonField(page, "Submit data")

submitButton.Bounds = New RectangleF(100, 60, 50, 20)

submitButton.ToolTip = "Submit"

document.Form.Fields.Add(submitButton)

'Adds a new page.

page = document.Pages.Add()

'Creates an instance of submit action. It submits data of the form fields to the mentioned URL.

Dim submitAction As New PdfSubmitAction("http://www.syncfusion.com/Submit.aspx")

submitAction.DataFormat = SubmitDataFormat.Html

submitButton.Actions.GotFocus = submitAction

'Saves and closes the PDF document.

document.Save("Output.pdf")

document.Close()
{% endhighlight %}


