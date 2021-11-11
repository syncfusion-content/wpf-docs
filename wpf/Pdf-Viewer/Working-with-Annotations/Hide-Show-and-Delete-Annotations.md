---
layout: post
title: Hide, Show and Delete annotations using WPF PDF Viewer | Syncfusion
description: Learn about hide, show and Delete the annotation programmatically using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Hide, Show and Delete annotations programmatically 

## Hide an annotation

PDF Viewer allows the user to hide the annotation programmatically without user interaction. This functionality returns true if any annotation is found and hidden, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer to the following link to get and set an annotation name: https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation   

N> If there are multiple annotations with the same name in the document, it will hide the first one.

### Hide an annotation in the PDF file

PDF Viewer allows the user to hide an annotation programmatically using the HideAnnotation method. The annotation name should be passed as a parameter to hide the annotation. 

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

Similarly, we can implement it for all other annotations.

### Hide an annotation at specific page

PDF Viewer also allows the user to hide the annotation from a specific page programmatically using the overload HideAnnotation method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be hidden. 

N> For better performance, we can use the method HideAnnotation with page number overload.

The following code snippet explains how to hide an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Hide ink annotation with the annotation’s name and page number  

private void HideAnnotation() { bool isHidden = pdfViewer.HideAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.

## Show an annotation 

PDF Viewer allows the user to show the hidden annotation programmatically without user interaction. This functionality returns true if any annotation is found and shown, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer to the following link to get and set an annotation name: https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation   

N> If there are multiple annotations with the same name in the document, it will show the first one. 

### Show an annotation in the PDF file 

PDF Viewer allows the user to show an annotation programmatically that was hidden using the ShowAnnotation method. The annotation name should be passed as a parameter to show the annotation. 

The following code snippet explains how to show a hidden ink annotation using the annotation name. 

{% tabs %}
{% highlight C# %}

//Show ink annotation using annotation’s name 

private void ShowAnnotation() 
{ 
   bool isShowed =  pdfViewer.ShowAnnotation(inkAnnotationName); 
} 

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.

### Show an annotation at specific page  

PDF Viewer also allows the user to show the annotation from a specific page programmatically using the overload ShowAnnotation method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be shown.  

N> For better performance, we can use the method ShowAnnotation with page number overload.

The following code snippet explains how to show an ink annotation on the first page of the document using the annotation name.

{% tabs %}
{% highlight C# %}

//Show ink annotation with the annotation’s name and page number  

private void ShowAnnotation() { bool isShowed = pdfViewer.ShowAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.

## Delete an annotation  

PDF Viewer allows the user to delete an annotation programmatically without user interaction. This functionality returns true if any annotation is found and deleted, otherwise it returns false. The annotation [Name](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotationChangedEventArgs.html#Syncfusion_Windows_PdfViewer_AnnotationChangedEventArgs_Name) property is used to identify the annotation. Refer to the following link to get and set an annotation name: https://help.syncfusion.com/wpf/pdf-viewer/working-with-annotations/select-and-modify-annotations#how-to-get-and-set-name-of-an-annotation   

N> If there are multiple annotations with the same name in the document, it will delete the first one.

### Delete an annotation in the PDF file

PDF Viewer allows the user to delete an annotation programmatically using the DeleteAnnotation method. The annotation name should be passed as a parameter to delete the annotation. 

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

Similarly, we can implement it for all other annotations.

### Delete an annotation at specific page  

PDF Viewer also allows the user to delete the annotation from a specific page programmatically using the overload DeleteAnnotation method with a specified page number on which the annotation is located. The annotation name and its page number should be passed as a parameter that needs to be deleted. 

N> For better performance, we can use the method DeleteAnnotation with page number overload.

The following code snippet explains how to delete an ink annotation on the first page of the document using the annotation name. 

{% tabs %}
{% highlight C# %}

//Delete ink annotation with the annotation’s name and page number  

private void DeleteAnnotation() { bool isDeleted = pdfViewer.DeleteAnnotation(inkAnnotationName, 1); } 

{% endhighlight %}
{% endtabs %}

Similarly, we can implement it for all other annotations.