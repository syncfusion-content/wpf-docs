---
layout: post
title: Working with annotations using WPF PDF Viewer | Syncfusion
description: Learn about Selecting and Modifying the annotation's properties programmatically using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Working with annotations programmatically
## Add an annotation

PDF Viewer allows users to add annotations programmatically without user interaction. Annotations can be added to the PDF document using the [PdfViewerControl’s loadedDocument](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_LoadedDocument) property from the code behind.

The following code snippet explains how to add an ink annotation at runtime to the PDF document.

{% tabs %}
{% highlight C# %}

//Adding ink annotation at runtime to the PDF document.
private void AddAnnotation()
{ 
    //Get the instance of the loadedDocument from the PdfViewerControl.
    PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;

    //Specify the ink points
    List<float> inkPoints = new List<float> { 40, 300, 60, 100, 40, 50, 40, 300 };
    //Specify the bounds of an annotation
    RectangleF rectangle = new RectangleF(0, 0, 300, 400);
    //Create a new ink annotation
    PdfInkAnnotation inkAnnotation = new PdfInkAnnotation(rectangle, inkPoints);

    //Add the ink annotation to the desired page of the PdfLoadedDocument property instance.
    loadedDocument.Pages[0].Annotations.Add(inkAnnotation);
}

{% endhighlight %}
{% highlight VB %}

'Adding ink annotation at runtime to the PDF document.
private void AddAnnotation()
{ 
    'Get the instance of the loadedDocument from the PdfViewerControl.
    Dim loadedDocument As PdfLoadedDocument = pdfViewer.LoadedDocument

    'Specify the ink points
    Dim inkPoints As List(Of Single) = New List(Of Single) From {40, 300, 60, 100, 40, 50, 40, 300}
    'Specify the bounds of an annotation
    Dim rectangle As RectangleF = New RectangleF(0, 0, 300, 400)
    'Create a new ink annotation
    Dim inkAnnotation As PdfInkAnnotation = New PdfInkAnnotation(rectangle, inkPoints)

    'Add the ink annotation to the desired page of the PdfLoadedDocument property instance.
    loadedDocument.Pages(0).Annotations.Add(inkAnnotation)
}
{% endhighlight %}
{% endtabs %}

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

## Modify an annotation
PDF Viewer allows users to modify annotations programmatically without user interaction with the below ways.

### Modify an annotation using annotation changed event settings 
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

### Modify an annotation using loadedDocument

Annotations can be modified to the PDF document using the [PdfViewerControl’s loadedDocument](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_LoadedDocument) property from the code behind.

The following code snippet explains how to modify an ink annotation at runtime to the PDF document.

{% tabs %}
{% highlight C# %}

//Modify ink annotation at runtime to the PDF document.
private void ModifyAnnotation()
{ 
    //Get the instance of the loadedDocument from the PdfViewerControl.
    PdfLoadedDocument loadedDocument = pdfViewer.LoadedDocument;
    //Check whether the annotation in PdfInkAnnotation
    if(loadedDocument.Pages[0].Annotations[0] is PdfInkAnnotation)
    {
        PdfInkAnnotation inkAnnotation = loadedDocument.Pages[0].Annotations[0] as PdfInkAnnotation;
        //Modify the color of the ink annotation 
        inkAnnotation.Color = new PdfColor(System.Drawing.Color.Blue);
    }
}

{% endhighlight %}
{% highlight VB %}

'Modify ink annotation at runtime to the PDF document.
private void ModifyAnnotation()
{ 
    'Get the instance of the loadedDocument from the PdfViewerControl.
    Dim loadedDocument As PdfLoadedDocument = pdfViewer.LoadedDocument
    Dim inkAnnotation As PdfInkAnnotation = Nothing
    'Check whether the annotation in PdfInkAnnotation
    If TypeOf loadedDocument.Pages(0).Annotations(0) Is PdfInkAnnotation Then
        inkAnnotation = TryCast(loadedDocument.Pages(0).Annotations(0), PdfInkAnnotation)
        'Modify the color of the ink annotation 
        inkAnnotation.Color = New PdfColor(System.Drawing.Color.Blue)
    End If
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

## Delete all annotations  

The PDF Viewer enables users to programmatically remove all annotations from a document without requiring any user interaction. This option helps users to remove unwanted annotations from the document. 

### Delete all annotations in the PDF file

PDF Viewer allows the user to delete all annotations programmatically using the [ClearAllAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ClearAllAnnotations) method. 

The following code snippet explains how to delete all annotations. 

{% tabs %}
{% highlight C# %}

//delete all annotations
private void DeleteAnnotations()
{ 
   pdfViewer.ClearAllAnnotations(); 
} 

{% endhighlight %}
{% highlight VB %}

'delete all annotations
private void DeleteAnnotations()
{ 
   pdfViewer.ClearAllAnnotations()
} 

{% endhighlight %}
{% endtabs %}

### Delete all annotations at specific page  

PDF Viewer also allows the user to delete all annotations from a specific page programmatically using the overload [ClearAllAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ClearAllAnnotations_System_Int32_) method with a specified page number on which the annotations are located. The page number which we pass as a parameter, its annotations get deleted.

The following code snippet explains how to delete all annotations on the first page of the PDF document. 

{% tabs %}
{% highlight C# %}

//Delete all annotations from page 1
private void DeleteAnnotation() 
{ 
    pdfViewer.ClearAllAnnotations(1); 
} 

{% endhighlight %}
{% highlight VB %}

'delete all annotations from page 1
private void DeleteAnnotations()
{ 
   pdfViewer.ClearAllAnnotations(1)
} 

{% endhighlight %}
{% endtabs %}

## Update the annotation's modified date

PDF Viewer allows the user to update the [ModifiedDate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationSettings.html#Syncfusion_Windows_PdfViewer_AnnotationSettings_ModifiedDate) of an annotation programmatically without user interaction. With this feature, users can alter the modified date and time according to their preferences.

### How to update the modified date of an annotation using default annotation settings?

User can include a [ModifiedDate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationSettings.html#Syncfusion_Windows_PdfViewer_AnnotationSettings_ModifiedDate) field when adding an annotation to a PDF document using default annotation settings.

The following code snippet explains how to set the modified date field of an ink annotation to be included. Similarly, we can implement it for all other annotations.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    pdfviewer.Load("Input.pdf");
    pdfviewer.InkAnnotationSettings.ModifiedDate = new DateTime(2020, 12, 1, 1, 1, 1);
}

{% endhighlight %}
{% highlight VB %}

private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
{
    pdfviewer.Load("Input.pdf")
    pdfviewer.InkAnnotationSettings.ModifiedDate = new DateTime(2020, 12, 1, 1, 1, 1)
}

{% endhighlight %}
{% endtabs %}

### How to update the modified date of an annotation using annotation changed event settings?

User can include a [ModifiedDate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationSettings.html#Syncfusion_Windows_PdfViewer_AnnotationSettings_ModifiedDate) field of an annotation to a PDF document using annotation changed event settings.

The following code snippet explains how to set the modified date field of an ink annotation using ink annotation changed event settings. Similarly, we can implement it for all other annotations.

{% tabs %}
{% highlight C# %}

private void PdfViewer_InkAnnotationChanged(object sender, InkAnnotationChangedEventArgs e)
{
    e.Settings.ModifiedDate = new DateTime(2023, 12, 1, 1, 1, 1);
}

{% endhighlight %}
{% highlight VB %}

private Sub PdfViewer_InkAnnotationChanged(sender As Object, e As InkAnnotationChangedEventArgs)
{
    e.Settings.ModifiedDate = new DateTime(2023, 12, 1, 1, 1, 1)
}

{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.