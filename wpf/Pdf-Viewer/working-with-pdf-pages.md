---
layout: post
title: Working with PDF Pages in WPF Pdf Viewer control | Syncfusion<sup>&reg;</sup>;
description: Learn about Working with PDF Pages support in Syncfusion<sup>&reg;</sup>; Essential Studio&reg; WPF Pdf Viewer control, its elements and more.
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


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.

## Page Events
The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) notifies users of interactions with PDF pages through events such as [PageClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageClicked) and [PageMouseMove](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageMouseMove).

### Page Clicked
The [PageClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageClicked) event occurs when users click on a PDF page. It provides the information about the page index and the clicked position on the page. The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace WPF_PDFViewer
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Load the PDF file
            pdfViewer.Load("F Sharp Succinctly.pdf");
            //Wire the PageClicked event
            pdfViewer.PageClicked += PdfViewer_PageClicked;
        }

        /// <summary>
        /// Handle the PageClicked Event of PdfViewerControl
        /// </summary>
        private void PdfViewer_PageClicked(object sender, PageClickedEventArgs args)
        {
            //Get the page index on the page where you clicked
            int pageIndex = args.PageIndex;
            //Get the position on the page where you clicked
            Point position = args.Position;

            //Insert Your code Here.
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Page Mouse Move
The [PageMouseMove](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageMouseMove) event occurs when a user move the mouse on a PDF page. It provides information about the page index and the position on the page where the mouse has moved. The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace WPF_PDFViewer
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Load the PDF file
            pdfViewer.Load("F Sharp Succinctly.pdf");
            //Wire the PageMouseMove event
            pdfViewer.PageMouseMove += PdfViewer_PageMouseMove;
        }

        /// <summary>
        /// Handle the PageMouseMove Event of PdfViewerControl
        /// </summary>
        private void PdfViewer_PageMouseMove(object sender, PageMouseMoveEventArgs args)
        {
            //Get the page index on the page where you clicked
            int pageIndex = args.PageIndex;
            //Get the position on the page where you clicked
            Point position = args.Position;

            //Insert Your code Here.
        }
    }
}
{% endhighlight %}
{% endtabs %}