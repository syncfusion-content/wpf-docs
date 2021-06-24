---
layout: post
title: Select and Modify annotations programmatically in WPF Pdf Viewer control | Syncfusion
description: Learn about Select and Modify annotations programmatically support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

#Select and Modify annotations programmatically.

##Select an annotation.

PDF Viewer allows the users to select the annotation programmatically using SelectAnnotation method. The annotation’s name should pass as a parameter which needs to be selected. This method returns true, if any annotation is found to be selected. Otherwise, it returns false. 

N> For better performance, we can use the method `SelectAnnotation` with page number overload.

The following code snippet explains how to select ink annotation and similarly we can implement for all other annotation.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation with annotation’s name and page number
private void SelectAnnotation(object sender, RoutedEventArgs e)
{ 
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName, 1);
}

//Selecting ink annotation with annotation’s name 
private void SelectAnnotation1(object sender, RoutedEventArgs e)
{ 
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName);
}

{% endhighlight %}
{% endtabs %}

### How to obtain the name of an annotation.

Annotation’s name can be obtained either from respective annotation changed event while adding the annotation in the document or from `LoadedDocument` where the annotation was already exist.

The following code snippet explains how to get ink annotation’s name in both. Similarly, we can implement for all other annotation.

{% tabs %}
{% highlight C# %}

//Getting annotation’s name while adding the annotation
private void PdfViewer_InkAnnotationChanged(object sender, InkAnnotationChangedEventArgs e)
{
    if (e.Action == AnnotationChangedAction.Add)
    {
        string inkAnnotationName = e.Name;
    }
}

//Getting existing annotation’s name
private void PdfViewer_DocumentLoaded(object sender, EventArgs args)
{
     PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;
     PdfPageBase page = loadedDocument.Pages[0];
     string annotationName = page.Annotations[0].Name;
}

{% endhighlight %}
{% endtabs %}

## Modify an annotation.

Annotation’s properties can be modified programmatically through `Settings` in respective annotation changed event. 

The following code snippet explains how to modify the selected ink annotation’s properties. we can implement for all other annotation.

{% tabs %}
{% highlight C# %}

//Modifying the selected annotation’s properties.
private void PdfViewer_InkAnnotationChanged(object sender, InkAnnotationChangedEventArgs e)
{
    if (e.Action == AnnotationChangedAction.Select)
    {
		PdfViewerInkSettings pdfViewerInkSettings = (e.Settings as PdfViewerInkSettings);
		pdfViewerInkSettings.InkColor = System.Windows.Media.Color.FromArgb(255, 0, 0, 255);
		pdfViewerInkSettings.Opacity = 1f;
		pdfViewerInkSettings.Thickness = 5;
    }
}

{% endhighlight %}
{% endtabs %}
