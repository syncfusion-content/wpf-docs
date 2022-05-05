---
layout: post
title: Printing PDF Files in WPF Pdf Viewer control | Syncfusion
description: Learn about Printing PDF Files support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Printing PDF Files in WPF Pdf Viewer

PDF Viewer allows printing loaded PDFs using the Print button in the toolbar. The following Print dialog opens upon triggering the Print button.

![WPF PDF Viewer PrintDialog Window](Concept-and-Features_images/wpf-pdf-viewer-print-dialog-window.png)

N> PdfDocumentView is used to view the PDF documents without the toolbar. So, make use of PdfViewerControl to print the document using Print button in the toolbar.

## Silent Printing

The [Print](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Print) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) and [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) allows you to print PDF files silently to the system's default printer, without any user interaction. You can enable the preferred settings for silent printing using the [PrinterSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrinterSettings) property. The following code example shows how to perform silent printing in WPF PDF Viewer.

{% tabs %}
{%highlight c#%}

pdfviewer1.Print();

{%endhighlight%}

{%highlight vb%}

pdfviewer1.Print()

{%endhighlight%}
{% endtabs %}

## Customizing print size

PDF viewer printer settings allows scaling PDF pages to shrink or enlarge while printing.

### Actual Size

Actual size is the default value of print size option in printer settings. This prints the loaded PDF document without any scaling factors. The pages that do not fit on the paper will be cropped. The following code example illustrates how to print the document in Actual Size.

{% tabs %}
{% highlight c# %}

// Prints the document in actual size.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.ActualSize;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document in actual size.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.ActualSize

{% endhighlight %}
{% endtabs %}

### Fit

Fit option enlarges or reduces each page to fit the printable area of the selected paper size. The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

// Prints the document in fit size.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.Fit;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document in fit size.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.Fit

{% endhighlight %}
{% endtabs %}

### Custom Scale

Custom Scale option resizes the page with the specified scale percentage. The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

// Prints the document with custom scaling.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.CustomScale;

// Scale percentage with the page to be resized and it is applicable only for Custom Scale. The default value is 100.

pdfviewer1.PrinterSettings.ScalePercentage = 120;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document with custom scaling.

pdfviewer1.PrinterSettings.PageSize = PdfViewerPrintSize.CustomScale

' Scale percentage with the page to be resized and it is applicable only for Custom Scale. The default value is 100.

pdfviewer1.PrinterSettings.ScalePercentage = 120

{% endhighlight %}
{% endtabs %}

## Printing PDF document with orientation settings

PDF Viewer printer settings allows the user to print the document with a custom orientation.

### Auto Portrait/Landscape

Auto Portrait/Landscape is the default option and it automatically selects the best orientation (Portrait or Landscape) based on the content and selected paper. The following code example illustrates how to print the document in Auto orientation.

{% tabs %}
{% highlight c# %}

// Prints the document in auto orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Auto;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document in auto orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Auto

{% endhighlight %}
{% endtabs %}

### Portrait

Portrait option prints the PDF document in portrait orientation and it overrides the orientation settings provided in the print dialog. The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

// Prints the document in portrait orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Portrait;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document in portrait orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Portrait

{% endhighlight %}
{% endtabs %}

### Landscape

Landscape option prints the PDF document in landscape orientation and it overrides the orientation settings provided in print dialog. The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

// Prints the document in landscape orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Landscape;

{% endhighlight %}

{% highlight vbnet %}

' Prints the document in landscape orientation.

pdfviewer1.PrinterSettings.PageOrientation = PdfViewerPrintOrientation.Landscape

{% endhighlight %}
{% endtabs %}

## Set the custom document name to be displayed when printing

PDF viewer allows you to set the custom document name to be displayed when printing the PDF document using the [DocumentName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_DocumentName) property that is available in the [PrinterSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrinterSettings). You can either set the original file name or a custom text to the property for display. Setting the [DocumentName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_DocumentName) property will affect the Document name details in the print status dialog.

![WPF PDF Viewer Print Status Dialog](printing-images/wpf-pdf-viewer-print-status-dialog.png)

The [DocumentName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_DocumentName) property will also affect the Document name details in the print queue information window.

![WPF PDF Viewer Print Queue](printing-images/wpf-pdf-viewer-print-queue.png)

The following code shows how to set the original file name to the [DocumentName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_DocumentName) property.

{% tabs %}
{% highlight c# %}

using System.IO;
using System.Windows;

namespace PdfViewer
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

            //Load PDF file with the absolute file path.
            string filePath = Path.GetFullPath(@"../../Data/PDF_Succinctly.pdf");
            pdfViewer.Load(filePath);
            
            //Get the file name
            string fileName = pdfViewer.DocumentInfo.FileName;
            
            //Set the document name to be displayed when printing the document.
            pdfViewer.PrinterSettings.DocumentName = fileName;

            //Print the file.
            pdfViewer.Print();
        }
        #endregion
    }
}

{% endhighlight %}
{% endtabs %}

## Hide Print Status dialog when printing the PDF files

PDF Viewer allows you to hide the following print status dialog when printing the PDF files by setting the value `false` to the [ShowPrintStatusDialog](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_ShowPrintStatusDialog) property that is available in the [PrinterSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrinterSettings).

![WPF PDF Viewer Hide Print Status Dialog](printing-images/wpf-pdf-viewer-print-status-dialog.png)

It will be helpful if no UI interactions are required when printing. The following code shows how to hide the print status dialog using the [ShowPrintStatusDialog](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerPrinterSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerPrinterSettings_ShowPrintStatusDialog) property.

{% tabs %}
{% highlight c# %}

using System.IO;
using System.Windows;

namespace PdfViewer
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

            //Load PDF file.
            string filePath = Path.GetFullPath(@"../../Data/PDF_Succinctly.pdf");
            pdfViewer.Load(filePath);
            
            //Set the document name to be displayed when printing the document.
            pdfViewer.PrinterSettings.ShowPrintStatusDialog = false;

            //Print the file.
            pdfViewer.Print();
        }
        #endregion
    }
}

{% endhighlight %}
{% endtabs %}

## Customizing Paper source in Silent Printing

You can customize [PaperSource](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings.papersource?view=net-5.0) in silent printing by changing the [PaperSource](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings.papersource?view=net-5.0) property in [PageSettings](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings?view=net-5.0) and passing it as a parameter with printer name to the [Print](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_Print_System_String_System_Drawing_Printing_PageSettings_) API. 

N> The `System.Drawing` assembly is required. 

The following code example illustrates how to set [PaperSource](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings.papersource?view=net-5.0) for Your printer. In the [PageSettings](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings?view=net-5.0), pass the required [PaperSource](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.printing.pagesettings.papersource?view=net-5.0) value. 

{% tabs %}
{% highlight c# %}

PrinterSettings printerSettings = new PrinterSettings(); 
PageSettings pageSettings = new PageSettings();

private void Button_Click(object sender, RoutedEventArgs e)
{

 //Enter Your Printer’s Name
 printerSettings.PrinterName = "Mention Your printer's name here";

 //Changes the papersource in pagesettings
 pageSettings.PaperSource = printerSettings.PaperSources[3];

 //Prints the PDF with required papersource
 pdfviewer.Print(printerSettings.PrinterName, pageSettings);
 
}

{% endhighlight %}
{% endtabs %}

## Events

The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) notifies you at the start, progress, and end of the printing through events such as [BeginPrint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_BeginPrint), [PrintProgress](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrintProgress), and [EndPrint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_EndPrint), respectively.

### Begin Print

The [BeginPrint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_BeginPrint) event occurs when the print is called and before the first page of the document prints. The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

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
            //Wire the BeginPrint event
            pdfViewer.BeginPrint += pdfViewer_BeginPrint;

            //Load the PDF file
            pdfViewer.Load("F Sharp Succinctly.pdf");

            //Print the PDF silently to the default printer. 
            pdfViewer.Print(true);
        }
        //Handle the BeginPrint Event
        private void pdfViewer_BeginPrint(object sender, BeginPrintEventArgs args)
        {
            //Insert Your code Here.
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Print Progress

The [PrintProgress](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrintProgress) event provides information on how much printing content you submitted to the printing subsystem. It provides the page information through the [PrintProgressEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PrintProgressEventArgs.html). The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace WPF_PDFViewer
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Wire the PrintProgress event
            pdfViewer.PrintProgress += pdfViewer_PrintProgress;

            //Load the PDF file
            pdfViewer.Load("F Sharp Succinctly.pdf");

            //Print the PDF silently to the default printer. 
            pdfViewer.Print(true);
        }
        //Handle the PrintProgress Event
        private void pdfViewer_PrintProgress(object sender, PrintProgressEventArgs args)
        {
            //Provide the total number of pages in the PDF
            int printCount = args.PageCount;

            //Provide the currently printing page number
            int currentPage = args.PageIndex;
        }
    }
}

{% endhighlight %}
{% endtabs %}

### End Print

The [EndPrint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_EndPrint) event occurs when you have printed the last page of the document. It also happens if you cancel the printing process or an exception occurs during the printing process. The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

using System.Windows;
using Syncfusion.Windows.PdfViewer;

namespace WPF_PDFViewer
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Wire the EndPrint event
            pdfViewer.EndPrint += pdfViewer_EndPrint;

            //Load the PDF file
            pdfViewer.Load("F Sharp Succinctly.pdf");

            //Print the PDF silently to the default printer. 
            pdfViewer.Print(true);
        }
        //Handle the EndPrint Event
        private void pdfViewer_EndPrint(object sender, EndPrintEventArgs args)
        {
            //Insert your code here
        }
    }
}

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.