---
layout: post
title: Document-Conversion
description: document conversion
platform: wpf
control: PDF
documentation: ug
---

# Document Conversion

This section explains about conversion of different file format documents (HTML, word, tiff, RTF, XPS) into PDF document.

## HTML To PDF

The core of a web page is a file written in Hypertext Markup Language (HTML). When you convert a web page to PDF, the HTML file and all associated files such as JPEG images, cascading style sheets, text files, image maps, and forms are included in the conversion process. The resulting PDF behaves much like the original web page. For example, the images, links, and image maps function normally within the PDF.

Syncfusion products support conversion of the HTML and webpages into PDF document. This is done using two different rendering engines. They are

* IE Rendering 
* Gecko Rendering

## IE Rendering


WebPages and HTML pages can be imported to PDF using the HtmlConverter. The HTMLConverter converts the HTML web page into a Bitmap or Metafile image using MSHTML.

MSHTML is a rendering library used to render HTML documents. The MSHTML library is like an engine that is used to drive the Internet Explorer.

Essential PDF renders the converted image into the PDF. You can convert a web page to PDF, either as Bitmap or Metafile types.

* Rendering web pages as Bitmap provides reasonable performance
* Rendering web pages as Metafile provides high resolution

This section covers the following:

* Converting Methods
* HTMLConvertor Options 

### Converting Methods

HTML documents can be converted to PDF through the following methods:

* ConvertToImage
* FromString


#### ConvertToImage

The ConvertToImage method converts the URL into an image. It recognizes tables, images, lists, etc. The URL parameter can be a HTTP or HTTPS address such as "http://www.server.com/path/file.html", or a local physical path such as "c:\path\file.html".

N> If you want to open a dynamically generated document such as .asp or aspx file, you need to invoke it through HTTP even if this file is local to your own script.

The overloaded ConvertToImage method enables converting an HTML page to an image with AspectRatio to maintain the ratio of the image dimension. This prevents text truncation at the corners.


{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage page = pdfDocument.Pages.Add();

SizeF pageSize = page.Size;

AspectRatio dimension = AspectRatio.None;

//Declares the layout format for the image.

PdfLayoutFormat bitmapFormat = new PdfLayoutFormat();

bitmapFormat.Break = PdfLayoutBreakType.FitPage;

bitmapFormat.Layout = PdfLayoutType.Paginate;

HtmlConverter html = new HtmlConverter();

//Converts to Bitmap.

Image img = html.ConvertToImage("www.google.com", ImageType.Bitmap, (int)pageSize.Width, (int)pageSize.Height, dimension);

PdfImage image = new PdfBitmap(img);

//Draws bitmap in PdfPage.

if (img.Size.Width > pageSize.Width)

else

image.Draw(page, new RectangleF(0, 0, pageSize.Width, -1), bitmapFormat);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim page As PdfPage = pdfDocument.Pages.Add()

Dim pageSize As SizeF = page.Size

Dim dimension As AspectRatio = AspectRatio.None

'Declares layout format for the image.

Dim bitmapFormat As New PdfLayoutFormat()

bitmapFormat.Break = PdfLayoutBreakType.FitPage

bitmapFormat.Layout = PdfLayoutType.Paginate

Dim html As New HtmlConverter()

'Converts to Bitmap.

Dim img As Image = html.ConvertToImage("www.google.com", ImageType.Bitmap, CInt(pageSize.Width), CInt(pageSize.Height), dimension)

Dim image As PdfImage = New PdfBitmap(img)

'Draws bitmap in PdfPage.

If img.Size.Width > pageSize.Width Then

image.Draw(page, New RectangleF(0, 0, img.Width, -1), bitmapFormat)

Else

image.Draw(page, New RectangleF(0, 0, pageSize.Width, -1), bitmapFormat)

End If

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

N> HTML To PDF conversion allows text selection and search within the generated document. However, in machines where IE9 is installed, document would contain Bitmap image of the converted page/file thereby restricting text selection and search. This behavior can be changed for certain webpages by changing the registry value. For more details, refer to Frequently Asked Questions section.

#### Authentication

You can use the ConvertToImage method to access the authenticated web pages by passing its user credential values as arguments. The following code example illustrates this:



{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage page = pdfDocument.Pages.Add();

SizeF pageSize = page.Size;

AspectRatio dimension = AspectRatio.None;

//Declares the layout format for the image.

PdfLayoutFormat bitmapFormat = new PdfLayoutFormat();

bitmapFormat.Break = PdfLayoutBreakType.FitPage;

bitmapFormat.Layout = PdfLayoutType.Paginate;

HtmlConverter html = new HtmlConverter();

//Converts to Bitmap.

Image img = html.ConvertToImage("www.google.com", ImageType.Bitmap, (int)pageSize.Width, (int)pageSize.Height, dimension, "UserName", "Passwprd");

PdfImage image = new PdfBitmap(img);

//Draws bitmap in PdfPage.

if (img.Size.Width > pageSize.Width)

image.Draw(page, new RectangleF(0, 0, img.Width, -1), bitmapFormat);

else

image.Draw(page, new RectangleF(0, 0, pageSize.Width, -1), bitmapFormat);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim page As PdfPage = pdfDocument.Pages.Add()

Dim pageSize As SizeF = page.Size

Dim dimension As AspectRatio = AspectRatio.None

'Declares the layout format for the image.

Dim bitmapFormat As New PdfLayoutFormat()

bitmapFormat.Break = PdfLayoutBreakType.FitPage

bitmapFormat.Layout = PdfLayoutType.Paginate

Dim html As New HtmlConverter()

'Converts to Bitmap.

Dim img As Image = html.ConvertToImage("www.google.com", ImageType.Bitmap, CInt(pageSize.Width), CInt(pageSize.Height), dimension, "UserName", "Passwprd")

Dim image As PdfImage = New PdfBitmap(img)

'Draws bitmap in PdfPage.

If img.Size.Width > pageSize.Width Then

image.Draw(page, New RectangleF(0, 0, img.Width, -1), bitmapFormat)

Else

image.Draw(page, New RectangleF(0, 0, pageSize.Width, -1), bitmapFormat)

End If

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

#### FromString

FromString method renders HTML from the string to the image. The following code example illustrates this:



{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to PDF document.

PdfPage page = pdfDocument.Pages.Add();

SizeF pageSize = page.Size;

AspectRatio dimension = AspectRatio.None;

string html = "<html><body><p>Hello World</p></body></html>";

//Declares layout format for the image.

PdfLayoutFormat bitmapFormat = new PdfLayoutFormat();

bitmapFormat.Break = PdfLayoutBreakType.FitPage;

bitmapFormat.Layout = PdfLayoutType.Paginate;

//Initialzes the HTML converter.

HtmlConverter converter = new HtmlConverter();

//Converts HTML to PDF.

Image result = converter.FromString(html, ImageType.Metafile, (int)pageSize.Width, -1, AspectRatio.KeepWidth);

//Renders image in PDF document.

PdfImage pdfImage = PdfImage.FromImage(result);

pdfImage.Draw(page, PointF.Empty, bitmapFormat);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to PDF document.

Dim page As PdfPage = pdfDocument.Pages.Add()

Dim pageSize As SizeF = page.Size

Dim dimension As AspectRatio = AspectRatio.None

Dim html As String = "<html><body><p>Hello World</p></body></html>";

'Declaring the layout format for the image.

Dim bitmapFormat As New PdfLayoutFormat()

bitmapFormat.Break = PdfLayoutBreakType.FitPage

bitmapFormat.Layout = PdfLayoutType.Paginate

'Initialzes the HTML converter.

Dim converter As New HtmlConverter()

'Converts HTML to PDF.

Dim result As Image = converter.FromString(html, ImageType.Metafile, CInt(pageSize.Width), -1, AspectRatio.KeepWidth)

'Renders image in PDF document.

Dim pdfImage__1 As PdfImage = PdfImage.FromImage(result)

pdfImage__1.Draw(page, PointF.Empty, bitmapFormat)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

N> Both ConvertToImage() and FromString() methods are used to convert the HTML pages whose height is less than 32767 pixels as image, and the options like  EnableHyperlinks, EnableJavascript  and AutoDetectPageBreak has no effect.


#### HtmlConverter Options

HtmlConverter provides the following options to control HtmlToPDF conversions.

* EnableJavaScript
* AutoDetectPageBreak
* Enable Hyperlinks

#### EnableJavaScript

You can control the JavaScript by using the EnableJavaScript property of the HtmlConverter class library. By default this property is set to False. So the JavaScript code is disabled during conversion. Set the EnableJavaScript property to True to activate the JavaScript code during conversion.

N> If JavaScript code is not executed by setting the EnableJavaScript property, it means the Internet Security Settings on the server does not allow the JavaScript execution.

#### Enable Hyperlink

Essential PDF provides support to enabe or disable the live hyperlinks in PDF when converting web pages to PDF. The following code example illustrates this:

#### AutoDetectPageBreak 

The HtmlConverter supports custom page breaks with standard CSS styles like page-break-before: always and page-break-after: always that can be applied to any HTML object. You can enable custom page breaks by setting the AutoDetectPageBreak property to True.

The following code example illustrates the use of EnableJavaScript, EnableHyperlink and AutoDetectPageBreak:



{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to PDF document.

PdfPage page = pdfDocument.Pages.Add();

SizeF pageSize = page.Size;

AspectRatio dimension = AspectRatio.None;

//Declares layout format for the image.

PdfLayoutFormat bitmapFormat = new PdfLayoutFormat();

bitmapFormat.Break = PdfLayoutBreakType.FitPage;

bitmapFormat.Layout = PdfLayoutType.Paginate;

HtmlConverter html = new HtmlConverter();

//Activates JavaScript.

html.EnableJavaScript = true;

//Enables Hyperlink.

html.EnableHyperlinks = true;

//Activates the Page Break.

html.AutoDetectPageBreak = true;

//Converts to Bitmap.

Image img = html.ConvertToImage("www.google.com", ImageType.Bitmap, (int)pageSize.Width, (int)pageSize.Height, dimension);

PdfImage image = new PdfBitmap(img);

image.Draw(page, new RectangleF(0, 0, pageSize.Width, -1), bitmapFormat);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to PDF document.

Dim page As PdfPage = pdfDocument.Pages.Add()

Dim pageSize As SizeF = page.Size

Dim dimension As AspectRatio = AspectRatio.None

'Declares layout format for the image.

Dim bitmapFormat As New PdfLayoutFormat()

bitmapFormat.Break = PdfLayoutBreakType.FitPage

bitmapFormat.Layout = PdfLayoutType.Paginate

Dim html As New HtmlConverter()

'Activates JavaScript.

html.EnableJavaScript = True

'Enables Hyperlink.

html.EnableHyperlinks = True

'Activates the Page Break.

html.AutoDetectPageBreak = True

'Converts to Bitmap.

Dim img As Image = html.ConvertToImage("www.google.com", ImageType.Bitmap, CInt(pageSize.Width), CInt(pageSize.Height), dimension)

Dim image As PdfImage = New PdfBitmap(img)

image.Draw(page, New RectangleF(0, 0, pageSize.Width, -1), bitmapFormat)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}

#### Rendering HTML page without Splitting

To avoid images and text split across page breaks when rendering a large Meta file with images and text in a PDF document, disable the SplitTextLines and SplitImages properties of PdfMetafileLayoutFormat class. The following code illustrates this:



{% highlight c# %}

//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to PDF document.

PdfPage page = pdfDocument.Pages.Add();

SizeF pageSize = page.Size;

AspectRatio dimension = AspectRatio.None;

//Declares layout format for the image.

PdfMetafileLayoutFormat format = new PdfMetafileLayoutFormat();

format.SplitTextLines = false;

format.SplitImages = false;

HtmlConverter html = new HtmlConverter();

//Activates JavaScript.

html.EnableJavaScript = true;

//Enables Hyperlink.

html.EnableHyperlinks = true;

//Activates the Page Break.

html.AutoDetectPageBreak = true;

//Converts to Bitmap.

Image img = html.ConvertToImage("www.google.com", ImageType.Bitmap, (int)pageSize.Width, (int)pageSize.Height, dimension);

PdfImage image = new PdfBitmap(img);

image.Draw(page, new RectangleF(0, 0, pageSize.Width, -1), format);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}




{% highlight vbnet %}

'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document.

Dim page As PdfPage = pdfDocument.Pages.Add()

Dim pageSize As SizeF = page.Size

Dim dimension As AspectRatio = AspectRatio.None

'Declares layout format for the image.

Dim format As New PdfMetafileLayoutFormat()

format.SplitTextLines = False

format.SplitImages = False

Dim html As New HtmlConverter()

'Activates JavaScript.

html.EnableJavaScript = True

'Enables Hyperlink.

html.EnableHyperlinks = True

'Activates the Page Break.

html.AutoDetectPageBreak = True

'Converts to Bitmap.

Dim img As Image = html.ConvertToImage("www.google.com", ImageType.Bitmap, CInt(pageSize.Width), CInt(pageSize.Height), dimension)

Dim image As PdfImage = New PdfBitmap(img)

image.Draw(page, New RectangleF(0, 0, pageSize.Width, -1), format)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)

{% endhighlight %}


### Gecko Rendering

HTML to PDF Conversion using Gecko Rendering Engine

Gecko is a free and open source layout engine used in many applications developed by Mozilla Foundation and the Mozilla Corporation (notably the Firefox web browser), as well as in many other open source software projects. Essential PDF also supports converting Webpages to PDF using Mozilla’s Gecko rendering engine. 

#### Use Case Scenario

Starting with Internet Explorer 9, Microsoft has made a series of core-architectural changes to Internet Explorer.  One of them was to use DirectX (a.k.a, D2D) to render webpage to achieve full-hardware acceleration development to support HTML5 standard features instead of GDI based rendering. As your HTML to PDF conversion depends on IE’s GDI based rendering, during conversion your HTML Converter will not be able to generate PDF documents that contain selectable text.  Hence, if the machine has IE9 or later installed, then you should consider using the Gecko based rendering. This approach reliably generates PDF documents that are text selectable and printer friendly.

#### Prerequisites

Prerequisites

<table>
<tr>
<th>
Dlls</th><th>
<br>* Syncfusion.Core.dll
<br>* Syncfusion.Compression.Base.dll
<br>* Syncfusion.Pdf.Base.dll
<br>* Syncfusion.HtmlConverter.Base.dll
<br>* Syncfusion.GeckoHtmlRenderer.dll
<br>* Syncfusion.GeckoWrapper.dll</th></tr>
<tr>
<td>
<br>Software Development Kit (SDK)</td><td>
* XulRunner-SDK 2.0</td></tr>
</table>

#### Installation Steps


To facilitate conversion, HTML Converter depends on Active-X Wrapper control that interacts with the GECKO APIs during conversion.  When installing the Essential Studio, the assembly manager registers the Syncfusion.GeckoWrapper.dll in the machine. GeckoWrapper.dll is built in debug mode .Being debug assemblies, these cannot be shipped by the xcopy method of deployment. Therefore, you are required to install:

1. VC++ 2010 express edition that is necessary to install the required debug assemblies (msvcr100d.dll). 
2. VC++ 2008 (SP1) express edition necessary to install the ATL90.dll.



To register the Active-X wrapper control manually:

1. Move the syncfusion.GeckoWrapper.dll to the bin folder of Gecko SDK (shipped with install–{Installed Drive}:\Program Files\Syncfusion\Essential Studio\{version number}\XulRunner-2.0.sdk\bin\) to the server.
2. Register the Syncfusion.GeckoWrapper.dll by using the following command in command   prompt: regsvr32 Syncfusion.GeckoWrapper.dll

Currently, Gecko SDK can be built only for x86 configurations. From the beginning, Syncfusion has provided GeckoHtmlRenderer.Base.dll compatible only for x86 configuration. You can check the following link for details: [https://developer.mozilla.org/en/Creating_XPCOM_Components/Setting_up_the_Gecko_SDK](https://developer.mozilla.org/en/Creating_XPCOM_Components/Setting_up_the_Gecko_SDK)

The limitations with this approach are as follows:

1. Formatting/styles created by using dynamic scripts are not rendered in the resultant PDF.
2. Other features in HTML to PDF conversion such as hyperlinks are not available for conversion by using Gecko rendering engine. However, the page breaks are supported, but the page break cannot be explicitly controlled.

#### Conversion of HTML to PDF using Gecko Rendering Engine


The following code sample explains you the conversion of HTML to PDF using the Gecko Rendering Engine.

{% highlight c# %}

//Creates PDF Generator.

PdfDocument doc = new PdfDocument();

//Adds pages.

PdfPage page = doc.Pages.Add();

//Initializes Gecko.

using (GeckoHtmlRendererControl renderer = new GeckoHtmlRendererControl())

{

using (HtmlConverter converter = new HtmlConverter(renderer))

{

 using (HtmlToPdfResult result = converter.Convert("www.google.com", ImageType.Metafile, (int)page.Size.Width, (int)page.Size.Height, AspectRatio.KeepWidth))

{

//Renders HTML in PDF.

result.Render(doc);

}

}

}

//Saves PDF document.

doc.Save("HtmlToPdf.pdf");

{% endhighlight %}



{% highlight vbnet %}

'Creates PDF Generator.

Dim doc As New PdfDocument()

'Adds pages.

Dim page As PdfPage = doc.Pages.Add()

'Initializes Gecko.

Using renderer As New GeckoHtmlRendererControl()

Using converter As New HtmlConverter(renderer)

Using result As HtmlToPdfResult = converter.Convert("www.google.com", ImageType.Metafile, CInt(page.Size.Width), CInt(page.Size.Height), AspectRatio.KeepWidth)

'Renders HTML in PDF.

result.Render(doc)

End Using

End Using

End Using

'Saves PDF document.

doc.Save("HtmlToPdf.pdf")

{% endhighlight %}



## Word to PDF

Essential DocIO enables to export the Word document into a PDF document. By using the ConvertToPDF method of the DocToPDFConverter class, you can convert the Word document to PDF and save the PDF document.

N> You need to have Essential PDF and Essential DocIO installed in your system. This is because "Syncfusion.DocToPDFConverter.Base.dll" is conditionally shipped when both DocIO.Base and Pdf.Base is installed.

This section covers the following:

* Assemblies Dependent on this Conversion
* Supported Elements and Limitations
* Unsupported Elements and Limitation

Assembly Dependency for this Conversion

* Syncfusion.DocToPDFConverter.Base.dll
* Syncfusion.DocIO.Base.dll
* Syncfusion.Pdf.Base.dll
* Syncfusion.Core.dll
* Syncfusion.Compression.Base.dll

The following code illustrates you on how to convert a Word document, say, "sample.doc" to a PDF document.



{% highlight c# %}

//Loads the Word document.

WordDocument wordDoc = new WordDocument("sample.doc");

//Declares the DocToPDFConverter.

DocToPDFConverter converter = new DocToPDFConverter();

//Converts Word document into PDF document.

PdfDocument pdfDoc = converter.ConvertToPDF(wordDoc);

//Saves the PDF file.

pdfDoc.Save("DoctoPDF.pdf");

{% endhighlight %}



{% highlight vbnet %}

'Loads the Word document.

Dim wordDoc As New WordDocument("sample.doc")

'Declares the DocToPDFConverter.

Dim converter As New DocToPDFConverter()

'Converts word document into PDF document.

Dim pdfDoc As PdfDocument = converter.ConvertToPDF(wordDoc)

'Saves the PDF file.

pdfDoc.Save("DoctoPDF.pdf")

{% endhighlight %}


### Supported Elements

This feature provides support for the following elements.

* Paragraph and Character Formatting
* MultiColumn Text
* Headers and Footers
* Bulleted, Numbered, and MultiLevel Lists
* Images
* Tables (both simple and nested)
* Breaks (page, section, linebreak, etc.)
* OLEObject
* Text Box
* Page Settings and Background Image
* Document Properties


#### Paragraph and Character Formatting 


This feature supports almost all the paragraph formatting options except Full-Justification. The supported paragraph formatting options are as follows.

* Paragraph and Character Fonts
* Font styles (Bold, Italic, Underline and Strike through)
* Subscript and Superscript
* Paragraph and Text Highlighting
* Indents, tabs and spaces
* Line Spacing
* Left, Right and Center Justification 

Known Limitations

* Borders around paragraphs.
* Full Justification.
* MultiColumn Text

#### MultiColumn Text


Word document containing multicolumn text is supported. 

Known Limitations - The output can look different in case of full-justification formatting is applied onto the columns. 

#### Headers and Footers

Page headers and footers are supported and can contain images, text, and page number fields.

#### Bulleted, Numbered, and MultiLevel Lists

Bulleted, numbered, and multilevel lists are supported with proper indentation and alignments as represented in the Word document.

Known Limitations - In some case, the image bullets preserved in the document may be replaced by the disc style bullet.

#### Images

The images present in the document are supported along with their corresponding positions and sizes.

Known Limitations - However, the images placed inside a shape cannot be preserved in the generated PDF document.

#### Tables

Both simple and nested tables are supported with proper preservation of text formatting and images present inside the table cell.

Known Limitations

* Tables making use of patterns and 3D borders cannot be retained in the output document.
* Absolutely positioned tables are not supported.

#### Breaks


Columns, section, line and page breaks are fully supported.

#### OLEObject

OLEObjects are partially supported, that is the image that represents a particular document that is available in the generated PDF document. But the object associated with the object cannot be converted into the generated document.

#### Text Box

The text value present in the text box can be rendered as text in its actual position in the generated PDF document.

#### Page Settings

The actual page settings can be preserved in the generated PDF document that includes page size, orientation, page borders and its background image, if available.

#### Document Properties

The document properties present in the Word document can also be preserved in the generated PDF Document.

### Unsupported Elements

The following are the list of unsupported elements that cannot be preserved in the generated PDF document.

* Shapes and AutoShapes
* Comments
* Hyperlinks
* Bookmarks
* Footnotes and Endnotes
* Dynamic Fields
* Charts
* Table of Contents

Known Limitations - Pagination 

#### Pagination

Essential DocIO, when generating the PDF document, makes sensible decisions while laying out the text and its supported elements. However, pagination is not guaranteed with all the documents.

## Tiff to PDF

TIFF image can be converted into PDF document and it can be done by accessing each frame of the multiframe TIFF image and rendering it in each page of the PDF document.

The code sample to illustrate the same is as follows.



{% highlight c# %}

//Creates a PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a section to PDF document.

PdfSection section = pdfDocument.Sections.Add();

//Declares the PDF page.

PdfPage page;

//Declares PDF graphics.

PdfGraphics g;

//Loads Multiframe Tiff image.

PdfBitmap tiffImage = new PdfBitmap("image.tiff");

int frameCount = tiffImage.FrameCount;

for (int i = 0; i < frameCount; i++)

{

page = section.Pages.Add();

section.PageSettings.Margins.All = 0;

g = page.Graphics;

tiffImage.ActiveFrame = i;

g.DrawImage(tiffImage, 0, 0, page.GetClientSize().Width, page.GetClientSize().Height);

}

pdfDocument.Save("Sample.pdf");

pdfDocument.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a section to the PDF document.

Dim section As PdfSection = pdfDocument.Sections.Add()

'Declares the PDF page.

Dim page As PdfPage

'Declares PDF graphics.

Dim g As PdfGraphics

'Loads Multiframe Tiff image.

Dim tiffImage As New PdfBitmap("image.tiff")

Dim frameCount As Integer = tiffImage.FrameCount

For i As Integer = 0 To frameCount - 1

page = section.Pages.Add()

section.PageSettings.Margins.All = 0

g = page.Graphics

tiffImage.ActiveFrame = i

g.DrawImage(tiffImage, 0, 0, page.GetClientSize().Width, page.GetClientSize().Height)

Next

pdfDocument.Save("Sample.pdf")

pdfDocument.Close(True)

{% endhighlight %}


## RTF to PDF

Essential PDF supports conversion of RTF document into PDF document. This is achieved in two ways, they are using,

1. Bitmap
2. Metafile

The following code sample illustrates the conversion of RTF to PDF using Bitmap.

{% highlight c# %}



//Creates a PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Declares PDF page.

PdfPage page = pdfDocument.Pages.Add();

//Reads the RTF document.

StreamReader reader = new StreamReader(@"Essential PDF.rtf", Encoding.ASCII);

string text = reader.ReadToEnd();

reader.Close();

//Creates bitmap from RTF string.

PdfImage bitmap = PdfImage.FromRtf(text, page.GetClientSize().Width, PdfImageType.Bitmap);

PdfLayoutFormat format = new PdfLayoutFormat();

format.Break = PdfLayoutBreakType.FitPage;

format.Layout = PdfLayoutType.Paginate;

bitmap.Draw(page, 0, 0, format);

pdfDocument.Save("Sample.pdf");

pdfDocument.Close(true);
{% endhighlight %}


{% highlight vbnet %}



'Creates a PDF document.

Dim pdfDocument As New PdfDocument()

'Declares PDF page.

Dim page As PdfPage = pdfDocument.Pages.Add()

'Reads the RTF document.

Dim reader As New StreamReader("Essential PDF.rtf", Encoding.ASCII)

Dim text As String = reader.ReadToEnd()

reader.Close()

'Creates bitmap from the RTF string.

Dim bitmap As PdfImage = PdfImage.FromRtf(text, page.GetClientSize().Width, PdfImageType.Bitmap)

Dim format As New PdfLayoutFormat()

format.Break = PdfLayoutBreakType.FitPage

format.Layout = PdfLayoutType.Paginate

bitmap.Draw(page, 0, 0, format)

pdfDocument.Save("Sample.pdf")

pdfDocument.Close(True)

{% endhighlight %}

The following code sample illustrates the conversion of RTF to PDF using Metafile.

{% highlight c# %}



//Creates a PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Declares PDF page.

PdfPage page = pdfDocument.Pages.Add();

//Reads RTF document.

StreamReader reader = new StreamReader(@"Essential PDF.rtf", Encoding.ASCII);

string text = reader.ReadToEnd();

reader.Close();

//Converts it as metafile.

PdfMetafile metafile = (PdfMetafile)PdfImage.FromRtf(text, page.GetClientSize().Width, PdfImageType.Metafile);

PdfMetafileLayoutFormat format = new PdfMetafileLayoutFormat();

//Allows the text to flow multiple pages without any breaks.

format.SplitTextLines = true;

//Draws the image.

metafile.Draw(page, 0, 0, format);

pdfDocument.Save("Sample.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a PDF document.

Dim pdfDocument As New PdfDocument()

'Declares the PDF page.

Dim page As PdfPage = pdfDocument.Pages.Add()

'Reads the RTF document.

Dim reader As New StreamReader("Essential PDF.rtf", Encoding.ASCII)

Dim text As String = reader.ReadToEnd()

reader.Close()

'Converts it as metafile.

Dim metafile As PdfMetafile = DirectCast(PdfImage.FromRtf(text, page.GetClientSize().Width, PdfImageType.Metafile), PdfMetafile)

Dim format As New PdfMetafileLayoutFormat()

'Allows the text to flow multiple pages without any breaks.

format.SplitTextLines = True

'Draws the image.

metafile.Draw(page, 0, 0, format)

pdfDocument.Save("Sample.pdf")

pdfDocument.Close(True)
{% endhighlight %}

## XPS to PDF

An XPS (XML Paper Specification) document standardized by Ecma International can be converted to PDF.

The XPS document format consists of XML structured markup that defines the layout of a document and the visual appearance of each page, along with rendering rules for distributing, archiving, rendering, processing, and printing the documents. Similar to PDF, XPS is also a fixed-layout document format that helps to preserve document fidelity and to achieve device-independent document appearance.

XPS documents can be converted to PDF using the Convert method of the XPSToPdfConverter class.

N> You need to add the Syncfusion.XPS namespace to work with the XPSToPdfConverter class.

An XPS document can be converted into PDF using the following code sample.

{% highlight c# %}



//Creates converter class.

XPSToPdfConverter converter = new XPSToPdfConverter();

//Converts the XPS to PDF.

PdfDocument document = converter.Convert("Sample.xps");

//Saves and closes the document.

document.Save("Sample.pdf");

document.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates converter class.

Dim converter As New XPSToPdfConverter()

'Converts the XPS to PDF.

Dim document As PdfDocument = converter.Convert("Sample.xps")

'Saves and closes the document.

document.Save("Sample.pdf")

document.Close(True)

{% endhighlight %}

#### Supported Elements

List of Supported Elements

<table>
<tr>
<th>
Element</th><th>
Convert to PDF</th></tr>
<tr>
<td>
ArcSegment</td><td>
Yes</td></tr>
<tr>
<td>
Canvas</td><td>
Yes</td></tr>
<tr>
<td>
DocumentOutline</td><td>
No</td></tr>
<tr>
<td>
DocumentReference</td><td>
No</td></tr>
<tr>
<td>
FigureStructure</td><td>
No</td></tr>
<tr>
<td>
FixedPageResources</td><td>
Yes</td></tr>
<tr>
<td>
Glyphs</td><td>
Yes</td></tr>
<tr>
<td>
Gradient</td><td>
Yes</td></tr>
<tr>
<td>
ImageBrush</td><td>
Yes</td></tr>
<tr>
<td>
Intent</td><td>
Yes</td></tr>
<tr>
<td>
LinkTarget</td><td>
Yes</td></tr>
<tr>
<td>
ListItemStructure</td><td>
Yes</td></tr>
<tr>
<td>
ListStructure</td><td>
Yes</td></tr>
<tr>
<td>
MatrixTransform</td><td>
Yes</td></tr>
<tr>
<td>
NamedElement</td><td>
No</td></tr>
<tr>
<td>
OutlineEntry</td><td>
No</td></tr>
<tr>
<td>
PageContent</td><td>
Yes</td></tr>
<tr>
<td>
PageContentLinkTargets</td><td>
No</td></tr>
<tr>
<td>
ParagraphStructure</td><td>
No</td></tr>
<tr>
<td>
Path</td><td>
Yes</td></tr>
<tr>
<td>
PolyBezierSegment</td><td>
Yes</td></tr>
<tr>
<td>
PolyLineSegment</td><td>
Yes</td></tr>
<tr>
<td>
PolyQuadraticBezierSegment</td><td>
Yes</td></tr>
<tr>
<td>
ResourceDictionary</td><td>
Yes</td></tr>
<tr>
<td>
SectionStructure</td><td>
No</td></tr>
<tr>
<td>
SignBy</td><td>
No</td></tr>
<tr>
<td>
SignatureDefinition</td><td>
No</td></tr>
<tr>
<td>
SignatureDefinitions</td><td>
No</td></tr>
<tr>
<td>
SigningLocation</td><td>
No</td></tr>
<tr>
<td>
SolidColorBrush</td><td>
Yes</td></tr>
<tr>
<td>
SpotLocation</td><td>
No</td></tr>
<tr>
<td>
Story</td><td>
No</td></tr>
<tr>
<td>
TableStructure</td><td>
No</td></tr>
<tr>
<td>
VisualBrush</td><td>
No</td></tr>
</table>

## Tagged PDF

HTML to PDF conversion handled using MSHTML rendering library can now generate tagged PDF documents.

Tagged PDF is a stylized use of PDF that builds on the logical structure framework. It defines a set of standard structure types and attributes that allow page content (text, graphics, and images) to be extracted and reused. The contents are accessible to users with visual impairments.

HTML documents can be converted to tagged PDFs using the ConvertToTaggedPDF method. It returns PdfLayoutResult that provides the end rectangle bounds and PDF page after the conversion.

A tagged PDF can be converted from a Web page or HTML string by using the following code sample.


{% highlight c# %}

//Creates a new PdfDocument.

PdfDocument document = new PdfDocument();

PdfLayoutResult result = null;

//Creates a new instance of HtmlConverter class.

{

//Turns on or off various options.

html.EnableJavaScript = true;

//Converts to Tagged PDF.

}

//Saves and closes the document.

document.Save("Sample.pdf");

document.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PdfDocument.

Dim document As New PdfDocument()

Dim result As PdfLayoutResult = Nothing

'Creates a new instance of HtmlConverter class.

Using html As New HtmlConverter()

'Turns on or off various options.

html.EnableJavaScript = True

html.EnableActiveXContents = True

'Converts to Tagged PDF.

End Using

'Saves and closes the document.

document.Save("Sample.pdf")

document.Close(True)

{% endhighlight %}

N> The HTML to PDF conversion that creates a metafile during the evolution, would interpret the content as either text or an image. The outcome of this PDF would contain only paragraph and figure tags; hyperlinks are not supported.

## Text Extraction

PDF file represents an ordered sequence of fixed pages. The planned appearance of everything that each page contains is completely specified down to the smallest detail. All the graphics, images, and text are specified to appear at precise spots on the page in a particular color of a given and fixed size, and so on.

Essential PDF provides support to extract text from an existing PDF document. By using the ExtractText method, you can extract the text, page by page.

The following code example illustrates this.

{% highlight c# %}



//Loads an existing PDF.

PdfLoadedDocument ldoc = new PdfLoadedDocument("Sample.pdf");

//Loads first page.

PdfPageBase page = ldoc.Pages[0];

//Extracts text from first page.

string s = page.ExtractText();

{% endhighlight %}

{% highlight vbnet %}



'Loads an existing PDF.

Dim ldoc As New PdfLoadedDocument("Sample.pdf")

'Loads first page.

Dim page As PdfPageBase = ldoc.Pages(0)

'Extracts text from first page.

Dim s As String = page.ExtractText()
 {% endhighlight %}

N> The text is extracted in the order in which it is written in the document stream and not in the order in which it is viewed in the PDF viewer.

## Image Extraction

Essential PDF provides support to extract images from an existing PDF document. You can extract images by using the ExtractImages method in the PdfLoadedPage class.

The following code example illustrates how to extract images from a PDF document.

{% highlight c# %}



//Loads an existing PDF.

PdfLoadedDocument ldoc = new PdfLoadedDocument("Sample.pdf");

//Loads first page.

PdfPageBase page = ldoc.Pages[0];

Extracts images from first page.

Image[] img = page.ExtractImages();

{% endhighlight %}

{% highlight vbnet %}



'Loads an existing PDF.

Dim ldoc As New PdfLoadedDocument("Sample.pdf")

'Loads first page.

Dim page As PdfPageBase = ldoc.Pages(0)

'Extracts images from first page.

Dim img As Image() = page.ExtractImages()


{% endhighlight %}
