---
layout: post
title: Annotation
description: annotation
platform: wpf
control: PDF
documentation: ug
---

# Annotation

An annotation associates an object such as a note, sound, or a movie with location on the page of a PDF document, or provides a way to interact with you by means of mouse and keyboard.

Essential PDF library provides support to add annotations to both existing and newly created PDF files.The following annotion types are supported.

List of Annotation types

<table>
<tr>
<th>
Annotation Type</th><th>
Uses</th></tr>
<tr>
<td>
Sound Annotation</td><td>
Embeds sound file into the PDF and plays the sound file.</td></tr>
<tr>
<td>
Attachment Annotation</td><td>
Embeds files into PDF files.</td></tr>
<tr>
<td>
URI Annotation</td><td>
Navigates to specified URI.</td></tr>
<tr>
<td>
File Link Annotation</td><td>
Opens file with specified path.</td></tr>
<tr>
<td>
Document Link Annotation</td><td>
Navigates to specified destination within the document.</td></tr>
<tr>
<td>
Popup Annotation</td><td>
Displays the text in a pop-up window for entry and editing.</td></tr>
<tr>
<td>
Line Annotation</td><td>
Displays a single straight line on the page.</td></tr>
<tr>
<td>
Rubber Stamp Annotation</td><td>
Displays text or graphics intended to look as if they were stamped on the page with a rubber stamp.</td></tr>
<tr>
<td>
Free text annotation</td><td>
Displays text directly on the page.</td></tr>
<tr>
<td>
Ink Annotation</td><td>
Represents a freehand “scribble” composed of one or more disjoint paths.</td></tr>
<tr>
<td>
3D Annotation</td><td>
3D artwork is represented in a PDF document.</td></tr>
</table>

## Adding Annotation to newly created document

The annotations are stored by the PdfAnnotationCollection of a particular PdfPage. This collection contains annotations for that individual page only; every page has its own PdfAnnotationCollection. In order to add an annotation in a particular page, you need to add it to the PdfAnnotationCollection of that page using Add method.

* Create a particular annotation that you want to add to the PDF.
* Add the annotation to the PdfPage'sPdfAnnotationCollection.



{% highlight C# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new popup annotation.

PdfPopupAnnotation popupAnnotation = new PdfPopupAnnotation(rectangle,"Test popup annotation");

popupAnnotation.Border.Width = 4;

popupAnnotation.Border.HorizontalRadius = 20;

popupAnnotation.Border.VerticalRadius = 30;

//Sets the PDF popup icon.

popupAnnotation.Icon = PdfPopupIcon.NewParagraph;

//Adds this annotation to a new page.

page.Annotations.Add(popupAnnotation);

//Saves the document to disk.

document.Save("PopupAnnotation.pdf");

document.Close();
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new popup annotation.

Dim popupAnnotation As New PdfPopupAnnotation(rectangle, "Test popup annotation")

popupAnnotation.Border.Width = 4

popupAnnotation.Border.HorizontalRadius = 20

popupAnnotation.Border.VerticalRadius = 30

'Sets the PDF popup icon.

popupAnnotation.Icon = PdfPopupIcon.NewParagraph

'Adds this annotation to a new page.

page.Annotations.Add(popupAnnotation)

'Saves the document to disk.

document.Save("PopupAnnotation.pdf")

document.Close()
{% endhighlight %}

## Adding and getting Annotation from existing Pdf document

Essential PDF provides you support to add annotations to an existing document and also to get annotations from an existing document.

All the annotations for a particular page can be found in the PdfLoadedAnnotationCollection of that PdfLoadedPage. In order to get a particular annotation, you need to specify the Index of the annotation. This returns an object of type PdfAnnotation and you need to cast it to a particular type of the annotation.

{% highlight c# %}



//Loads an existing document.

PdfLoadedDocument document = new PdfLoadedDocument("Annotations.pdf");

PdfLoadedPage page = document.Pages[0] as PdfLoadedPage;

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new URI Annotation.

PdfUriAnnotation uriAnnotation = new PdfUriAnnotation(rectangle, "http://www.google.com");

//Sets Text to URIAnnotation.

uriAnnotation.Text = "Uri Annotation";

//Adds this annotation to a new page.

page.Annotations.Add(uriAnnotation);

//Adds annotation to existing document.

page.Annotations.Add(uriAnnotation);

//Gets the annotation from loaded document.

PdfLoadedPopupAnnotation popupAnnotation = page.Annotations[0] as PdfLoadedPopupAnnotation;

//Sets the popup annotation border.

popupAnnotation.Border.Width = 4;

popupAnnotation.Border.HorizontalRadius = 20;

popupAnnotation.Border.VerticalRadius = 30;

//Sets the popup icon.

popupAnnotation.Icon = PdfPopupIcon.Key;

//Saves the document.

document.Save("Annotation.pdf");

document.Close();
{% endhighlight %}


{% highlight vbnet %}



'Loads an existing document.

Dim document As New PdfLoadedDocument("Annotations.pdf")

Dim page As PdfLoadedPage = TryCast(document.Pages(0), PdfLoadedPage)

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new URI Annotation.

Dim uriAnnotation As New PdfUriAnnotation(rectangle, "http://www.google.com")

'Sets Text to uriAnnotation.

uriAnnotation.Text = "Uri Annotation"

'Adds this annotation to a new page.

page.Annotations.Add(uriAnnotation)

'Adds annotation to existing document.

page.Annotations.Add(uriAnnotation)

'Gets the annotation from loaded document.

Dim popupAnnotation As PdfLoadedPopupAnnotation = TryCast(page.Annotations(0), PdfLoadedPopupAnnotation)

'Sets the popup annotation border.

popupAnnotation.Border.Width = 4

popupAnnotation.Border.HorizontalRadius = 20

popupAnnotation.Border.VerticalRadius = 30

'Sets the popup icon.

popupAnnotation.Icon = PdfPopupIcon.Key

'Saves the document.

document.Save("Annotation.pdf")

document.Close()
{% endhighlight %}

## 3D Annotation

3D Annotations are by means where the 3D artwork is represented in a PDF document. Essential PDF can embed 3D files (u3d) in PDF files. It provides a way to interact with you by using the mouse and keyboard.

3D annotation is handled by the Pdf3DAnnotation class.The following example illustrates you on how to embed a 3D file.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new pdf3d annotation.

Pdf3DAnnotation pdf3dAnnotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), @"3DAnnotation.U3D");

//Creates pdfFont, pdfFont style and brush.

Font font = new Font("Calibri", 11, FontStyle.Regular);

PdfFont pdfFont = new PdfTrueTypeFont(font, false);

PdfBrush brush = new PdfSolidBrush(Color.DarkBlue);

//Handles the activation of the 3D annotation.

Pdf3DActivation activation = new Pdf3DActivation();

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation;

activation.ShowToolbar = true;

pdf3dAnnotation.Activation = activation;

pdf3dAnnotation.Appearance.Normal.Graphics.DrawString("Click to activate", pdfFont, brush, new PointF(40, 40));

//Adds this annotation to a new page.

pdf3dAnnotation.Appearance.Normal.Draw(page, new PointF(pdf3dAnnotation.Location.X, pdf3dAnnotation.Location.Y));

//Adds annotation to page.

page.Annotations.Add(pdf3dAnnotation);

//Saves the document to disk.

document.Save("3DAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new pdf3d annotation.

Dim pdf3dAnnotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Creates pdfFont, pdfFont style and brush.

Dim font As New Font("Calibri", 11, FontStyle.Regular)

Dim pdfFont As PdfFont = New PdfTrueTypeFont(font, False)

Dim brush As PdfBrush = New PdfSolidBrush(Color.DarkBlue)

'Handles the activation of the 3D annotation.

Dim activation As New Pdf3DActivation()

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation

activation.ShowToolbar = True

pdf3dAnnotation.Activation = activation

pdf3dAnnotation.Appearance.Normal.Graphics.DrawString("Click to activate", pdfFont, brush, New PointF(40, 40))

'Adds this annotation to a new page.

pdf3dAnnotation.Appearance.Normal.Draw(page, New PointF(pdf3dAnnotation.Location.X, pdf3dAnnotation.Location.Y))

'Adds annotation to page.

page.Annotations.Add(pdf3dAnnotation)

'Saves the document to disk.

document.Save("3DAnnotation.pdf")
{% endhighlight %}

### 3D View

3D View specifies parameters to be applied to the virtual camera associated with 3D annotation. These parameters include orientation and position of the camera, details regarding the projection of camera coordinates onto the target coordinate system of the annotation, and a description of the background where the artwork is to be drawn.

Pdf3DView class used to handle 3D view.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new pdf3d annotation.

Pdf3DAnnotation pdf3dAnnotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

Pdf3DView defaultView = new Pdf3DView();

defaultView.ExternalName = "Near View";

defaultView.CameraToWorldMatrix = new float[] { -0.382684f, 0.92388f, -0.0000000766026f, 0.18024f, 0.0746579f, 0.980785f, 0.906127f, 0.37533f, -0.19509f, -100, -112.432f, 45.6829f };

defaultView.CenterOfOrbit = 500f;

pdf3dAnnotation.Views.Add(defaultView);

page.Annotations.Add(pdf3dAnnotation);

//Saves the document to disk.

document.Save("3DViews.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new pdf3d annotation.

Dim pdf3dAnnotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

Dim defaultView As New Pdf3DView()

defaultView.ExternalName = "Near View"

defaultView.CameraToWorldMatrix = New Single() {-0.382684F, 0.92388F, -0.0000000766026F, 0.18024F, 0.0746579F, 0.980785F, 0.906127F, 0.37533F, -0.19509F, -100, -112.432F, 45.6829F}

defaultView.CenterOfOrbit = 500.0F

pdf3dAnnotation.Views.Add(defaultView)

page.Annotations.Add(pdf3dAnnotation)

'Saves the document to disk.

document.Save("3DViews.pdf")
{% endhighlight %}

### 3D Projection

3D Projection defines the mapping of 3D camera coordinates onto the target coordinate system of the annotation. Using this class, you can specify the type of Projection that determines how objects are projected onto the near plane and scaled. The possible values are Orthographic projection and Perspective projection.

Pdf3DProjection class handles the 3D projection that supports both near and far clipping. This type of clipping defines a near plane and far plane. Objects or parts of objects that are beyond the far plane or closer to the camera than the near plane are not drawn.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3DAnnotation.

Pdf3DAnnotation annotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), @"3DAnnotation.U3D");

//Handles the activation of the 3D annotation.

Pdf3DActivation activation = new Pdf3DActivation();

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation;

activation.ShowToolbar = true;

annotation.Activation = activation;

//Creates a new Pdf3DProjection.

Pdf3DProjection projection = new Pdf3DProjection();

projection.ProjectionType = Pdf3DProjectionType.Perspective;

projection.FieldOfView = 10;

projection.ClipStyle = Pdf3DProjectionClipStyle.ExplicitNearFar;

projection.NearClipDistance = 10;

//Creates a new Pdf3DView.

Pdf3DView view = new Pdf3DView();

view.Projection = projection;

view.CameraToWorldMatrix = new float[] { -1, 0, 0 ,0,1,0, 0, 0, -1, 0, 0, 1};

view.ExternalName = "Near View";

annotation.Views.Add(view);

//Adds the annotation in a new page.

page.Annotations.Add(annotation);

//Saves the document to disk.

document.Save("Pdf3DProjection.pdf")
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new Pdf3DAnnotation.

Dim annotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Handles the activation of the 3D annotation.

Dim activation As New Pdf3DActivation()

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation

activation.ShowToolbar = True

annotation.Activation = activation

'Creates a new Pdf3DProjection.

Dim projection As New Pdf3DProjection()

projection.ProjectionType = Pdf3DProjectionType.Perspective

projection.FieldOfView = 10

projection.ClipStyle = Pdf3DProjectionClipStyle.ExplicitNearFar

projection.NearClipDistance = 10

'Creates a new Pdf3DView.

Dim view As New Pdf3DView()

view.Projection = projection

view.CameraToWorldMatrix = New Single() {-1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1}

view.ExternalName = "Near View"

annotation.Views.Add(view)

'Adds the annotation in a new page.

page.Annotations.Add(annotation)

'Saves the document to disk.

document.Save("Pdf3DProjection.pdf")
{% endhighlight %}

### 3D Activation

3D Activation determines when a 3D annotation is active or inactive. 3D artwork is activated in one of the following three states. 

* ExplicitActivation-Initial state of the annotation is deactivated. When you want to activate the annotation by clicking it, you can use the explicit annotation. 
* PageOpen-Annotation is activated when opening the PDF document page.
* PageVisible-Annotation is activated when the page is visible. 

Pdf3DActivation class handles the 3D activations. With the help of Pdf3DActivationMode class, you can set the above metioned activaton states.

You can show or hide the toolbar by using the ShowToolbar property.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3D Annotation.

Pdf3DAnnotation annotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

//Creates a new Pdf3DActivation.

Pdf3DActivation activation = new Pdf3DActivation();

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation;

activation.ShowToolbar = false;

annotation.Activation = activation;

page.Annotations.Add(annotation);

//Saves the document to disk.

document.Save("Pdf3DActivation.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new Pdf3D Annotation.

Dim annotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Creates a new Pdf3DActivation.

Dim activation As New Pdf3DActivation()

activation.ActivationMode = Pdf3DActivationMode.ExplicitActivation

activation.ShowToolbar = False

annotation.Activation = activation

page.Annotations.Add(annotation)

'Saves the document to disk.

document.Save("Pdf3DActivation.pdf")
{% endhighlight %}

### 3D Background

3D Background defines the background over which the 3D artwork is to be drawn.

Pdf3DBackground class handles the 3D Background. You can apply background color to the entire annotation by enabling ApplyToEntireAnnotation property. If set to _False_, background would apply only to the rectangle specified by the 3D view box of the annotation. Default value is _False_. 

The following code example illustrates this.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3DAnnotation.

Pdf3DAnnotation annotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

PdfColor color = new PdfColor(Color.Silver);

//Creates a new Pdf3DBackground.

Pdf3DBackground background = new Pdf3DBackground();

background.ApplyToEntireAnnotation = true;

background.Color = color;

Pdf3DView view = new Pdf3DView();

view.Background = background;

view.CameraToWorldMatrix = new float[] { -1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1 };

annotation.Views.Add(view);

page.Annotations.Add(annotation);

//Saves the document to disk.

document.Save("Pdf3DBackground.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new Pdf3DAnnotation.

Dim annotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

Dim color As New PdfColor(System.Drawing.Color.Silver)

'Creates a new Pdf3DBackground.

Dim background As New Pdf3DBackground()

background.ApplyToEntireAnnotation = True

background.Color = color

Dim view As New Pdf3DView()

view.Background = background

view.CameraToWorldMatrix = New Single() {-1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1}

annotation.Views.Add(view)

page.Annotations.Add(annotation)

'Saves the document to disk.

document.Save("Pdf3DBackground.pdf")
{% endhighlight %}

### 3D Render Mode

3D Render Mode specifies the rendering style for 3D artwork. For example, surfaces may be filled with opaque colors that may be stroked as a "wireframe" or the artwork may be rendered with special lighting effects.  

Pdf3DRenderMode class is used to hadle the 3D render mode.

The following are the rendering styles supported by the Pdf3DRenderMode class. 

* Solid 
* SolidWireframe 
* Transparent 
* TransparentWireframe 
* BoundingBox 
* TansparentBoundingBox 
* TransparentBoundingBoxOutline 
* Wireframe 
* ShadedWireframe 
* HiddenWireframe 
* Vertices 
* ShadedVertices 
* Illustration 
* SolidOutline 
* ShadedIllustration 

Apart from using the Style property, you can also change the rendering style by using the following properties.

* AuxilaryColor: PdfColor name that specifies the auxiliary color to be used when rendering the 3D image. The first entry in the array is a color space and the subsequent entries are values specifying color values in that color space. 
* FaceColor: PdfColor name that specifies the face color to be used when rendering the 3D image. This entry is relevant only when the Style property is set to Illustration. 
* Opacity: Number specifying the opacity of the added transparency applied by some rendering modes using a standard additive blend. Default value is _0.5_. 
* CreaseValue: Number specifying the angle in degrees to be used as the crease value while determining silhouette edges. Default value is _45_. 

The following code example illustrates this.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3D Annotation.

Pdf3DAnnotation annotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

//Creates a new Pdf3DRendermode.

Pdf3DRendermode renderMode = new Pdf3DRendermode();

renderMode.Style = Pdf3DRenderStyle.SolidWireframe;

renderMode.AuxilaryColor = new PdfColor(Color.Green);

renderMode.FaceColor = new PdfColor(Color.Black);

//Creates a new Pdf3DView.

Pdf3DView view = new Pdf3DView();

view.RenderMode = renderMode;

view.CameraToWorldMatrix = new float[] { -1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1 };

annotation.Views.Add(view);

page.Annotations.Add(annotation);

//Saves the document to disk.

document.Save("PDF3DRendermode.pdf");
{% endhighlight %}


{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new Pdf3D Annotation.

Dim annotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Creates a new Pdf3DRendermode.

Dim renderMode As New Pdf3DRendermode()

renderMode.Style = Pdf3DRenderStyle.SolidWireframe

renderMode.AuxilaryColor = New PdfColor(Color.Green)

renderMode.FaceColor = New PdfColor(Color.Black)

'Creates a new Pdf3DView.

Dim view As New Pdf3DView()

view.RenderMode = renderMode

view.CameraToWorldMatrix = New Single() {-1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1}

annotation.Views.Add(view)

page.Annotations.Add(annotation)

'Saves the document to disk.

document.Save("PDF3DRendermode.pdf")
{% endhighlight %}

### 3D Lighting

3D Lighting specifies the lighting to be applied to 3D artwork; Pdf3DLighting class handles 3D lighting.

The following lighting effects are supported by Pdf3DLighting class.

* Artwork 
* None 
* White 
* Day 
* Night 
* Hard 
* Primary 
* Blue 
* Red 
* Cube 
* CAD 
* Headlamp 



{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3DAnnotation.

Pdf3DAnnotation annot = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

//Creates a new Pdf3DLighting.

Pdf3DLighting lighting = new Pdf3DLighting();

lighting.Style = Pdf3DLightingStyle.CAD;

//Creates a new Pdf3DView.

Pdf3DView view = new Pdf3DView();

view.LightingScheme = lighting;

view.CameraToWorldMatrix = new float[] { -1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1 };

annot.Views.Add(view);

page.Annotations.Add(annot);

//Saves document to disk.

document.Save("Pdf3DLighting.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new Pdf3DAnnotation.

Dim annot As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Creates a new Pdf3DLighting.

Dim lighting As New Pdf3DLighting()

lighting.Style = Pdf3DLightingStyle.CAD

'Creates a new Pdf3DView.

Dim view As New Pdf3DView()

view.LightingScheme = lighting

view.CameraToWorldMatrix = New Single() {-1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1}

annot.Views.Add(view)

page.Annotations.Add(annot)

'Saves document to disk.

document.Save("Pdf3DLighting.pdf")
{% endhighlight %}

### 3D Cross Section

3D cross section specifies how a portion of 3D artwork is clipped for the purpose of showing artwork cross sections.

Pdf3DCrossSection handles 3D cross section with that you can set the inter section color using IntersectionColor property.

The following code example illustrates this.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new Pdf3DAnnotation.

Pdf3DAnnotation annotation = new Pdf3DAnnotation(new RectangleF(10, 50, 300, 150), "3DAnnotation.U3D");

//Creates a new Pdf3DCrossSection.

Pdf3DCrossSection crossSection = new Pdf3DCrossSection();

crossSection.Color = new PdfColor(Color.Blue);

crossSection.IntersectionIsVisible = true;

crossSection.IntersectionColor = new PdfColor(Color.Red);

//Creates a new Pdf3DView

Pdf3DView view = new Pdf3DView();

view.CrossSections.Add(crossSection);

view.CameraToWorldMatrix = new float[] { -1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1 };

annotation.Views.Add(view);

page.Annotations.Add(annotation);

//Saves the document to disk.

document.Save("Pdf3DCrossSection.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new Pdf3DAnnotation.

Dim annotation As New Pdf3DAnnotation(New RectangleF(10, 50, 300, 150), "3DAnnotation.U3D")

'Creates a new Pdf3DCrossSection.

Dim crossSection As New Pdf3DCrossSection()

crossSection.Color = New PdfColor(Color.Blue)

crossSection.IntersectionIsVisible = True

crossSection.IntersectionColor = New PdfColor(Color.Red)

'Creates a new Pdf3DView.

Dim view As New Pdf3DView()

view.CrossSections.Add(crossSection)

view.CameraToWorldMatrix = New Single() {-1, 0, 0, 0, 1, 0, 0, 0, -1, 0, 0, 1}

annotation.Views.Add(view)

page.Annotations.Add(annotation)

'Saves the document to disk.

document.Save("Pdf3DCrossSection.pdf")
{% endhighlight %}

## File Link Annotation

External files can be hyperlinked in a pdf document using the Annotation feature. An annotation can associate objects such as note, sound or a movie by specifying the corresponding object location in the document.

PdfFileLinkAnnotation class of the Essential PDF can be used to associate an external file to the document as follows.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new PDF file link annotation.

PdfFileLinkAnnotation fileLinkAnnotation = new PdfFileLinkAnnotation(rectangle, "logo.png");

//Adds this annotation to a new page.

page.Annotations.Add(fileLinkAnnotation);

//Saves the document to disk.

document.Save("FileLinkAnnotation.pdf");

document.Close();

{% endhighlight %}

{% highlight vbnet %}

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new PDF file link annotation.

Dim fileLinkAnnotation As New PdfFileLinkAnnotation(rectangle, "logo.png")

'Adds this annotation to a new page.

page.Annotations.Add(fileLinkAnnotation)

'Saves the document to disk.

document.Save("FileLinkAnnotation.pdf")

document.Close()
{% endhighlight %}

## Free Text Annotation

Free text annotation enables you to display text directly on the page. Unlike ordinary text annotation, free text annotation has no open or closed state; the text is not displayed on the pop-up window. When you want to add a comment directly without placing it on a pop-up window, FreeTextAnnotation can be used. Free Text Annotations can be included anywhere in the PDF Document by specifying the location and CallOutLine points.

PdfFreeTextAnnotation calss is used to create the free text annotation.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates PDF free text annotation.

PdfFreeTextAnnotation freeText = new PdfFreeTextAnnotation(new RectangleF(50, 100, 100, 50));

//Sets properties to the annotation.

freeText.MarkupText = "Free Text with Callouts";

freeText.TextMarkupColor = new PdfColor(Color.Black);

freeText.Font = new PdfStandardFont(PdfFontFamily.Helvetica, 7f);

freeText.Color = new PdfColor(Color.Yellow);

freeText.BorderColor = new PdfColor(Color.Red);

freeText.Border = new PdfAnnotationBorder(.5f);

freeText.LineEndingStyle = PdfLineEndingStyle.OpenArrow;

freeText.AnnotationFlags = PdfAnnotationFlags.Default;

freeText.Text = "Free Text";

freeText.Opacity = 0.5f;

PointF[] points = { new PointF(100, 400), new PointF(100, 450) };

freeText.CalloutLines = points;

//Adds the annotation to page.

page.Annotations.Add(freeText);

//Saves the document to disk.

document.Save("FreeTextAnnotation.pdf");

document.Close();
{% endhighlight %}


{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates PDF free text annotation.

Dim freeText As New PdfFreeTextAnnotation(New RectangleF(50, 100, 100, 50))

'Sets properties to the annotation.

freeText.MarkupText = "Free Text with Callouts"

freeText.TextMarkupColor = New PdfColor(Color.Black)

freeText.Font = New PdfStandardFont(PdfFontFamily.Helvetica, 7.0F)

freeText.Color = New PdfColor(Color.Yellow)

freeText.BorderColor = New PdfColor(Color.Red)

freeText.Border = New PdfAnnotationBorder(0.5F)

freeText.LineEndingStyle = PdfLineEndingStyle.OpenArrow

freeText.AnnotationFlags = PdfAnnotationFlags.Default

freeText.Text = "Free Text"

freeText.Opacity = 0.5F

Dim points() As PointF = {New PointF(100, 400), New PointF(100, 450)}

freeText.CalloutLines = points

'Adds the annotation to page.

page.Annotations.Add(freeText)

'Saves the document to disk.

document.Save("FreeTextAnnotation.pdf")

document.Close()
{% endhighlight %}

## Line Annotation

Line annotation displays a single straight line on the page. When you open it, it displays a pop-up window containing text of the associated note.

PdfLineAnnotation is used to create and set the properties to the Line annotation.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Specifies the line end points.

int[] points = new int[] { 80, 420, 150, 420 };

//Creates a new line annotation.

PdfLineAnnotation lineAnnotation = new PdfLineAnnotation(points, "Line Annoation");

//Creates PDF line border.

LineBorder lineBorder = new LineBorder();

lineBorder.BorderStyle = PdfBorderStyle.Solid;

lineBorder.BorderWidth = 1;

lineAnnotation.lineBorder = lineBorder;

lineAnnotation.LineIntent = PdfLineIntent.LineDimension;

//Assigns the line ending style.

lineAnnotation.BeginLineStyle = PdfLineEndingStyle.Butt;

lineAnnotation.EndLineStyle = PdfLineEndingStyle.Diamond;

lineAnnotation.AnnotationFlags = PdfAnnotationFlags.Default;

//Assigns the line color.

lineAnnotation.InnerLineColor = new PdfColor(Color.Green);

lineAnnotation.BackColor = new PdfColor(Color.Green);

//Assigns the leader line.

lineAnnotation.LeaderLineExt = 0;

lineAnnotation.LeaderLine = 0;

//Assigns the Line caption type.

lineAnnotation.LineCaption = true;

lineAnnotation.CaptionType = PdfLineCaptionType.Inline;

//Adds this annotation to a new page.

page.Annotations.Add(lineAnnotation);

//Saves the document to disk.

document.Save("LineAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Specifies the line end points.

Dim points() As Integer = {80, 420, 150, 420}

'Creates a new line annotation.

Dim lineAnnotation As New PdfLineAnnotation(points, "Line Annoation")

'Creates PDF line border.

Dim lineBorder As New LineBorder()

lineBorder.BorderStyle = PdfBorderStyle.Solid

lineBorder.BorderWidth = 1

lineAnnotation.lineBorder = lineBorder

lineAnnotation.LineIntent = PdfLineIntent.LineDimension

'Assigns the line ending style.

lineAnnotation.BeginLineStyle = PdfLineEndingStyle.Butt

lineAnnotation.EndLineStyle = PdfLineEndingStyle.Diamond

lineAnnotation.AnnotationFlags = PdfAnnotationFlags.Default

'Assigns the line color.

lineAnnotation.InnerLineColor = New PdfColor(Color.Green)

lineAnnotation.BackColor = New PdfColor(Color.Green)

'Assigns the leader line.

lineAnnotation.LeaderLineExt = 0

lineAnnotation.LeaderLine = 0

'Assigns the Line caption type.

lineAnnotation.LineCaption = True

lineAnnotation.CaptionType = PdfLineCaptionType.Inline

'Adds this annotation to a new page.

page.Annotations.Add(lineAnnotation)

'Saves the document to disk.

document.Save("LineAnnotation.pdf")
{% endhighlight %}

## Rubber stamp Annotation

Rubber stamp annotation displays text or graphics intended to look like it was stamped on the page with a rubber stamp. When opened, it displays a pop-up window containing the text of the associated note.

PdfRubberStampAnnotation is used to handle rubber stamp annotation.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new PDF rubber stamp annotation.

RectangleF rectangle = new RectangleF(40, 60, 80, 20);

PdfRubberStampAnnotation rubberstampAnnotation = new PdfRubberStampAnnotation(rectangle, " Text Rubber Stamp Annotation");

rubberstampAnnotation.Icon = PdfRubberStampAnnotationIcon.Draft;

rubberstampAnnotation.Text = "Text Properties Rubber Stamp Annotation";

page.Annotations.Add(rubberstampAnnotation);

//Saves the document to disk.

document.Save("Rubberstamp.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new PDF rubber stamp annotation.

Dim rectangle As New RectangleF(40, 60, 80, 20)

Dim rubberstampAnnotation As New PdfRubberStampAnnotation(rectangle, " Text Rubber Stamp Annotation")

rubberstampAnnotation.Icon = PdfRubberStampAnnotationIcon.Draft

rubberstampAnnotation.Text = "Text Properties Rubber Stamp Annotation"

page.Annotations.Add(rubberstampAnnotation)

'Saves the document to disk.

document.Save("Rubberstamp.pdf")
{% endhighlight %}

## Ink Annotation

Ink annotation represents freehand “scribble” comprising one or more disjoint paths. When you open it, it displays a pop-up window containing text of the associated note.

PdfInkAnnotation class handles Ink annotation.

## Pop-up Annotation

Pop-up annotation displays text in a pop-up window for entry and editing. It typically does not appear alone, but is associated with markup annotation, its parent annotation, and is used for editing the parent’s text.

PdfPopupAnnotation handles the pop-up annotation.

{% highlight c# %}



//Creates a new PDF document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new pop-up annotation.

PdfPopupAnnotation popupAnnotation = new PdfPopupAnnotation(rectangle, "Test popup annotation");

popupAnnotation.Border.Width = 4;

popupAnnotation.Border.HorizontalRadius = 20;

popupAnnotation.Border.VerticalRadius = 30;

//Sets the PDF pop-up icon.

popupAnnotation.Icon = PdfPopupIcon.NewParagraph;

//Adds this annotation to a new page.

page.Annotations.Add(popupAnnotation);

//Saves the document to disk.

document.Save("PopupAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new popup annotation.

Dim popupAnnotation As New PdfPopupAnnotation(rectangle, "Test popup annotation")

popupAnnotation.Border.Width = 4

popupAnnotation.Border.HorizontalRadius = 20

popupAnnotation.Border.VerticalRadius = 30

'Sets the PDF pop-up icon.

popupAnnotation.Icon = PdfPopupIcon.NewParagraph

'Adds this annotation to a new page.

page.Annotations.Add(popupAnnotation)

'Saves the document to disk.

document.Save("PopupAnnotation.pdf")
{% endhighlight %}

## File Attachment Annotation

File attachment annotation contains reference to a file that typically is embedded in the PDF file.

PdfAttachmentAnnotation class is used to create file attachement annotation.

{% highlight c# %}



//Creates a new PDF Document.

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF attachmentRectangle = new RectangleF(10, 40, 30, 30);

//Creates a new attachment annotation.

PdfAttachmentAnnotation attachmentAnnotation = new PdfAttachmentAnnotation(attachmentRectangle, "logo.png");

//Sets the attachment icon to attachment annotation.

attachmentAnnotation.Icon = PdfAttachmentIcon.PushPin;

//Adds this annotation to a new page.

page.Annotations.Add(attachmentAnnotation);

//Saves the document to disk.

document.Save("AttachmentAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}



'Creates a new PDF Document.

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim attachmentRectangle As New RectangleF(10, 40, 30, 30)

'Creates a new attachment annotation.

Dim attachmentAnnotation As New PdfAttachmentAnnotation(attachmentRectangle, "logo.png")

'Sets the attachment icon to attachment annotation.

attachmentAnnotation.Icon = PdfAttachmentIcon.PushPin

'Adds this annotation to a new page.

page.Annotations.Add(attachmentAnnotation)

'Saves the document to disk.

document.Save("AttachmentAnnotation.pdf")
{% endhighlight %}

## Sound Annotation

Sound annotation is similar to text annotation except that it contains sound recorded from the computer’s microphone or imported from a file instead of a text note. When the annotation is activated, the sound is played.

PdfSoundAnnotation class used to create sound annotation

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new sound annotation.

PdfSoundAnnotation soundAnnotation = new PdfSoundAnnotation(rectangle, "startup.wav");

soundAnnotation.Sound.Encoding = PdfSoundEncoding.Signed;

soundAnnotation.Sound.Channels = PdfSoundChannels.Stereo;

soundAnnotation.Sound.Bits = 16;

soundAnnotation.Color = new PdfColor(Color.Red);

//Sets the PDF sound icon.

soundAnnotation.Icon = PdfSoundIcon.Speaker;

//Adds this annotation to a new page.

page.Annotations.Add(soundAnnotation);

//Saves the document to disk.

document.Save("SoundIcon.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new sound annotation.

Dim soundAnnotation As New PdfSoundAnnotation(rectangle, "startup.wav")

soundAnnotation.Sound.Encoding = PdfSoundEncoding.Signed

soundAnnotation.Sound.Channels = PdfSoundChannels.Stereo

soundAnnotation.Sound.Bits = 16

soundAnnotation.Color = New PdfColor(Color.Red)

'Sets the PDF sound icon.

soundAnnotation.Icon = PdfSoundIcon.Speaker

'Adds this annotation to a new page.

page.Annotations.Add(soundAnnotation)

'Saves the document to disk.

document.Save("SoundIcon.pdf")
{% endhighlight %}

## URI Annotation

URI annotation is used to navigate to a particular web URI.

PdfUriAnnotation is used to create URI annotation.

{% highlight c# %}

PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF rectangle = new RectangleF(10, 40, 30, 30);

//Creates a new URI annotation.

PdfUriAnnotation uriAnnotation = new PdfUriAnnotation(rectangle, "http://www.google.com");

//Sets Text to URIAnnotation.

uriAnnotation.Text = "Uri Annotation";

//Adds this annotation to a new page.

page.Annotations.Add(uriAnnotation);

//Saves the document to disk.

document.Save("UriAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim rectangle As New RectangleF(10, 40, 30, 30)

'Creates a new URI Annotation.

Dim uriAnnotation As New PdfUriAnnotation(rectangle, "http://www.google.com")

'Sets Text to URIAnnotation.

uriAnnotation.Text = "Uri Annotation"

'Adds this annotation to a new page.

page.Annotations.Add(uriAnnotation)

'Saves the document to disk.

document.Save("UriAnnotation.pdf")
{% endhighlight %}

## Document Link Annotation

This annotation is used to navigate to a specific destination within the document.

PdfDocumentLinkAnnotation class is used to create the document link annotation and PdfDestination class is used to specify the destination of document link annotation.

{% highlight c# %}



PdfDocument document = new PdfDocument();

//Creates a new page and adds it as the last page of the document.

PdfPage page = document.Pages.Add();

//Creates a new rectangle.

RectangleF docLinkAnnotationRectangle = new RectangleF(10, 40, 30, 30);

//Creates a new document link annotation.

PdfDocumentLinkAnnotation documentLinkAnnotation = new PdfDocumentLinkAnnotation(docLinkAnnotationRectangle);

//Sets the annotation flags.

documentLinkAnnotation.AnnotationFlags = PdfAnnotationFlags.NoRotate;

//Sets the annotation text.

documentLinkAnnotation.Text = "Document link annotation";

//Set the annotation's color.

documentLinkAnnotation.Color = new PdfColor(Color.Navy);

//Creates a new page and adds it as the last page of the document.

PdfPage page2 = document.Pages.Add();

//Sets the PDF destination.

documentLinkAnnotation.Destination = new PdfDestination(page2);

//Sets the documentlink annotation location.

documentLinkAnnotation.Destination.Location = new Point(10, 0);

//Sets the document annotation zool level.

documentLinkAnnotation.Destination.Zoom = 5;

//Adds this annotation to a new page.

page.Annotations.Add(documentLinkAnnotation);

//Saves the document to disk.

document.Save("DocumentLinkAnnotation.pdf");

{% endhighlight %}

{% highlight vbnet %}



Dim document As New PdfDocument()

'Creates a new page and adds it as the last page of the document.

Dim page As PdfPage = document.Pages.Add()

'Creates a new rectangle.

Dim docLinkAnnotationRectangle As New RectangleF(10, 40, 30, 30)

'Creates a new document link annotation.

Dim documentLinkAnnotation As New PdfDocumentLinkAnnotation(docLinkAnnotationRectangle)

'Sets the annotation flags.

documentLinkAnnotation.AnnotationFlags = PdfAnnotationFlags.NoRotate

'Sets the annotation text.

documentLinkAnnotation.Text = "Document link annotation"

'Sets the annotation's color.

documentLinkAnnotation.Color = New PdfColor(Color.Navy)

'Creates a new page and adds it as the last page of the document.

Dim page2 As PdfPage = document.Pages.Add()

'Sets the PDF destination.

documentLinkAnnotation.Destination = New PdfDestination(page2)

'Sets the documentlink annotation location.

documentLinkAnnotation.Destination.Location = New Point(10, 0)

'Sets the document annotation zoom level.

documentLinkAnnotation.Destination.Zoom = 5

'Adds this annotation to a new page.

page.Annotations.Add(documentLinkAnnotation)

'Saves the document to disk.

document.Save("DocumentLinkAnnotation.pdf")

{% endhighlight %}

