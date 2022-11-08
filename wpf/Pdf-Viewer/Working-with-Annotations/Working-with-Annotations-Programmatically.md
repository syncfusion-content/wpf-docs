---
layout: post
title: Working with annotations using WPF PDF Viewer | Syncfusion
description: Learn about Selecting and Modifying the annotation's properties programmatically using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Working with annotations programmatically

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

N> Similarly, we can implement it for all other annotations.

### Select an annotations at specific page

PDF Viewer also allows the users to select the annotation programmatically using overload [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Int32_) method with specified the page number on which the annotation is located. The annotation’s name and its page number should pass as a parameter that needs to be selected. 

N> For better performance, we can use the method [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Int32_) with page number overload.

The following code snippet explains how to select an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation from page 1 with the annotation’s name
private void SelectAnnotation()
{ 
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName, 1);
}

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

### Select an annotation in the PDF file and bring it into view

PDF Viewer also allows the user to select and bring an annotation to view programmatically using overload [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Boolean_) method with `BringIntoView` Parameter. The annotation’s name and true value for `BringIntoView` should be passed as a parameter to select and bring an annotation into view. 

The following code snippet explains how to select an ink annotation using the annotation name and bring them into view.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation with the annotation’s name and bring them into view 
private void SelectAnnotation() 
{
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName, true); 
} 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations. 

### Select an annotation at specific page and bring it into view 

PDF Viewer also allows the user to select the annotation programmatically and bring it into view using overload [SelectAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SelectAnnotation_System_String_System_Int32_System_Boolean_) method, specifying the page number on which the annotation is located. The annotation’s name, its page number and its “true” value for `BringIntoView` should be passed as a parameter that needs to be selected. 

The following code snippet explains how to select an ink annotation on the first page of the document using the annotation name and bring it into view.

{% tabs %}
{% highlight C# %}

//Selecting ink annotation from page 1 with the annotation’s name and bringing into view parameter 

private void SelectAnnotation() 
{  
    bool isSelected = pdfViewer.SelectAnnotation(inkAnnotationName, 1, true);
} 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations. 

N> To bring an annotation into view we need to pass a “true” value for the BringIntoView parameter, providing a “false” value will only select the annotation.

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

## Add an annotation

PDF Viewer allows the users to add the annotation programmatically without user interaction. After adding the annotation, user can change the annotation’s properties programmatically.

The following code snippet explains how to add the ink annotation and modify the ink annotation’s properties. Similarly, we can implement for all other annotations.

{% tabs %}
{% highlight C# %}

private void AddInk (object sender, RoutedEventArgs e)
{
	PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;
	PdfLoadedPage page = loadedDocument.Pages[0] as PdfLoadedPage;
	List<float> inkList = new List<float> { 40, 200, 60, 100, 40, 50, 40, 200, 30, 40 };
	PdfInkAnnotation inkAnnotation = new PdfInkAnnotation(new RectangleF(28, 215, 34, 190), inkList);
	page.Annotations.Add(inkAnnotation);
	inkAnnotation.Color = new PdfColor(System.Drawing.Color.Blue);
	inkAnnotation.Opacity = .7f;
	inkAnnotation.BorderWidth = 6;
}

{% endhighlight %}
{% endtabs %}

## Remove an annotation

PDF Viewer allows the users to remove the annotation programmatically without user interaction.

{% tabs %}
{% highlight C# %}

private void RemoveAt (object sender, RoutedEventArgs e)
{
	PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;
	PdfLoadedPage page = loadedDocument.Pages[0] as PdfLoadedPage;
	if (page.Annotations.Count > 0)
		page.Annotations.RemoveAt(0);
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

## Hide an annotation

PDF Viewer allows the user to hide the annotation programmatically without user interaction. This functionality returns true if any annotation is found and hidden, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer this [UG link](https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation) to get and set an annotation Name property. 

N> If there are multiple annotations with the same name in the document, it will hide the first one.

### Hide an annotation in the PDF file

PDF Viewer allows the user to hide an annotation programmatically using the [HideAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_HideAnnotation_System_String_) method. The annotation name should be passed as a parameter to hide the annotation. 

The following code snippet explains how to hide an ink annotation using the annotation name. 

{% tabs %}
{% highlight C# %}

//Hide ink annotation using annotation’s name 

private void HideAnnotation() 
{ 
   bool isHidden =  pdfViewer.HideAnnotation(inkAnnotationName); 
} 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

### Hide an annotation at specific page

PDF Viewer also allows the user to hide the annotation from a specific page programmatically using the overload [HideAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_HideAnnotation_System_String_System_Int32_) method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be hidden. 

N> For better performance, we can use the method [HideAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_HideAnnotation_System_String_System_Int32_) with page number overload.

The following code snippet explains how to hide an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Hide ink annotation from page 1 with the annotation’s name 

private void HideAnnotation() { bool isHidden = pdfViewer.HideAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

## Show an annotation 

PDF Viewer allows the user to show the hidden annotation programmatically without user interaction. This functionality returns true if any annotation is found and shown, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer this [UG link](https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation) to get and set an annotation Name property.   

N> If there are multiple annotations with the same name in the document, it will show the first one. 

### Show an annotation in the PDF file 

PDF Viewer allows the user to show an annotation programmatically that was hidden using the [ShowAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowAnnotation_System_String_) method. The annotation name should be passed as a parameter to show the annotation. 

The following code snippet explains how to show a hidden ink annotation using the annotation name. 

{% tabs %}
{% highlight C# %}

//Show ink annotation using annotation’s name 

private void ShowAnnotation() 
{ 
   bool isShown =  pdfViewer.ShowAnnotation(inkAnnotationName); 
} 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

### Show an annotation at specific page  

PDF Viewer also allows the user to show the annotation from a specific page programmatically using the overload [ShowAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowAnnotation_System_String_System_Int32_) method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be shown.  

N> For better performance, we can use the method [ShowAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ShowAnnotation_System_String_System_Int32_) with page number overload.

The following code snippet explains how to show an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Show ink annotation from page 1 with the annotation’s name 

private void ShowAnnotation() { bool isShown = pdfViewer.ShowAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

## Delete an annotation  

PDF Viewer allows the user to delete an annotation programmatically without user interaction. This functionality returns true if any annotation is found and deleted, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer this [UG link](https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation) to get and set an annotation Name property.    

N> If there are multiple annotations with the same name in the document, it will delete the first one.

### Delete an annotation in the PDF file

PDF Viewer allows the user to delete an annotation programmatically using the [DeleteAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DeleteAnnotation_System_String_) method. The annotation name should be passed as a parameter to delete the annotation. 

The following code snippet explains how to delete an ink annotation using the annotation name. 

{% tabs %}
{% highlight C# %}

//delete ink annotation using annotation’s name 

private void DeleteAnnotation()
{ 
   bool isDeleted =  pdfViewer.DeleteAnnotation(inkAnnotationName); 
} 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

### Delete an annotation at specific page  

PDF Viewer also allows the user to delete the annotation from a specific page programmatically using the overload [DeleteAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DeleteAnnotation_System_String_System_Int32_) method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be deleted. 

N> For better performance, we can use the method [DeleteAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DeleteAnnotation_System_String_System_Int32_) with page number overload.

The following code snippet explains how to delete an ink annotation on the first page of the document using the annotation name. 

{% tabs %}
{% highlight C# %}

//Delete ink annotation from page 1 with the annotation’s name
private void DeleteAnnotation() { bool isDeleted = pdfViewer.DeleteAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

N> Similarly, we can implement it for all other annotations.

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.