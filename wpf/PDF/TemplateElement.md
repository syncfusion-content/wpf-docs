---
layout: post
title: TemplateElement
description: templateelement
platform: wpf
control: PDF
documentation: ug
---

# TemplateElement

Page Templates define graphic primitives for a range of pages. Each page has two sources of template, such as template on the document holding the section of the page and template on the section containing the page that apply sequentially.

Each page template has four properties for Left, Right, Top, and Bottom docked templates, and a collection of additional template elements (stamps). There are eight additional templates that you can add to the odd or even pages (EvenTop, OddTop, etc.). If one of these eight templates is set, it overrides its usual template (OddTop overrides top, etc.); otherwise, the usual template is used. 

> Note: A PdfPageTemplateElement is added as one template. It can be assigned to Left, Right, Top, or Bottom only once.

Using the Page Templates 

When you want to define some graphics content to all pages of the document, use the Template property of the PdfDocument class. You can define Left, Top, Right, and Bottom templates, as well as an arbitrary quantity of the other templates (stamps) that can be used for water marking or stamping of the pages.

When you decide to use some custom templates for a specified range of the page, use Template property of the PdfSection class containing these pages. It involves the same functionality as in the PdfDocument class. Additionally, you can disable or enable the document templates from the section.

Default Behavior

Document templates are enabled, by default.

> Note: Section template that is printed over the parent template, does not replace document templates. When you want to insert a watermark or stamp on the page, use Stamps property of the PdfDocumentTemplate class.

Behavior

PdfPageTemplateElement class has the functionality of aligning (use Alignment property) and docking (use Dock property) of this class. Docking to the Left, Top, Right, and Bottom are implemented similar to Windows Forms Docking functionality (Top and Bottom have priority). Docking stamp elements do not have any priorities and the appearance depends on their order in the collection. 

> Note: Alignment has higher priority than Docking in the template element, but Docking resets the Alignment.

Each template element that is docked, sticks to its appropriate side of the page. It stretches itself according to the dimensions of the page and resets the alignment. Avoid printing any content that can be stretched in cases where the pages have different sizes. Also, define the size of the template elements according to its docking style on the page. When you want to use some template element as Left, Top, Right, or Bottom, but do not want the element to be stretched, then you can set the Alignment property once you are assigned with the template element (or set Dock property) to any of the mentioned properties. In this case, the template sticks to the appropriate position, but not be stretched.

> Note: In this scenario, you can set the Alignment property to the appropriate side only (depending on the Dock style). For example, when you want to set some template element as Top, the allowed values for Alignment are: TopLeft, TopCenter, and TopRight. You cannot set any other value attributing to the possible inconsistency with docking style.

Z-Order of the Layers

Each page can contain page templates from the document and from the parent section. Also, it can contain its own layers. The order of the layers is as follows (from back to top): 

1. Document page templates (Left, Top, Right, Bottom) that have Background property set to True.
2. Document stamp elements that have Background property set to True.
3. Section page templates (Left, Top, Right, Bottom) that have Background property set to True.
4. Section stamp elements that have Background property set to True.
5. Page layers.
6. Section page templates (Left, Top, Right, Bottom) that have Foreground property set to True.
7. Section stamp elements that have Foreground property set to True.
8. Document page templates (Left, Top, Right, Bottom) that have Foreground property set to True.

9.    Document stamp elements that have Foreground property set to True.


![C:/Users/SURESH/Desktop/UGRevamp/TemplateElement.png](TemplateElement_images/TemplateElement_img1.png)



The code sample to use PdfTemplate to render it into the PDF document is illustrated as follows.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument pdfDocument = new PdfDocument();

//Adds a page to the PDF document.

PdfPage pdfPage = pdfDocument.Pages.Add();

//Create a PDF Template.

PdfTemplate template = new PdfTemplate(100, 50);

//Draws a rectangle into the graphics of the template.

template.Graphics.DrawRectangle(PdfBrushes.BurlyWood, new System.Drawing.RectangleF(0, 0, 100, 50));

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 14);

PdfBrush brush = new PdfSolidBrush(Color.Black);

//Draws a string into the graphics of the template.

template.Graphics.DrawString("Hello World", font, brush, 5, 5);

//Draws the template into the page graphics of the document.

pdfPage.Graphics.DrawPdfTemplate(template, PointF.Empty);

//Saves the document.

pdfDocument.Save("Output.pdf");

pdfDocument.Close(true);

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim pdfDocument As New PdfDocument()

'Adds a page to the PDF document

Dim pdfPage As PdfPage = pdfDocument.Pages.Add()

'Creates a PDF Template.

Dim template As New PdfTemplate(100, 50)

'Draws a rectangle into the graphics of the template.

template.Graphics.DrawRectangle(PdfBrushes.BurlyWood, New System.Drawing.RectangleF(0, 0, 100, 50))

Dim font As PdfFont = New PdfStandardFont(PdfFontFamily.Helvetica, 14)

Dim brush As PdfBrush = New PdfSolidBrush(Color.Black)

'Draws a string into the graphics of the template.

template.Graphics.DrawString("Hello World", font, brush, 5, 5)

'Draws the template into the page graphics of the document.

pdfPage.Graphics.DrawPdfTemplate(template, PointF.Empty)

'Saves the document.

pdfDocument.Save("Output.pdf")

pdfDocument.Close(True)
{% endhighlight %}

## Shapes

Essential PDF has a comprehensive set of API that can be used for drawing a variety of shapes such as: 

* Rectangles 
* Circles 
* Arcs 
* Curves and so on. 

Shapes are filled by using different types of brushes like gradient brush, Tiling brush, and so on. Essential PDF supports drawing of shapes with different color spaces. Transparency of shapes can also be set.

PdfGraphics class allows drawing a wide range of primitives like 

* Lines 
* Curves 
* Paths 
* Text 



For each such operation, there is a set of methods like Draw<primitive>() (for example: DrawLine). 

Each set of methods accepts parameters specific to each primitive type (for example: pen, brush, boundaries, etc.). 

* If pen is used, the primitive are drawn 
* If brush is used, the primitive are filled. 



> Note: You must add the Syncfusion.Pdf.Graphics namespace to work with graphic objects.

The following code example illustrates how to draw shapes.

{% highlight c# %}

//Creates a document.

PdfDocument doc = new PdfDocument();

//Adds a new page.

PdfPage page = doc.Pages.Add();

//Adds pen.

PdfPen pen = new PdfPen(PdfBrushes.Brown, 10f);

//Adds points.

PointF p1 = new PointF(10, 100);

PointF p2 = new PointF(10, 200);

PointF p3 = new PointF(100, 100);

PointF p4 = new PointF(100, 200);

PointF p5 = new PointF(55, 150);

PointF[] points = { p1, p2, p3, p4, p5};

// Draws Polygon.

page.Graphics.DrawPolygon(pen, PdfBrushes.Green, points);

//Saves the PDF.

doc.Save("Shapes.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a document.

Dim doc As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = doc.Pages.Add()

'Adds pen.

Dim pen As New PdfPen(PdfBrushes.Brown, 10.0F)

'Adds points.

Dim p1 As New PointF(10, 100)

Dim p2 As New PointF(10, 200)

Dim p3 As New PointF(100, 100)

Dim p4 As New PointF(100, 200)

Dim p5 As New PointF(55, 150)

Dim points As PointF() = {p1, p2, p3, p4, p5}

'Draws Polygon.

page.Graphics.DrawPolygon(pen, PdfBrushes.Green, points)

'Saves the PDF.

doc.Save("Shapes.pdf")
{% endhighlight %}


You can paginate the element as follows.

{% highlight c# %}



//Creates a document.

PdfDocument doc = new PdfDocument();

//Adds a new page.

PdfPage page = doc.Pages.Add();

//Sets bounds for ellipse.

RectangleF rect = new RectangleF(0, 0, 100, 1000);

//Creates ellipse.

PdfEllipse ellipse = new PdfEllipse(rect); 

//Sets layout property to make the element break across the pages. 

PdfLayoutFormat format = new PdfLayoutFormat(); 

format.Break = PdfLayoutBreakType.FitPage; 

format.Layout = PdfLayoutType.Paginate; 

ellipse.Brush = PdfBrushes.Brown; 

//Draws ellipse. 

ellipse.Draw(page, 20, 20, format);

//Saves the PDF.

doc.Save("Shapes.pdf");

{% endhighlight %}



{% highlight vbnet %}



'Creates a Document.

Dim doc As New PdfDocument()

'Adds a new page.

Dim page As PdfPage = doc.Pages.Add()

'Sets bounds for ellipse.

Dim rect As New RectangleF(0, 0, 100, 1000)

'Creates ellipse.

Dim ellipse As New PdfEllipse(rect)

'Sets layout property to make the element break across the pages. 

Dim format As New PdfLayoutFormat()

format.Break = PdfLayoutBreakType.FitPage

format.Layout = PdfLayoutType.Paginate

ellipse.Brush = PdfBrushes.Brown

'Draws ellipse. 

ellipse.Draw(page, 20, 20, format)

'Saves the PDF.

doc.Save("Shapes.pdf")

{% endhighlight %}

