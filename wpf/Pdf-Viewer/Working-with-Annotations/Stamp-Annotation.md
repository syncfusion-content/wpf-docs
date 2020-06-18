---
layout: post
title: Stamp Annotation in PDF Viewer WPF | Syncfusion
description: PDF Viewer provides the ability to add, move, resize and deleting stamp annotation in PDF document. It also supports adding custom stamps as images.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Stamp annotation in PDF Viewer WPF

PDF viewer WPF allows the user to include stamp annotation in the PDF document and provides options to edit or remove the existing stamp annotation in the PDF document.

The following code shows how to switch to stamp annotation mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Stamp;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.Stamp
End Sub

{% endhighlight %}
{% endtabs %}

The following image shows the stamp annotation being included in the PDF Document.

 ![Stamp annotation](Annotation-images\Stamp-Annotation-1.png)

## How to set the opacity of the stamp annotation?

The opacity of the stamp annotation can be customized at the time of inclusion itself. The following code shows how to set opacity value of the stamp annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StampAnnotationSettings.Opacity = 0.5F;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
       pdfviewer.StampAnnotationSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the author and subject of the stamp annotation?

The author and subject fields of the stamp annotation can be added for the stamp annotation to be added to the PDF document. The follow code shows how to set the author and subject field of the stamp annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StampAnnotationSettings.Author = "Syncfusion Softwares"; 
    pdfviewer.StampAnnotationSettings.Subject = "Stamp annotation";
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StampAnnotationSettings.Author = "Syncfusion Softwares" 
    pdfviewer.StampAnnotationSettings.Subject = "Stamp annotation"
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the icon of the stamp annotation?

The icon of the stamp annotation can be customized at the time of inclusion itself. The following code shows how to set icon value of the stamp annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StampAnnotationSettings.Icon = Syncfusion.Pdf.Interactive.PdfRubberStampAnnotationIcon.NotApproved;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StampAnnotationSettings.Icon = Syncfusion.Pdf.Interactive.PdfRubberStampAnnotationIcon.NotApproved
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the text for popup note of the stamp annotation?

The text for popup note of the stamp annotation can be customized at the time of inclusion itself. The following code shows how to set text for popup note of the stamp annotation to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.StampAnnotationSettings.Text = “Syncfusion Software”;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.StampAnnotationSettings.Text = “Syncfusion Software”
End Sub

{% endhighlight %}
{% endtabs %}

## Working with included/existing stamp annotations

Stamp annotation supports adding notes along with it, also it allows editing its opacity. To use these options, select the included/existing stamp annotation and click right using mouse, over the selected annotation, a pop up context menu will appear with the following options,

*	Open Pop-up note
*	Properties
*	Delete

## Open Pop-up notes

We can add notes to the stamp annotation choosing Open Pop-up note option from the context menu. The following image illustrates the notes added to the selected stamp annotation. The added notes will be saved along with the PDF document and if there are any existing notes, that will be displayed in here.

![Open popup note](Annotation-images\Stamp-Annotation-2.png)

## Properties

Selecting properties from the context menu will display the Stamp Properties window, which would consist of two tabs

*	Appearance
*	General 

## Appearance tab

The opacity of the stamp annotation can be edited using Appearance tab of Stamp Properties window.

### Editing opacity of the annotation

The slider control displayed in the Appearance tab allows modifying opacity of the selected stamp annotation. You can also modify the opacity of the selected stamp annotation by giving numeric value in the opacity text box.

The following image illustrates how to change the opacity of the stamp annotation.

![Edit opacity of stamp annotation](Annotation-images\Stamp-Annotation-3.png)

### Editing color

The background color of popup note of the selected stamp will be displayed in the color row in the appearance tab. Selecting the Color would display the color palette control, choosing a color from the color palette and clicking OK will apply the background color to the popup note of the stamp annotation.

The following image illustrates how to change the color of the stamp annotation included.

![Edit color of stamp annotation](Annotation-images\Stamp-Annotation-4.png)

## General tab

We can add or edit the Author and Subject of the stamp annotation using General tab of the Stamp Properties window.

The following image illustrates the change in Author and Subject of the included Stamp annotation.

![General Tab](Annotation-images\Stamp-Annotation-5.png)

## Deleting an annotation

Selecting delete option from the context menu which is displayed when clicking right on the selected annotation would delete the respective annotation from the PDF document.

The following image illustrates how to delete the included annotation from the PDF document.

![Delete stamp annotation](Annotation-images\Stamp-Annotation-6.png)

## Add custom stamps in the toolbar

The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl.html) allows you to add the custom stamps as images in the toolbar using the [StampAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerToolbarSettings~StampAnnotations.html) collection. You can select and include the stamp at the required location of the page using a mouse-tap. Refer to the following code to clear the existing standard stamps and to add a custom stamp in the toolbar.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.PdfViewer;
using System;
using System.Windows;
using System.Windows.Media.Imaging;

namespace PdfViewerDemo
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        # region Constructor
        public MainWindow()
        {
            InitializeComponent();
        
            //load the PDF document.
            pdfViewer.Load(@"HTTP Succinctly.pdf");

            //wire the DocumentLoaded event.
            pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
        }
        #endregion

        private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
        {
            // Clear the existing standard stamps if not needed.
            pdfViewer.ToolbarSettings.StampAnnotations.Clear();

            //Load the custom image from the local disk.
            System.Windows.Controls.Image customImage = new System.Windows.Controls.Image();
            customImage.Source = new BitmapImage(new Uri(@"..\..\Data\AdventureCycle.jpg", UriKind.RelativeOrAbsolute));
            
            //Create custom stamp from the image.
            PdfStampAnnotation customStamp = new PdfStampAnnotation(customImage);

            //Add the custom stamp in the toolbar.
            pdfViewer.ToolbarSettings.StampAnnotations.Add(customStamp);
        }
    }
}

{% endhighlight %}
{% endtabs %}

After executing the code, you can see the custom stamp has been added in the toolbar as shown in the following picture.

![Custom Stamp](Annotation-images\custom-stamp.png)

## Keyboard shortcuts

The below keyboard shortcuts are available to customize the annotation in the PDF document.

*	Delete key – Deletes the selected annotation from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.