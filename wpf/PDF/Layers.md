---
layout: post
title: Layers
description: layers
platform: wpf
control: PDF
documentation: ug
---

# Layers

Layers are collection of graphics and when the viewer application is used, you can make the layers visible or invisible dynamically. The graphics belonging to such a group can reside anywhere in the document.

## Creating PDF Layer in PDF document

PdfPageLayer is used to create unlimited levels of layers and sub-layers in a parent-child relationship in the PdfDocument. The layers are stored by the PdfPageLayerCollection of a particular PdfPage. This collection contains layers for that particular page only, and every page has its own PdfPageLayerCollection. In order to add a layer to a particular page, you need to add it to the PdfPageLayerCollection of that page using Add method.

{% highlight c# %}



//Creates PDF document.

PdfDocument document = new PdfDocument();

PdfPage page = document.Pages.Add();

//Adds the first layer.

PdfPageLayer layer = page.Layers.Add("Layer1");

PdfGraphics graphics = layer.Graphics;

graphics.TranslateTransform(100, 60);

//Draws Arc.

PdfPen pen = new PdfPen(System.Drawing.Color.Red, 50);

RectangleF rect = new RectangleF(0, 0, 50, 50);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Blue, 30);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

pen = new PdfPen(System.Drawing.Color.Yellow, 20);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Green, 10);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

//Adds another layer on the page.

PdfPageLayer layer2 = page.Layers.Add("Layer2");

graphics = layer2.Graphics;

graphics.TranslateTransform(100, 180);

graphics.SkewTransform(0, 50);

//Draws another set of elements.

pen = new PdfPen(System.Drawing.Color.Red, 50);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Blue, 30);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

pen = new PdfPen(System.Drawing.Color.Yellow, 20);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Green, 10);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

//Adds another layer.

PdfPageLayer layer3 = page.Layers.Add("Layer3");

graphics = layer3.Graphics;

graphics.TranslateTransform(160, 120);

//Draws another set of elements.

pen = new PdfPen(System.Drawing.Color.Red, 50);

graphics.DrawArc(pen, rect, -60, 60);

pen = new PdfPen(System.Drawing.Color.Blue, 30);

graphics.DrawArc(pen, 0, 0, 50, 50, -60, 60);

pen = new PdfPen(System.Drawing.Color.Yellow, 20);

graphics.DrawArc(pen, rect, -60, 60);

pen = new PdfPen(System.Drawing.Color.Green, 10);

graphics.DrawArc(pen, 0, 0, 50, 50, -60, 60);

//Saves to disk.

document.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates PDF document.

Dim document As New PdfDocument()

Dim page As PdfPage = document.Pages.Add()

'Adds the first layer.

Dim layer As PdfPageLayer = page.Layers.Add("Layer1")

Dim graphics As PdfGraphics = layer.Graphics

graphics.TranslateTransform(100, 60)

'Draws Arc.

Dim pen As New PdfPen(System.Drawing.Color.Red, 50)

Dim rect As New RectangleF(0, 0, 50, 50)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Blue, 30)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

pen = New PdfPen(System.Drawing.Color.Yellow, 20)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Green, 10)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

'Adds another layer on the page.

Dim layer2 As PdfPageLayer = page.Layers.Add("Layer2")

graphics = layer2.Graphics

graphics.TranslateTransform(100, 180)

graphics.SkewTransform(0, 50)

'Draws another set of elements.

pen = New PdfPen(System.Drawing.Color.Red, 50)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Blue, 30)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

pen = New PdfPen(System.Drawing.Color.Yellow, 20)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Green, 10)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

'Adds another layer.

Dim layer3 As PdfPageLayer = page.Layers.Add("Layer3")

graphics = layer3.Graphics

graphics.TranslateTransform(160, 120)

'Draws another set of elements.

pen = New PdfPen(System.Drawing.Color.Red, 50)

graphics.DrawArc(pen, rect, -60, 60)

pen = New PdfPen(System.Drawing.Color.Blue, 30)

graphics.DrawArc(pen, 0, 0, 50, 50, -60, 60)

pen = New PdfPen(System.Drawing.Color.Yellow, 20)

graphics.DrawArc(pen, rect, -60, 60)

pen = New PdfPen(System.Drawing.Color.Green, 10)

graphics.DrawArc(pen, 0, 0, 50, 50, -60, 60)

'Saves to disk.

document.Save("Sample.pdf")
{% endhighlight %}

## Modifying PDF Layer in the Loaded PDF document

You can remove the layers from an exsisting document by loading the layer from the PdfLoadedPage.

PdfLoadedPage contain its own PdfPageLayerCollection. You can remove the layer by its name using Remove method.

{% highlight c# %}



//Loads the document.

PdfLoadedDocument document = new PdfLoadedDocument("Sample.pdf");

PdfLoadedPage page = document.Pages[0] as PdfLoadedPage;

//Loads layer collection.

PdfPageLayerCollection coll = page.Layers;

//Removes layers from PDF.

coll.Remove("Layer 1");

//Saves to disk.

document.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Load the document

Dim document As New PdfLoadedDocument("Sample.pdf")

Dim page As PdfLoadedPage = TryCast(document.Pages(0), PdfLoadedPage)



'Loading layer collection

Dim coll As PdfPageLayerCollection = page.Layers

'Removing layers from PDF

coll.Remove("Layer 1")

'Save to disk

document.Save("Sample.pdf")
{% endhighlight %}

## Toggle the visibility of the layer

You can toggle the visibility of the PdfLayer when printing the PDF document using the PdfPrintState class and it has following three options.

* Print when visible – Print the layer when it is visible on the page.
* Never print – This option never prints Layer on the page.
* Always pring – This option always prints the Layer on the page.



{% highlight c# %}



PdfDocument document = new PdfDocument();

PdfPage page=document.Pages.Add();

//Adds the first layer.

PdfPageLayer layer = page.Layers.Add("Layer1");

//Sets the print state to PDF.

layer.PrintState = PdfPrintState.NeverPrint;

PdfGraphics graphics = layer.Graphics;

graphics.TranslateTransform(100, 60);

//Draws Arc.

PdfPen pen = new PdfPen(System.Drawing.Color.Red, 50);

RectangleF rect = new RectangleF(0, 0, 50, 50);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Blue, 30);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

pen = new PdfPen(System.Drawing.Color.Yellow, 20);

graphics.DrawArc(pen, rect, 360, 360);

pen = new PdfPen(System.Drawing.Color.Green, 10);

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360);

//Saves to disk.

document.Save("Sample.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

Dim page As PdfPage = document.Pages.Add()

'Adds the first layer.

Dim layer As PdfPageLayer = page.Layers.Add("Layer1")

'Sets the print state to PDF.

layer.PrintState = PdfPrintState.NeverPrint

Dim graphics As PdfGraphics = layer.Graphics

graphics.TranslateTransform(100, 60)

'Draws Arc.

Dim pen As New PdfPen(System.Drawing.Color.Red, 50)

Dim rect As New RectangleF(0, 0, 50, 50)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Blue, 30)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

pen = New PdfPen(System.Drawing.Color.Yellow, 20)

graphics.DrawArc(pen, rect, 360, 360)

pen = New PdfPen(System.Drawing.Color.Green, 10)

graphics.DrawArc(pen, 0, 0, 50, 50, 360, 360)

'Saves to disk.

document.Save("Sample.pdf")

{% endhighlight %}

