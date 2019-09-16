---
layout: post
title: Inclusion of Shape Annotation in a PDF document in Syncfusion Essential WPF PDF viewer.
description: Inclusion of Shape Annotation in a PDF document in Syncfusion Essential WPF PDF viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---
# Shape Annotation

PDF viewer WPF allows the user to include the following shape annotations into the PDF document.

* Line annotations
* Rectangle annotation
* Circle annotation
* Polygon Annotation

# Line Annotation

PDF viewer WPF allows the user to include line annotation into the PDF document and provides options to edit or remove the existing line annotation in the PDF document.

The following code shows how to switch to line annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Line;
}


{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Line
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the line annotation being included in the PDF Document.

   ![](Annotation-images\Line-Annotation-1.png)

# How to set the color of the line annotation?

The color of the line annotation included can be customized at the time of inclusion itself. The following code shows how to set color of the line annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.LineAnnotationSettings.LineColor = Colors.Blue;
}


{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.LineAnnotationSettings.LineColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the opacity of the line annotation?

The opacity of the line annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value of the included line annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.LineAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.LineAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the thickness of the line annotation?

The thickness of the line annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness of the included line annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.LineAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.LineAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the author and subject of the line annotation?

The author and subject fields of the line annotation can be added for the line annotation to be added to the PDF document. The following code shows how to set default Author and subject of the included line annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.LineAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.LineAnnotationSettings.Subject = "Line Annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.LineAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.LineAnnotationSettings.Subject = "Line Annotation"    
End Sub

{% endhighlight %}
{% endtabs %}

# Working with included/existing line annotations

Line annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing line annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

## Open Pop-up notes

We can add notes to the line annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected line annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

   ![](Annotation-images\Line-Annotation-2.png)

## Properties

Selecting properties from the context menu will display the line Properties window, which would consist of two tabs

* Appearance
* General 

## Appearance tab

The color, opacity and thickness of the line annotation can be edited using Appearance tab of line Properties window.

### Editing the thickness of the line annotation

Modifying the value in the NumericUpDown control in the Appearance tab of line annotation properties window will allow us to modify the thickness of the selected line annotation.

The following image illustrates how to change the thickness of the line annotation.

   ![](Annotation-images\Line-Annotation-3.png)

The following image illustrates the change in thickness of the selected line annotation.

   ![](Annotation-images\Line-Annotation-4.png)

### Editing color of the annotation

The color of the selected line annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the line annotation.

The following image illustrates how to change the color of the line annotation included.

   ![](Annotation-images\Line-Annotation-5.png)

The following image illustrates the change in the color of the included line annotation.

   ![](Annotation-images\Line-Annotation-6.png)

### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected line annotation. You can also modify the opacity of the selected line annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included line annotation.

  ![](Annotation-images\Line-Annotation-7.png)

The following image illustrates the change in the opacity of the included line annotation.

   ![](Annotation-images\Line-Annotation-8.png)

## General tab

We can add/edit the default Author and Subject to the included line annotation using General tab of the Line Properties window.

The following image illustrates the change in Author and Subject of the included line annotation.

  ![](Annotation-images\Line-Annotation-9.png)

## Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

  ![](Annotation-images\Line-Annotation-10.png)

# Rectangle Annotation

PDF viewer WPF allows the user to include Rectangle annotation into the PDF document and provides options to edit or remove the existing rectangle annotation in the PDF document.

The following code shows how to switch to rectangle annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Rectangle;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Rectangle
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the rectangle annotation being included in the PDF Document.

   ![](Annotation-images\Rectangle-Annotation-1.png)

# How to set the color of the rectangle annotation?

The color of the rectangle annotation included can be customized at the time of inclusion itself. The following code shows how to set default color of the included rectangle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.RectangleAnnotationSettings.RectangleColor = Colors.Blue;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.RectangleAnnotationSettings.RectangleColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the opacity of the rectangle annotation?

The opacity of the rectangle annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value of the included rectangle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.RectangleAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.RectangleAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the thickness of the rectangle annotation?

The thickness of the rectangle annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness of the included rectangle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.RectangleAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.RectangleAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the author and subject of the rectangle annotation?

The author and subject fields of the rectangle annotation can be added for the rectangle annotation to be added to the PDF document. The following code shows how to set default Author and subject of the included rectangle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.RectangleAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.RectangleAnnotationSettings.Subject = "Rectangle Annotation"; 
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.RectangleAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.RectangleAnnotationSettings.Subject = "Rectangle Annotation"    
End Sub

{% endhighlight %}
{% endtabs %}

# Working with included/existing rectangle annotations

Rectangle annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing rectangle annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

## Open Pop-up notes

We can add notes to the rectangle annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected rectangle annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

  ![](Annotation-images\Rectangle-Annotation-2.png)

## Properties

Selecting properties from the context menu will display the Rectangle Properties window, which would consist of two tabs

* Appearance
* General 

## Appearance tab

The color and opacity of the rectangle annotation can be edited using Appearance tab of Rectangle Properties window.

### Editing the thickness of the rectangle annotation

Modifying the value in the NumericUpDown control in the Appearance tab of rectangle annotation properties window will allow us to modify the thickness of the selected rectangle annotation.

The following image illustrates how to change the thickness of the rectangle annotation.

  ![](Annotation-images\Rectangle-Annotation-3.png)

The following image illustrates the change in thickness of the selected rectangle annotation.

  ![](Annotation-images\Rectangle-Annotation-4.png)

### Editing color of the annotation

The color of the selected rectangle annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the rectangle annotation.

The following image illustrates how to change the color of the rectangle annotation included.

  ![](Annotation-images\Rectangle-Annotation-5.png)

The following image illustrates the change in the color of the included rectangle annotation.

  ![](Annotation-images\Rectangle-Annotation-6.png)

### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected rectangle annotation. You can also modify the opacity of the selected rectangle annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included rectangle annotation.

  ![](Annotation-images\Rectangle-Annotation-7.png)

The following image illustrates the change in the opacity of the included rectangle annotation.	

  ![](Annotation-images\Rectangle-Annotation-8.png)

## General tab

We can add/edit the default Author and Subject to the included rectangle annotation using General tab of the Rectangle Properties window.

The following image illustrates the change in Author and Subject of the included rectangle annotation.

  ![](Annotation-images\Rectangle-Annotation-9.png)

## Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

 ![](Annotation-images\Rectangle-Annotation-10.png)



# Circle Annotation

PDF viewer WPF allows the user to include circle annotation into the PDF document and provides options to edit or remove the existing circle annotation in the PDF document.

The following code shows how to switch to circle annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Circle;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Circle
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the circle annotation being included in the PDF Document.

  ![](Annotation-images\Circle-Annotation-1.png)

# How to set the color of the circle annotation?

The color of the circle annotation included can be customized at the time of inclusion itself. The following code shows how to set default color of the included circle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.CircleAnnotationSettings.CircleColor = Colors.Blue;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.CircleAnnotationSettings.CircleColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the opacity of the circle annotation?

The opacity of the circle annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value of the included circle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.CircleAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.CircleAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the thickness of the circle annotation?

The thickness of the circle annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness of the included circle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.CircleAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.CircleAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the author and subject of the circle annotation?

The author and subject fields of the circle annotation can be added for the circle annotation to be added to the PDF document. The following code shows how to set default Author and subject of the included circle annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.CircleAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.CircleAnnotationSettings.Subject = "Circle Annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.CircleAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.CircleAnnotationSettings.Subject = "Circle Annotation"    
End Sub

{% endhighlight %}
{% endtabs %}

# Working with included/existing circle annotations

Circle annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing circle annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*   Open Pop-up note
*	Properties
*	Delete

## Open Pop-up notes

We can add notes to the circle annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected circle annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

 ![](Annotation-images\Circle-Annotation-2.png)

## Properties

Selecting properties from the context menu will display the Circle Properties window, which would consist of two tabs

*	Appearance
*	General 

## Appearance tab

The color and opacity of the circle annotation can be edited using Appearance tab of Oval Properties window.

### Editing the thickness of the circle annotation

Modifying the value in the NumericUpDown control in the Appearance tab of circle annotation properties window will allow us to modify the thickness of the selected circle annotation.

The following image illustrates how to change the thickness of the circle annotation.

![](Annotation-images\Circle-Annotation-3.png)

The following image illustrates the change in thickness of the selected circle annotation.

![](Annotation-images\Circle-Annotation-4.png)

### Editing color of the annotation

The color of the selected circle annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the circle annotation.

The following image illustrates how to change the color of the circle annotation included.

![](Annotation-images\Circle-Annotation-5.png)

The following image illustrates the change in the color of the included circle annotation.

![](Annotation-images\Circle-Annotation-6.png)

### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected circle annotation. You can also modify the opacity of the selected circle annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included circle annotation.

![](Annotation-images\Circle-Annotation-7.png)

The following image illustrates the change in the opacity of the included circle annotation.	

![](Annotation-images\Circle-Annotation-8.png)

## General tab

We can add/edit the default Author and Subject to the included circle annotation using General tab of the Oval Properties window.

The following image illustrates the change in Author and Subject of the included circle annotation.

![](Annotation-images\Circle-Annotation-9.png)

## Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![](Annotation-images\Circle-Annotation-10.png)

# Polygon Annotation

PDF viewer allows the user to include polygon annotation into the PDF document and provides options to edit or remove the existing polygon annotation in the PDF document.

The following code shows how to switch to polygon annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Polygon;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Polygon
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the polygon annotation being included in the PDF Document.

   ![Polygon Annotation](Annotation-images\Polygon-Annotation-1.png)

# How to set the stroke color of the polygon annotation?

The stroke color of the polygon annotation included can be customized at the time of inclusion itself. The following code shows how to set stroke color of the polygon annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolygonAnnotationSettings.StrokeColor = Colors.Blue;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolygonAnnotationSettings.StrokeColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the opacity of the polygon annotation?

The opacity of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value of the included polygon annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolygonAnnotationSettings.Opacity = 0.5F;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolygonAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the thickness of the polygon annotation?

The thickness of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness of the included polygon annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolygonAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolygonAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the fill color of the polygon annotation?

The fill color of the polygon annotation included can be customized at the time of inclusion itself. The following code shows how to set fill color of the polygon annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolygonAnnotationSettings.FillColor = Colors.Gray;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolygonAnnotationSettings.FillColor = Colors.Gray
End Sub

{% endhighlight %}
{% endtabs %}

# How to set the author and subject of the polygon annotation?

The author and subject fields of the polygon annotation can be added for the polygon annotation to be added to the PDF document. The following code shows how to set default Author and subject of the included polygon annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolygonAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.PolygonAnnotationSettings.Subject = "Polygon Annotation";  
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolygonAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.PolygonAnnotationSettings.Subject = "Polygon Annotation"    
End Sub

{% endhighlight %}
{% endtabs %}

# Working with included/existing polygon annotations

Polygon annotation supports adding notes along with it, also it allows editing its stroke color, fill color, opacity and thickness. To use these options, select the included/existing polygon annotation and click right using mouse, over the selected annotation, a popup context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

## Open Pop-up notes

We can add notes to the polygon annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected polygon annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

  ![Open popup note](Annotation-images\Polygon-Annotation-2.png)

## Properties

Selecting properties from the context menu will display the Polygon Properties window, which would consist of two tabs

* Appearance
* General 

## Appearance tab

The stroke color, fill color, thickness and opacity of the polygon annotation can be edited using Appearance tab of Polygon Properties window.

### Editing the thickness of the polygon annotation

Modifying the value in the NumericUpDown control in the Appearance tab of polygon annotation properties window will allow us to modify the thickness of the selected polygon annotation.

The following image illustrates how to change the thickness of the polygon annotation.

  ![Before applying polygon thickness](Annotation-images\Polygon-Annotation-3.png)

The following image illustrates the change in thickness of the selected polygon annotation.

  ![After applied polygon thickness](Annotation-images\Polygon-Annotation-4.png)

### Editing stroke color of the annotation

The stroke color of the selected polygon annotation will be displayed in the color row in the Appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the stroke color to the polygon annotation.

The following image illustrates how to change the stroke color of the polygon annotation included.

  ![Before applying polygon stroke color](Annotation-images\Polygon-Annotation-5.png)

The following image illustrates the change in the stroke color of the included polygon annotation.

  ![After applied polygon stroke color](Annotation-images\Polygon-Annotation-6.png)
  
### Editing fill color of the annotation

The fill color of the selected polygon annotation will be displayed in the Fill Color row in the Appearance tab. Selecting the Fill Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the fill color to the polygon annotation.

The following image illustrates how to change the fill color of the polygon annotation included.

  ![Before applying polygon fil color](Annotation-images\Polygon-Annotation-7.png)

The following image illustrates the change in the fill color of the included polygon annotation.

  ![After applied polygon fill color](Annotation-images\Polygon-Annotation-8.png)

### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected polygon annotation. You can also modify the opacity of the selected polygon annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included polygon annotation.

  ![Before applying polygon opacity](Annotation-images\Polygon-Annotation-9.png)

The following image illustrates the change in the opacity of the included polygon annotation.	

  ![After applied polygon opacity](Annotation-images\Polygon-Annotation-10.png)

## General tab

We can add/edit the default Author and Subject to the included polygon annotation using General tab of the Polygon Properties window.

The following image illustrates the change in Author and Subject of the included polygon annotation.

  ![General Tab](Annotation-images\Polygon-Annotation-11.png)

## Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

 ![Delete polygon annotation](Annotation-images\Polygon-Annotation-12.png)

## Keyboard shortcuts

The below keyboard shortcuts are available to customize the annotation in the PDF document.

*	Delete key – Deletes the selected annotation from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.




























      



