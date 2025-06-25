---
layout: post
title: Text Annotation in WPF Pdf Viewer control | Syncfusion&reg;
description: Learn about Text Annotation support in Syncfusion&reg; Essential Studio&reg; WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---
# Text Annotation in WPF Pdf Viewer

The text annotation support in PDF viewer allows you to include text anywhere in the PDF document pages through a text box. You can also edit, modify, delete, and load existing text annotations. 

## How to include the text annotation

### Step 1: Set AnnotationMode to FreeText
The following code shows how to switch to text annotation mode in code behind.  

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf);   
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.FreeText;
}
{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)  
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.FreeText
End Sub

{% endhighlight %}
{% endtabs %}

### Step 2: Tap anywhere on the page

A text box will be prompted when tapping on the page or requesting text data. Enter the text for text annotation on that text box. 

The following image shows the text annotation being included in the PDF document. 

![FreeText Annotation](Annotation-images\FreeText-Annotation_1.png)

## Modifying the color of the text annotation

The color of the text annotation included can be either customized at the time of inclusion or after the inclusion. The following code shows how to set color of the text annotation at the time of inclusion. The customization of color after inclusion is explained in the later part.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    // To set the background color of text annotation
    pdfviewer.FreeTextAnnotationSettings.Background = Colors.White;
    // To set the background color of text annotation
    pdfviewer.FreeTextAnnotationSettings.BorderColor = Colors.Blue;
    // To set the background color of text annotation
    pdfviewer.FreeTextAnnotationSettings.FontColor = Colors.Black;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    'To set the background color of text annotation
    pdfviewer.FreeTextAnnotationSettings.Background = Colors.White
    'To set the background color of text annotation
    pdfviewer.FreeTextAnnotationSettings.BorderColor = Colors.Blue
    'To set the font color
    pdfviewer.FreeTextAnnotationSettings.FontColor = Colors.Black
End Sub

{% endhighlight %}
{% endtabs %}

## Setting the opacity of the text annotation

The opacity of the text annotation can be customized either at the time of inclusion or after the inclusion. The following code shows how to set opacity value of the text annotation at the time of inclusion. The customization of opacity after inclusion is explained in the later part.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.FreeTextAnnotationSettings.Opacity = 0.5f;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.FreeTextAnnotationSettings.Opacity = 0.5f
End Sub

{% endhighlight %}
{% endtabs %}

## Setting the font size of the text annotation

The font size of the text annotation can be customized either at the time of inclusion or after the inclusion. The following code shows how to set font size of the text annotation to be included. The customization of font size after inclusion is explained in the later part.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
  	pdfviewer.FreeTextAnnotationSettings.FontSize = 16;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.FreeTextAnnotationSettings.FontSize = 16
End Sub

{% endhighlight %}
{% endtabs %}

## Setting the font family of the text annotation

The font family of the text annotation can be customized either at the time of inclusion or after the inclusion. The following code shows how to set the font family of the text annotation at the time of inclusion.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.FreeTextAnnotationSettings.FontFamily = new System.Windows.Media.FontFamily("font family");
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.FreeTextAnnotationSettings.FontFamily = new System.Windows.Media.FontFamily("font family")
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing text annotations

The included/existing text annotations are moved, resized, edited, customized, and deleted. To perform these operations, select the included/existing text annotation and right-click over the selected annotation, a pop-up context menu will appear with the following options:
       
* Properties
* Delete 

### Properties

Selecting properties from the context menu will display the Text Properties window, which consist of two tabs:

* Appearance
* General

#### Appearance tab

The border color, background color, border thickness,and opacity of the text annotation can be edited using Appearance tab in the Text Properties window.

##### Editing border thickness of the text annotation

To modify the thickness of the selected text annotation, modify the value of the NumericUpDown control in the Appearance tab of text annotation properties. 

The following image illustrates how to change the border thickness of the text annotation.  

![Text Annotation](Annotation-images\FreeText-Annotation_2.png)

##### Editing border color of the annotation

The border color of the selected text annotation will be displayed in the border color row in the Appearance tab. Selecting the color will display the color palette control. Choosing a color from the color palette and clicking OK will apply the color to the text annotation.

The following image illustrates how to change the border color of the text annotation included.

![Text Annotation](Annotation-images\FreeText-Annotation_3.png)

##### Editing background color of the text

Similarly, you can modify the background color of the text.

The following image illustrates how to change the background color of the text annotation included.

![Text Annotation](Annotation-images\FreeText-Annotation_4.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab allows modifying the opacity of the selected text annotation. You can also modify the opacity by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the text annotation.

![Text Annotation](Annotation-images\FreeText-Annotation_5.png)

The following screenshot illustrates the completely customized text annotation included in a PDF page.

![Text Annotation](Annotation-images\FreeText-Annotation_6.png)

#### General tab

You can add or edit the Author and Subject of the text annotation using General tab of the Text Properties window.

The following image illustrates the change in Author and Subject of the included text annotation.

![Text Annotation](Annotation-images\FreeText-Annotation_7.png)

#### Editing font properties

Font properties such as size and color are modified using font properties dialog that is displayed in the text editing mode.

N> Double clicking the text box will enable the text editing mode.

The following image illustrates how to change the font size of the text.

![Text Annotation](Annotation-images\FreeText-Annotation_8.png)

The following image illustrates how to change the font color of the text.

![Text Annotation](Annotation-images\FreeText-Annotation_9.png)

The following image illustrates the change in font color and font size of the text annotation.

![Text Annotation](Annotation-images\FreeText-Annotation_10.png)

### Deleting an annotation

Selecting the delete option from the context menu that is displayed by right-clicking the selected annotation will delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![Text Annotation](Annotation-images\FreeText-Annotation_11.png)

## Events

The PdfViewerControl notifies through events, when `AnnotationChangedAction` such us adding, deleting, select, deselect, moving and resizing made in annotations. It also provides the annotations common information such as annotation name, page index, bounds and action type performed in respective annotation. 

### FreeTextAnnotationChanged Event

The [FreeTextAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_FreeTextAnnotationChanged) event occurs when the [Action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Action) performed in free text annotation. It provides the common information and annotation properties which are available in `Settings` through the [FreeTextAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FreeTextAnnotationChangedEventArgs.html). The user can modify the annotation properties through [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FreeTextAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_FreeTextAnnotationChangedEventArgs_Settings).

The following code shows how to write the FreeTextAnnotationChanged event in PdfViewerControl

{% tabs %}
{% highlight C# %}

private void PdfViewer_FreeTextAnnotationChanged(object sender, FreeTextAnnotationChangedEventArgs e)
{
    //COMMON PROPERTIES
    //AnnotationChangedAction to identify action performed for annotation 
    AnnotationChangedAction action = e.Action;
    //Page index in which this shape annotation was modified 
    int pageNumber = e.PageNumber;
    //Annotation's previous position and current position 
    RectangleF currentBound = e.NewBounds;
    RectangleF previousBound = e.NewBounds;
    PdfViewerFreeTextSettings settings = e.Settings;
    //Annotation's properties which can be modify 
    string author = settings.Author;
    string subject = settings.Subject;
    string Text = settings.Text;
    float opacity = settings.Opacity;
    double height = settings.Height;
    double width = settings.Width;
    System.Windows.Media.Color backgroundColor = settings.Background;
    System.Windows.Media.Color borderColor = settings.BorderColor;
    float thickness = settings.BorderThickness;
    System.Windows.Media.Color fontColor = settings.FontColor;
    System.Windows.Media.FontFamily fontFamily = settings.FontFamily;
    int size = settings.FontSize;
}

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.