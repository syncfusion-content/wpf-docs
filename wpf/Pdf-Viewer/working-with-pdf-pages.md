---
layout: post
title: Working with PDF Pages in WPF Pdf Viewer control | Syncfusion
description: Learn about Working with PDF Pages support in Syncfusion WPF Pdf Viewer control and more.
platform: WPF
control: PDF Viewer
documentation: UG
---

# Working with PDF Pages in WPF Pdf Viewer

## Page Border

The [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageBorder.html) allows you to customize the border visibility and color of the pages that are being displayed in the PDF Viewer.

N> This border customization applies only when viewing the PDF file in the PDF viewer and it will not affect the saved or printed file from the PDF Viewer.

### Color

The [Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageBorder.html#Syncfusion_Windows_PdfViewer_PageBorder_Color) property of the [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageBorder) allows you to customize the border color of the pages that are being displayed in the PDF Viewer. The default border color of the pages is `Black`. Refer to the following code sample to set a different color to the border of the pages.

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace PdfViewerDemo
{
    /// <summary>
    /// Interaction logic for Window1.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        #region Constructor
        public MainWindow()
        {
            InitializeComponent();

            //Create an instance for `PageBorder`.
            PageBorder pageBorder = new PageBorder();

            //Set the `Color` property.
            pageBorder.Color = System.Drawing.Color.Red;

            //Assign the 'PageBorder' propery of PDF Viewer.
            pdfViewer.PageBorder = pageBorder;

            //Load the PDF file.
            pdfViewer.Load(@"Sample.pdf");
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

### Visibility

The [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageBorder) property allows you to show or hide the border of the pages that are being displayed in the PDF Viewer. By default, the border of the pages will be visible. Refer to the following code sample to hide the border of the pages.

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace PdfViewerDemo
{
    /// <summary>
    /// Interaction logic for Window1.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        #region Constructor
        public MainWindow()
        {
            InitializeComponent();

            //Create an instance for `PageBorder`.
            PageBorder pageBorder = new PageBorder();

            //Set the `IsVisible` property as false to hide the page border.
            pageBorder.IsVisible = false;

            //Assign the 'PageBorder' propery of PDF Viewer.
            pdfViewer.PageBorder = pageBorder;

            //Load the PDF file.
            pdfViewer.Load(@"Sample.pdf");
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}
