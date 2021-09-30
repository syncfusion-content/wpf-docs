---
layout: post
title: Select and Modify annotations using WPF PDF Viewer | Syncfusion
description: Learn about Selecting and Modifying the annotation's properties programmatically using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Select and Modify annotations programmatically

## Select an annotation

PDF Viewer allows the users to select the annotation programmatically without user interaction. This functionality returns true, if any annotation is found to be selected. Otherwise, it returns false.

### Select an annotation in the PDF file

PDF Viewer allows the users to select the annotation programmatically using [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_) method. The annotation’s name should pass as a parameter that needs to be selected.  

The following code snippet explains how to select an ink annotation using the annotation name.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation with annotation’s name 
private void SelectAnnotation()
{ 
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName);
}

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.

### Select an annotations at specific page

PDF Viewer also allows the users to select the annotation programmatically using overload [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Int32_) method with specified the page number on which the annotation is located. The annotation’s name and its page number should pass as a parameter that needs to be selected. 

N> For better performance, we can use the method [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Int32_) with page number overload.

The following code snippet explains how to select an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation with annotation’s name and page number
private void SelectAnnotation()
{ 
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName, 1);
}

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.

### How to get and set name of an annotation

Annotation’s name can be obtained either for newly added annotation or the annotation that already exist. Also, you can modify the [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property to give annotations a unique name. In the following sections, the ink annotation was explained brevity and similarly, you can get and set names for all other annotations.

####  Get and Set Annotations’ Name

The annotations’ name can be obtained from the annotation changed event. The following code sample explains how to get the annotations’ name when adding it to the document.

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

{% endhighlight %}
{% endtabs %}

You can also change the name of an annotation. The following code sample demonstrates how to change the name of an ink annotation. Similarly, you can implement it for all other annotations. 
{% tabs %}
{% highlight C# %}

//Set the annotation name 
private void PdfViewer_InkAnnotationChanged(object sender, InkAnnotationChangedEventArgs e) 
{  
   e.Name = ”YOUR OWN NAME”;     
} 

{% endhighlight %}
{% endtabs %}

N> The annotation name must be unique. If there are multiple annotations with the same name in the document, any functions based on the name will only affect the first one identified. 


#### Getting annotation’s name for existing annotation

The existing annotation’s name can be obtained from [LoadedDocument]( https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_LoadedDocument). The following code snippet explains how to get the existing annotation’s name. 

{% tabs %}
{% highlight C# %}
//Getting existing annotation’s name
private void PdfViewer_DocumentLoaded(object sender, EventArgs args)
{
     PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;
     PdfPageBase page = loadedDocument.Pages[0];
     string annotationName = page.Annotations[0].Name;
}

{% endhighlight %}
{% endtabs %}

## Modify an annotation

Annotation’s properties can be modified programmatically through `Settings` in respective annotation changed event. 

The following code snippet explains how to modify the selected ink annotation’s properties. Similarly, we can implement for all other annotations.

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


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.