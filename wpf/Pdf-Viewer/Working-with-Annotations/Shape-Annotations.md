---
layout: post
title: Shape Annotations in WPF Pdf Viewer control | Syncfusion
description: Learn about Shape Annotations support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---
# Shape Annotations in WPF Pdf Viewer

PDF viewer WPF allows the user to include the following shape annotations into the PDF document.

* Line.
* Rectangle.
* Circle.
* Arrow.
* Polygon.
* Polyline.

## Line Annotation

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

   ![line annotation](Annotation-images\Line-Annotation-1.png)

### How to set the color of the line annotation?

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

### How to set the opacity of the line annotation?

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

### How to set the thickness of the line annotation?

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

### How to set the author and subject of the line annotation?

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

### Working with included/existing line annotations

Line annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing line annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

#### Open Pop-up notes

We can add notes to the line annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected line annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

   ![line annotation](Annotation-images\Line-Annotation-2.png)

#### Properties

Selecting properties from the context menu will display the line Properties window, which would consist of two tabs

* Appearance
* General 

#### Appearance tab

The color, opacity and thickness of the line annotation can be edited using Appearance tab of line Properties window.

##### Editing the thickness of the line annotation

Modifying the value in the NumericUpDown control in the Appearance tab of line annotation properties window will allow us to modify the thickness of the selected line annotation.

The following image illustrates how to change the thickness of the line annotation.

   ![line annotation](Annotation-images\Line-Annotation-3.png)

The following image illustrates the change in thickness of the selected line annotation.

   ![line annotation](Annotation-images\Line-Annotation-4.png)

##### Editing color of the annotation

The color of the selected line annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the line annotation.

The following image illustrates how to change the color of the line annotation included.

   ![line annotation](Annotation-images\Line-Annotation-5.png)

The following image illustrates the change in the color of the included line annotation.

   ![line annotation](Annotation-images\Line-Annotation-6.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected line annotation. You can also modify the opacity of the selected line annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included line annotation.

  ![line annotation](Annotation-images\Line-Annotation-7.png)

The following image illustrates the change in the opacity of the included line annotation.

   ![line annotation](Annotation-images\Line-Annotation-8.png)

#### General tab

We can add/edit the default Author and Subject to the included line annotation using General tab of the Line Properties window.

The following image illustrates the change in Author and Subject of the included line annotation.

  ![line annotation](Annotation-images\Line-Annotation-9.png)

#### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

  ![line annotation](Annotation-images\Line-Annotation-10.png)

## Rectangle Annotation

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

   ![rectangle annotation](Annotation-images\Rectangle-Annotation-1.png)

### How to set the color of the rectangle annotation?

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

### How to set the opacity of the rectangle annotation?

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

### How to set the thickness of the rectangle annotation?

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

### How to set the author and subject of the rectangle annotation?

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

### Working with included/existing rectangle annotations

Rectangle annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing rectangle annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

#### Open Pop-up notes

We can add notes to the rectangle annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected rectangle annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-2.png)

#### Properties

Selecting properties from the context menu will display the Rectangle Properties window, which would consist of two tabs

* Appearance
* General 

#### Appearance tab

The color and opacity of the rectangle annotation can be edited using Appearance tab of Rectangle Properties window.

##### Editing the thickness of the rectangle annotation

Modifying the value in the NumericUpDown control in the Appearance tab of rectangle annotation properties window will allow us to modify the thickness of the selected rectangle annotation.

The following image illustrates how to change the thickness of the rectangle annotation.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-3.png)

The following image illustrates the change in thickness of the selected rectangle annotation.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-4.png)

##### Editing color of the annotation

The color of the selected rectangle annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the rectangle annotation.

The following image illustrates how to change the color of the rectangle annotation included.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-5.png)

The following image illustrates the change in the color of the included rectangle annotation.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-6.png)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected rectangle annotation. You can also modify the opacity of the selected rectangle annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included rectangle annotation.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-7.png)

The following image illustrates the change in the opacity of the included rectangle annotation.	

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-8.png)

##### Border Styles

PDF viewer allows the users to change the annotation border style. Currently, it provides support for following border style. 

* Cloudy
* Solid

By default, the annotation border style will be solid.

##### Changing the border style from UI

The border style of the selected rectangle annotation will be displayed in the combo box control of the appearance tab. This combo box will allow us to modify the border style of the selected rectangle shape.

The following image illustrates how to change the border style of the rectangle annotation.

![WPF PDFViewer Before applying rectangle annotation border style](Annotation-images\WPF-PDFViewer-Before-applying-rectangle-annotation-border-style.png)

The following image illustrates the change of thickness in the selected rectangle annotation.

![WPF PDFViewer After applying rectangle annotation border style](Annotation-images\WPF-PDFViewer-After-applying-rectangle-annotation-border-style.png)

##### Changing the border style programmatically

The rectangle annotation can be customized at the time of inclusion. The following code shows how to set the default border style of the included rectangle annotation by using the [BorderEffect](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerRectangleSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerRectangleSettings_BorderEffect) property.

{% tabs %}
{% highlight C# %}
private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Rectangle;
    pdfViewer.RectangleAnnotationSettings.BorderEffect = BorderEffect.Cloudy;
}

{% endhighlight %}
{% endtabs %}

#### General tab

We can add/edit the default Author and Subject to the included rectangle annotation using General tab of the Rectangle Properties window.

The following image illustrates the change in Author and Subject of the included rectangle annotation.

  ![rectangle annotation](Annotation-images\Rectangle-Annotation-9.png)

#### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

 ![rectangle annotation](Annotation-images\Rectangle-Annotation-10.png)



## Circle Annotation

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

  ![circle annotation](Annotation-images\Circle-Annotation-1.png)

### How to set the color of the circle annotation?

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

### How to set the opacity of the circle annotation?

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

### How to set the thickness of the circle annotation?

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

### How to set the author and subject of the circle annotation?

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

### Working with included/existing circle annotations

Circle annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the included/existing circle annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*   Open Pop-up note
*	Properties
*	Delete

#### Open Pop-up notes

We can add notes to the circle annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected circle annotation. The added notes will be saved along with the PDF document and if there is any existing notes, it will be displayed in here.

 ![circle annotation](Annotation-images\Circle-Annotation-2.png)

#### Properties

Selecting properties from the context menu will display the Circle Properties window, which would consist of two tabs

*	Appearance
*	General 

#### Appearance tab

The color and opacity of the circle annotation can be edited using Appearance tab of Oval Properties window.

##### Editing the thickness of the circle annotation

Modifying the value in the NumericUpDown control in the Appearance tab of circle annotation properties window will allow us to modify the thickness of the selected circle annotation.

The following image illustrates how to change the thickness of the circle annotation.

![circle annotation](Annotation-images\Circle-Annotation-3.png)

The following image illustrates the change in thickness of the selected circle annotation.

![circle annotation](Annotation-images\Circle-Annotation-4.png)

##### Editing color of the annotation

The color of the selected circle annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the circle annotation.

The following image illustrates how to change the color of the circle annotation included.

![circle annotation](Annotation-images\Circle-Annotation-5.png)

The following image illustrates the change in the color of the included circle annotation.

![circle annotation](Annotation-images\Circle-Annotation-6.png)

##### Editing opacity of the annotation

The slider displayed in the Appearance tab will allow us to modify the opacity of the selected circle annotation. You can also modify the opacity of the selected circle annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included circle annotation.

![circle annotation](Annotation-images\Circle-Annotation-7.png)

The following image illustrates the change in the opacity of the included circle annotation.	

![circle annotation](Annotation-images\Circle-Annotation-8.png)

#### General tab

We can add/edit the default Author and Subject to the included circle annotation using General tab of the Oval Properties window.

The following image illustrates the change in Author and Subject of the included circle annotation.

![circle annotation](Annotation-images\Circle-Annotation-9.png)

#### Deleting an annotation

Selecting delete option from the context menu which will be displayed by right click on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![circle annotation](Annotation-images\Circle-Annotation-10.png)

## Arrow

PDF Viewer provides an option to include, edit, or remove the arrow in a PDF document. The following code shows how to execute the annotation command for arrow annotation.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl"/>	
    <Button Content="Arrow" CommandParameter="Arrow" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}

{% highlight C# %}

private void GoToArrowAnnotationMode()
{
	pdfViewer.AnnotationCommand.Execute("Arrow");
}

{% endhighlight %}
{% endtabs %}

### How to set the stroke color

The stroke color of the arrow can be customized at the time of inclusion itself. The following code shows how to set default stroke color of the arrow to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArrowAnnotationSettings.StrokeColor = Colors.Blue; 
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArrowAnnotationSettings.StrokeColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the fill color of the arrow

The fill color of the arrow can be customized at the time of inclusion itself. The following code shows how to set default fill color of the arrow to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArrowAnnotationSettings.FillColor = Colors.Blue; 
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArrowAnnotationSettings.FillColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the opacity of the arrow

The opacity of the arrow can be customized at the time of inclusion itself. The following code shows how to set default opacity value for the arrow in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArrowAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArrowAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the thickness of the arrow

The thickness of the arrow can be customized at the time of inclusion itself. The following code shows how to set the default thickness for the arrow in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArrowAnnotationSettings.Thickness = 5; 
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArrowAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the begin and end style of the arrow

The begin and end style of the arrow can be customized at the time of inclusion itself. The following code shows how to set default begin and end style for the arrow in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e) 
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArrowAnnotationSettings.BeginLineStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.OpenArrow;
 pdfviewer.ArrowAnnotationSettings.EndLineStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.Diamond;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArrowAnnotationSettings.BeginLineStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.OpenArrow
    pdfviewer.ArrowAnnotationSettings.EndLineStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.Diamond
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the author and subject of the arrow

The author and subject fields of the arrow can be added at the time of inclusion itself. The following code shows how to set default author and subject of the arrow in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
 PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
 pdfviewer.Load(pdf);
 pdfviewer.ArroannotationSettings.Author = "Syncfusion Softwares";
 pdfviewer.ArrowAnnotationSettings.Subject = "Line Annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim pdf As PdfLoadedDocument = New PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf)
    pdfviewer.ArroannotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.ArrowAnnotationSettings.Subject = "Line Annotation"
End Sub

{% endhighlight %}
{% endtabs %}

### Working with existing arrow shapes

Arrow shape supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the existing arrow shape and right-click using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

#### Open Pop-up notes

You can add notes to the arrow shape by choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected arrow shape. The added notes will be saved along with the PDF document and if there are any existing notes, it will be displayed here.

   ![arrow shape](Annotation-images\Arrow-Annotation-1.png)

#### Properties

Selecting properties from the context menu will display the Properties window that consists of two tabs:

* Appearance
* General 

#### Appearance tab

The stroke color, fill color, begin style, end style, opacity and thickness of the arrow shape can be edited using Appearance tab of Properties window.

##### Editing thickness of the arrow

Modifying the value in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control in the Appearance tab of properties window will allow us to modify the thickness of the selected arrow shape.

The following image illustrates how to change the thickness of the arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-2.png)

The following image illustrates the change in the thickness of the arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-3.png)

##### Editing stroke color of the arrow

The stroke color of the selected arrow will be displayed in the color row in the Appearance tab. Selecting the Color will display the color palette control, choosing a color from the color palette and clicking OK will apply the color to the arrow shape.

The following image illustrates how to change the color of the arrow.

   ![arrow shape](Annotation-images\Arrow-Annotation-4.png)

The following image illustrates the change in the color of the arrow.

   ![arrow shape](Annotation-images\Arrow-Annotation-5.png)

##### Editing fill color of the annotation

The fill color of the selected arrow will be displayed in the color row in the appearance tab. Selecting the Fill Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the fill color to the arrow shape styles.

The following image illustrates how to change the fill color of the arrow shape included.

   ![arrow shape](Annotation-images\Arrow-Annotation-6.png)

The following image illustrates the change in the fill color of the included arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-7.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected arrow shape. You can also modify the opacity of the selected arrow shape by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included arrow shape.

  ![arrow shape](Annotation-images\Arrow-Annotation-8.png)

The following image illustrates the change in the opacity of the included arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-9.png)
   
##### Editing begin and end style of the arrow shape

The combo box control displayed in the Appearance tab will allow us to modify the begin and end style of the selected arrow shape.

The following image illustrates how to change the begin style of the included arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-10.png)

The following image illustrates how to change the end begin of the included arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-11.png)

The following image illustrates the change in the start and end style of the included arrow shape.

   ![arrow shape](Annotation-images\Arrow-Annotation-12.png)

#### General tab

You can add/edit the default Author and Subject to the included arrow shape using General tab of the arrow Properties window.

The following image illustrates the change in Author and Subject of the included arrow shape.

  ![arrow shape](Annotation-images\Arrow-Annotation-13.png)

#### Deleting an annotation

Select the delete option from the context menu, which will be displayed by right-clicking the selected annotation to delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

  ![arrow shape](Annotation-images\Arrow-Annotation-14.png)

## Polygon Annotation

PDF Viewer provides an option to include, edit, or remove the polygon annotation in a PDF document.

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

The following image shows the polygon annotation included in the PDF Document.

   ![Polygon Annotation](Annotation-images\Polygon-Annotation-1.png)

### How to set the stroke color of the polygon annotation

The stroke color of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set default stroke color of the polygon annotation to be included.

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

### How to set the fill color of the polygon annotation

The fill color of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set default fill color of the polygon annotation to be included.

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

### How to set the opacity of the polygon annotation

The opacity of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value for the polygon annotation in code behind.

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

### How to set the thickness of the polygon annotation

The thickness of the polygon annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness for the polygon annotation in code behind.

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

### How to set the author and subject of the polygon annotation

The author and subject fields of the polygon annotation can be added at the time of inclusion itself. The following code shows how to set default author and subject of the polygon annotation in code behind.

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

### Working with existing polygon annotations

Polygon annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the existing polygon annotation and right-click using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

#### Open Pop-up notes

You can add notes to the arrow shape by choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected polygon annotation. The added notes will be saved along with the PDF document and if there are any existing notes, it will be displayed here.

  ![Open popup note](Annotation-images\Polygon-Annotation-2.png)

#### Properties

Selecting properties from the context menu will display the Properties window that consists of two tabs:

* Appearance
* General 

#### Appearance tab

The stroke color, fill color, thickness and opacity of the polygon annotation can be edited using Appearance tab of Polygon Properties window.

##### Editing the thickness of the polygon annotation

Modifying the value in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control in the Appearance tab of polygon annotation properties window will allow us to modify the thickness of the selected polygon annotation.

The following image illustrates how to change the thickness of the polygon annotation.

  ![Before applying polygon thickness](Annotation-images\Polygon-Annotation-3.png)

The following image illustrates the change in thickness of the selected polygon annotation.

  ![After applied polygon thickness](Annotation-images\Polygon-Annotation-4.png)

##### Editing stroke color of the annotation

The stroke color of the selected polygon annotation will be displayed in the color row in the Appearance tab. Selecting the Color will display the color palette control, choosing a color from the color palette and clicking OK will apply the color to the polygon annotation.

The following image illustrates how to change the color of the polygon annotation.

  ![Before applying polygon stroke color](Annotation-images\Polygon-Annotation-5.png)

The following image illustrates the change in the color of the polygon annotation.

  ![After applied polygon stroke color](Annotation-images\Polygon-Annotation-6.png)
  
##### Editing fill color of the annotation

The fill color of the selected polygon annotation will be displayed in the Fill Color row in the Appearance tab. Selecting the Fill Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the fill color to the polygon annotation.

The following image illustrates how to change the fill color of the polygon annotation.

  ![Before applying polygon fil color](Annotation-images\Polygon-Annotation-7.png)

The following image illustrates the change in the fill color of the included polygon annotation.

  ![After applied polygon fill color](Annotation-images\Polygon-Annotation-8.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected polygon annotation. You can also modify the opacity of the selected arrow shape by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the polygon annotation.

  ![Before applying polygon opacity](Annotation-images\Polygon-Annotation-9.png)

The following image illustrates the change in the opacity of the included polygon annotation.	

  ![After applied polygon opacity](Annotation-images\Polygon-Annotation-10.png)

##### Border Styles

PDF viewer allows the users to change the annotation border style. Currently it provides support for following border style. 

* Cloudy
* Solid

By default, annotation border style will be solid.

 N>For complex cloud polygons, the cloud border-style appearance might differ from other PDF readers like Adobe.

##### Changing the border style from UI

The border style of the selected polygon annotation will be displayed in the combo box control of the appearance tab. This combo box will allow us to modify the border style of the selected polygon shape.

The following image illustrates how to change the border style of the polygon annotation included.

![WPF PDFViewer Before applying polygon border style](Annotation-images\WPF-PDFViewer-Before-applying-polygon-border-style.png)

The following image illustrates the change of border style in the selected polygon annotation.

![WPF PDFViewer After applying polygon border style](Annotation-images\WPF-PDFViewer-After-applying-polygon-border-style.png)

##### Changing the border style programmatically

The polygon annotation can be customized at the time of inclusion. The following code shows how to set the default border style of the included polygon annotation by using the BorderEffect property.

{% tabs %}
{% highlight C# %}
private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfViewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Polygon;
    pdfViewer.PolygonAnnotationSettings.BorderEffect = BorderEffect.Cloudy;
}

{% endhighlight %}
{% endtabs %}

##### How to directly include cloud shape from toolbar

Using the default toolbar of PDF Viewer, you can directly enable the mode to add cloud shapes in PDF pages

The following image illustrates how to select the cloud shape from the toolbar.

![WPF PDFViewer Cloud shape option in toolbar](Annotation-images\WPF-PDFViewer-Cloud-shape-option-in-toolbar.png)

#### General tab

You can add/edit the default Author and Subject to the included polygon annotation using General tab of the Properties window.

The following image illustrates the change in Author and Subject of the polygon annotation.

  ![General Tab](Annotation-images\Polygon-Annotation-11.png)

#### Deleting an annotation

Select the delete option from the context menu, which will be displayed by right-clicking the selected annotation to delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

 ![Delete polygon annotation](Annotation-images\Polygon-Annotation-12.png)

## Polyline Annotation

PDF Viewer provides an option to include, edit, or remove the polyline annotation in a PDF document.

The following code shows how to switch to polyline annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Polyline;
}


{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Polyline
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the polyline annotation included in the PDF Document.

   ![polyline annotation](Annotation-images\Polyline-Annotation-1.png)

### How to set the stroke color of polyline annotation

The stroke color of the polyline annotation can be customized at the time of inclusion itself. The following code shows how to set default stroke color of the polyline annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolylineAnnotationSettings.StrokeColor = Colors.Blue;
}


{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolylineAnnotationSettings.StrokeColor = Colors.Blue
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the opacity of the polyline annotation

The opacity of the polyline annotation can be customized at the time of inclusion itself. The following code shows how to set default opacity value for the polyline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolylineAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolylineAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the thickness of the polyline annotation

The thickness of the polyline annotation can be customized at the time of inclusion itself. The following code shows how to set the default thickness of the included polyline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolylineAnnotationSettings.Thickness = 5;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolylineAnnotationSettings.Thickness = 5
End Sub

{% endhighlight %}
{% endtabs %}

### How to set the author and subject of the polyline annotation

The author and subject fields of the polyline annotation can be added at the time of inclusion itself. The following code shows how to set default author and subject of the polyline annotation in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.PolylineAnnotationSettings.Author = "Syncfusion Softwares";
    pdfviewer.PolylineAnnotationSettings.Subject = "Polygonal Line Annotation";
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.PolylineAnnotationSettings.Author = "Syncfusion Softwares"
    pdfviewer.PolylineAnnotationSettings.Subject = "Polygonal Line Annotation"    
End Sub

{% endhighlight %}
{% endtabs %}

### Working with existing polyline annotations

Polyline annotation supports adding notes along with it, also it allows editing its color, opacity and thickness. To use these options, select the existing polyline annotation and right-click using mouse, over the selected annotation, a pop up context menu will appear with the following options,

* Open Pop-up note
* Properties
* Delete

#### Open Pop-up notes

You can add notes to the polyline annotation by choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected polyline annotation. The added notes will be saved along with the PDF document and if there are any existing notes, it will be displayed here.

   ![polyline annotation](Annotation-images\Polyline-Annotation-2.png)

#### Properties

Selecting properties from the context menu will display the polyline properties window, which would consist of two tabs

* Appearance
* General 

#### Appearance tab

The color, opacity and thickness of the polyline annotation can be edited using Appearance tab of polyline properties window.

##### Editing the thickness of the polyline annotation

Modifying the value in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control in the Appearance tab of polyline annotation properties window will allow us to modify the thickness of the selected polyline annotation.

The following image illustrates how to change the thickness of the polyline annotation.

   ![polyline annotation](Annotation-images\Polyline-Annotation-3.png)

The following image illustrates the change in thickness of the selected polyline annotation.

   ![polyline annotation](Annotation-images\Polyline-Annotation-4.png)

##### Editing color of the annotation

The color of the selected polyline annotation will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette control, choosing a color from the color palette and clicking OK will apply the color to the polyline annotation.

The following image illustrates how to change the color of the polyline annotation included.

   ![polyline annotation](Annotation-images\Polyline-Annotation-5.png)

The following image illustrates the change in the color of the included polyline annotation.

   ![polyline annotation](Annotation-images\Polyline-Annotation-6.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab will allow us to modify the opacity of the selected polyline annotation. You can also modify the opacity of the selected polyline annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the included polyline annotation.

  ![polyline annotation](Annotation-images\Polyline-Annotation-7.png)

The following image illustrates the change in the opacity of the included polyline annotation.

   ![polyline annotation](Annotation-images\Polyline-Annotation-8.png)

#### General tab

We can add/edit the default Author and Subject to the included polyline annotation using General tab of the Polyline Properties window.

The following image illustrates the change in Author and Subject of the included polyline annotation.

  ![polyline annotation](Annotation-images\Polyline-Annotation-9.png)

#### Deleting an annotation

Select the delete option from the context menu, which will be displayed by right-clicking the selected annotation to delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

  ![polyline annotation](Annotation-images\Polyline-Annotation-11.png)

## Events

The PdfViewerControl notifies through events, when [AnnotationChangedAction](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedAction.html) such us adding, deleting, select, deselect, moving and resizing made in annotations. It also provides the annotations common information such as annotation name, page index, bounds and action type performed in respective annotation. 

### ShapeAnnotationChanged Event

The [ShapeAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShapeAnnotationChanged) event occurs when the [Action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Action) performed in shape annotation. It provides the common information, [Type](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.ShapeAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_ShapeAnnotationChangedEventArgs_Type) and its annotation properties which are available in [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.ShapeAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_ShapeAnnotationChangedEventArgs_Settings) through the [ShapeAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.ShapeAnnotationChangedEventArgs.html). The user can modify the annotation properties through [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.ShapeAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_ShapeAnnotationChangedEventArgs_Settings).

The following code shows how to write the [ShapeAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShapeAnnotationChanged) event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight C# %}

private void PdfViewer_ShapeAnnotationChanged(object sender, ShapeAnnotationChangedEventArgs e)
{
	//COMMON PROPERTIES
	//AnnotationChangedAction to identify action performed for annotation 
	AnnotationChangedAction action = e.Action;

	//To identify which type shape annotation
	ShapeAnnotationType annotationType = e.Type;

	//Page index in which this shape annotation was modified 
	int pageNumber = e.PageNumber;

	//Get Shape annotation's position and size 
	System.Drawing.PointF position = e.NewBounds.Location;
	System.Drawing.SizeF size = e.NewBounds.Size;

	//For Polygon and Polyline annotations collection of points   
	ReadOnlyCollection<System.Windows.Point> points = e.Points;

	ShapeAnnotationSettings settings = e.Settings;

	//SHAPES PROPERTIES can be get/set. 
	string author = settings.Author;
	string subject = settings.Subject;
	string Text = settings.Text;
	float thickness = settings.Thickness;
	float opacity = settings.Opacity;
}

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.