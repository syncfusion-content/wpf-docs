---
layout: post
title: Text Callout Annotation in WPF Pdf Viewer control | Syncfusion&reg;
description: Learn about Text Annotation support in Syncfusion&reg; Essential Studio&reg; WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---
# Free Text Callout Annotation in WPF Pdf Viewer

The free text callout annotation support in PDF viewer allows you to include text anywhere in the PDF document pages through a text box with an arrow line. You can also edit, modify, delete, and load existing free text callout annotations. The callout annotation can help you provide suggestions or feedback that can point to a specific spot on the page with an arrow.

## How to include the free text callout annotation

### Step 1: Set AnnotationMode to FreeText Callout
The following code shows how to switch to free text callout annotation mode in code behind.  

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf")
    pdfviewer.Load(pdf);   
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.FreeText;
    pdfViewer.FreeTextAnnotationSettings.Intent = Syncfusion.Pdf.Interactive.PdfAnnotationIntent.FreeTextCallout;
}
{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)  
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.FreeText
    pdfViewer.FreeTextAnnotationSettings.Intent = Syncfusion.Pdf.Interactive.PdfAnnotationIntent.FreeTextCallout
End Sub

{% endhighlight %}
{% endtabs %}

### Step 2: Click and Drag anywhere on the page

A callout text box will be prompted when tapping, clicking, dragging on the page, or requesting text data. Enter the text for free text callout annotation on that text box.
The following image shows the free text callout annotation being included in the PDF document.

![FreeText Callout Annotation](Annotation-images\FreeTextCallout-Annotation_1.png)

## Modifying the color of the free text callout annotation

The color of the free text callout annotation can be customized at the time of inclusion or after the inclusion. The following code shows how to set the color of the text annotation at the time of inclusion. The customization of color after inclusion is explained later in this guide.

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
## Modifying the end style of the free text callout annotation

The ending style of the free text callout annotation can be customized at the time of inclusion or after the inclusion. The following code shows how to set the end style of the text annotation at the time of inclusion. The customization of the end style after inclusion is explained later in this guide.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    // To set the background end style of free text callout annotation
    pdfViewer.AnnotationMode = Syncfusion.Windows.PdfViewer.PdfDocumentView.PdfViewerAnnotationMode.FreeText;
    pdfViewer.FreeTextAnnotationSettings.Intent = Syncfusion.Pdf.Interactive.PdfAnnotationIntent.FreeTextCallout;
    pdfViewer.FreeTextAnnotationSettings.CalloutLineEndingStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.Diamond;
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    // To set the background end style of free text callout annotation
    pdfViewer.AnnotationMode = Syncfusion.Windows.PdfViewer.PdfDocumentView.PdfViewerAnnotationMode.FreeText;
    pdfViewer.FreeTextAnnotationSettings.Intent = Syncfusion.Pdf.Interactive.PdfAnnotationIntent.FreeTextCallout;
    pdfViewer.FreeTextAnnotationSettings.CalloutLineEndingStyle = Syncfusion.Pdf.Interactive.PdfLineEndingStyle.Diamond;
End Sub

{% endhighlight %}
{% endtabs %}

## Setting the opacity of the free text callout annotation

The opacity of the free text callout annotation can be customized either at the time of inclusion or after the inclusion. The following code shows how to set the opacity value of the free text callout annotation at the time of inclusion. The customization of opacity after inclusion is explained later part in this guide.

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

## Setting the font size of the free text callout annotation

The font size of the free text callout annotation can be customized either at the time of inclusion or after the inclusion. The following code shows how to set the font size of the free text callout annotation to be included. The customization of font size after inclusion is explained later in this guide.

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

## Working with included/existing free text callout annotations

The included/existing free text callout annotations are moved, resized, edited, customized, and deleted. To perform these operations, select the included/existing free text callout annotation and right-click the selected annotation, and a pop-up context menu will appear with the following options:
       
* Properties
* Delete 

### Properties

Selecting properties from the context menu will display the Text Properties window, which consist of two tabs:

* Appearance
* General

#### Appearance tab

The border color, background color, border thickness, opacity, and ending style of the free text callout annotation can be edited using the Appearance tab in the Free text callout Properties window.
##### Editing end style of the free text callout annotation

To modify the selected free text callout annotation's end style, modify the ComboBox control's value in the Appearance tab of the free text callout annotation properties.
The following image illustrates how to change the end style of the free text callout annotation.  

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_12.png)

##### Editing border thickness of the free text callout annotation

To modify the selected free text callout annotation thickness, modify the value of the NumericUpDown control in the Appearance tab of the free text callout annotation properties.
The following image illustrates how to change the border thickness of the free text callout annotation.  

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_2.png)

##### Editing border color of the annotation

The border color of the selected free text callout annotation will be displayed in the border color row in the Appearance tab. Selecting the color will display the color palette control. Choosing a color from the color palette and clicking OK will apply the color to the text annotation.
The following image illustrates how to change the border color of the free text callout annotation included.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_3.png)

##### Editing background color of the text

Similarly, you can modify the background color of the text.

The following image illustrates how to change the background color of the free text callout annotation included.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_4.png)

##### Editing opacity of the annotation

The slider control displayed in the Appearance tab allows modifying the opacity of the selected free text callout annotation. You can modify the opacity by giving numeric values in the opacity text box.

The following image illustrates how to change the opacity of the free text callout annotation.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_5.png)

The following screenshot illustrates the completely customized text annotation included in a PDF page.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_6.png)

#### General tab

You can add or edit the Author and Subject of the free text callout annotation using the General tab of the Text Callout Properties window.

The following image illustrates the change in Author and Subject of the included text callout annotation.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_7.png)

#### Editing font properties

Font properties such as size and color are modified using the font properties dialog displayed in the text editing mode.

N> Double clicking the text box will enable the text editing mode.

The following image illustrates how to change the font size of the text.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_8.png)

The following image illustrates how to change the font color of the text.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_9.png)

The following image illustrates the change in font color and font size of the text callout annotation.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_10.png)

### Deleting an annotation

Selecting the delete option from the context menu displayed by right-clicking the selected annotation will delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![Text Callout Annotation](Annotation-images\FreeTextCallout-Annotation_11.png)

## Events

The PdfViewerControl notifies through events when `AnnotationChangedAction` such as adding, deleting, selecting, deselecting, moving, and resizing made in annotations. It also provides the annotation’s common information such as annotation name, page index, bounds, and action type performed in the respective annotation. 

### FreeTextAnnotationChanged Event

The [FreeTextAnnotationChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_FreeTextAnnotationChanged) event occurs when the [Action](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Action)  is performed in free text annotation. It provides the common information and annotation properties available in `Settings` through the [FreeTextAnnotationChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FreeTextAnnotationChangedEventArgs.html). The user can modify the annotation properties through [Settings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FreeTextAnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_FreeTextAnnotationChangedEventArgs_Settings).

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
    System.Collections.ObjectModel.ReadOnlyCollection<System.Windows.Point> calloutPoints;
    //Annotation's previous position, current position and callout points
    RectangleF currentBound = e.NewBounds;
    RectangleF previousBound = e.OldBounds;
    calloutPoints = e.CalloutPoints;
    PdfViewerFreeTextSettings settings = e.Settings;
    //Annotation's properties which can be modify 
    PdfAnnotationIntent calloutIntent = settings.Intent;
    PdfLineEndingStyle calloutEndStyle = settings.CalloutLineEndingStyle;
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


N> For its groundbreaking feature representations, you can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer)  feature tour page. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to learn how to render and configure the pdfviewer.