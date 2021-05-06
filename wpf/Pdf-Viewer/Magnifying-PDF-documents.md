---
layout: post
title: Magnifying PDF documents in WPF Pdf Viewer control | Syncfusion
description: Learn about Magnifying PDF documents support in Syncfusion WPF Pdf Viewer control and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Magnifying PDF documents in WPF Pdf Viewer

PDF Viewer allows you to magnify the PDF document that is being displayed using the [ZoomTo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ZoomTo_System_Int32_) method. The following code examples can be used to perform this action.

{% tabs %}
{% highlight c# %}
//Initialize PDF Viewer.
PdfViewerControl pdfViewer1 = new PdfViewerControl();

//Load the PDF.
pdfViewer1.Load("Sample.pdf");

//Magnify the document to 150%
pdfviewer1.ZoomTo(150);
{% endhighlight %}

{% highlight vbnet %}
'Initialize PDF Viewer.
Private pdfViewer1 As New PdfViewerControl()

'Load the PDF.
pdfViewer1.Load("Sample.pdf")

'Magnify the document to 150%
pdfviewer1.ZoomTo(150)
{% endhighlight %}
{% endtabs %}

The magnification can also be set by updating the [Zoom](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Zoom) property of the PDF Viewer.
{% tabs %}
{% highlight c# %}

//Magnify the document to 150%
pdfviewer1.Zoom = 250;
{% endhighlight %}
{% highlight vbnet %}

'Magnify the document to 150%
pdfviewer1.Zoom = 250
{% endhighlight %}
{% endtabs %}

## Current zoom percentage

Current magnification percentage of the PDF Viewer can be acquired with the use of the property [ZoomPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ZoomPercentage)

{% tabs %}
{% highlight c# %}

//Acquire current zoom percentage

int currentZoomPercentage = pdfviewer1.ZoomPercentage;

{% endhighlight %}

{% highlight vbnet %}
' Acquire current zoom percentage 
Dim currentZoomPercentage As Integer = pdfviewer1.ZoomPercentage
{% endhighlight %}
{% endtabs %}

## Zoom mode

Zoom mode of the PDF viewer can be set using the following code example.

{% tabs %}
{% highlight c# %}

//Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth;
{% endhighlight %}

{% highlight vbnet %}

'Setting zoom mode to the PDF Viewer
pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth

{% endhighlight %}
{% endtabs %}

## Customize the minimum and maximum zoom percentage

The default minimum and maximum zoom percentage of the PDF Viewer is 50 and 400 respectively. However, the PDF Viewer allows you to customize the minimum and maximum zoom percentage values based on your requirement.

### Minimum zoom percentage

You can customize the minimum zoom percentage of the PDF viewer using the [MinimumZoomPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_MinimumZoomPercentage) property. Its default value is 50. Refer to the following code to set the property and apply the customized minimum zoom percent to [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

using System.Windows;

namespace ZoomPercentDemo
{
    #region Constructor
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();

            //Load PDF document.
            pdfviewer.Load(@"../../Data/Barcode.pdf");

            //Set the minimum zoom percentage.
            pdfviewer.MinimumZoomPercentage = 25;

            //Magnify the document to minimum zoom percentage.
            pdfviewer.ZoomTo(pdfviewer.MinimumZoomPercentage);
        }
    }
    #endregion
}

{% endhighlight %}
{% endtabs %}

N> The allowed value of this property ranges from 10 to the value of the [MaximumZoomPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_MaximumZoomPercentage) of PDF Viewer.

### Minimum zoom percentage

You can customize the maximum zoom percentage of the PDF viewer using the [MaximumZoomPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_MaximumZoomPercentage) property. Its default value is 400. Refer to the following code to set the property and apply the customized maximum zoom percentage to [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

using System.Windows;

namespace ZoomPercentDemo
{
    #region Constructor
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();

            // Load PDF document.
            pdfviewer.Load(@"../../Data/Barcode.pdf");

            //Set the maximum zoom percentage.
            pdfviewer.MaximumZoomPercentage = 600;

            //Magnify the document to maximum zoom percentage.
            pdfviewer.ZoomTo(pdfviewer.MaximumZoomPercentage);
        }
    }
    #endregion
}

{% endhighlight %}
{% endtabs %}

N> The allowed value of this property ranges from the value of [MinimumZoomPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_MinimumZoomPercentage) of the PDF Viewer to 800.
