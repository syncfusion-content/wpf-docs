---
layout: post
title: Working with PDF Pages | PDF Viewer | WPF | Syncfusion
description: This section explains about how to customize the border color of the PDF pages and toggle the border visibility in PDF Viewer. 
platform: WPF
control: PDF Viewer
documentation: UG
---

# Working with PDF Pages

## Page Border

The [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PageBorder.html) allows you to customize the visibility and color of the border of the pages which are being displayed in the PDF Viewer.

N> This border customization applies only when on viewing the PDF file in the PDF viewer and it will not have an effect in the saved or printed file from the PDF Viewer.

### Color

The [Color](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PageBorder~Color.html) property of the [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~PageBorder.html) allows you to customize the border color of the pages which are being displayed in the PDF Viewer. The default border color of the pages is `Black`. Refer to the following code sample to set a different color to the border of the pages.

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

The [PageBorder](https://help.syncfusion.com/cr/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~PageBorder.html) property allows you to show or hide the border of the pages which are being displayed in the PDF Viewer. By default, the border of the pages will be visible. Refer to the following code sample to hide the border of the pages.

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