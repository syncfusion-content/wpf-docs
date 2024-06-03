---
layout: post
title: Viewing PDF Files in WPF Pdf Viewer control | Syncfusion
description: Learn about Viewing PDF Files support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Viewing PDF Files in WPF Pdf Viewer

PDF Viewer allows you to easily open and view the PDF files interactively using the <b>Open</b> button in the built-in toolbar as well as from code behind using the available APIs.

## Open PDF file from the local disk using toolbar

You can open a PDF file from the toolbar by browsing it from the local disk. You can open both the normal and password-protected PDF files. The Open button in the toolbar allows you to perform the same using the following steps.

1. Add the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) in the MainWindow.xaml and run the project.

   ~~~xaml
	<Window 
		x:Class="PdfViewerDemo.MainWindow"
		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
		WindowState="Maximized"
		xmlns:syncfusion="clr-namespace:Syncfusion.Windows.PdfViewer;assembly=Syncfusion.PdfViewer.WPF">
		<Grid>
			<syncfusion:PdfViewerControl x:Name="pdfViewer"></syncfusion:PdfViewerControl>
		</Grid>
	</Window>
   ~~~
   
2. Click the <b>Open</b> button in the toolbar, as shown in the following picture. ![WPF PDF Viewer Open PDF file](view-pdf-file-images/wpf-pdf-viewer-open-file.png)
3. In the open file dialog, enter the file name or browse the file from the local disk and select <b>Open</b>.

## View PDF file using the file path

You can view the PDF file from code behind, by passing the file path as a parameter to the [Load](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Load_System_String_) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). It accepts both the absolute and relative file paths. Refer to the following code to perform the same.

{% tabs %}
{% highlight c# %}
using System.Windows;

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

            //Load PDF file using the file path.
            pdfViewer.Load(@"HTTP Succinctly.pdf");
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

## View PDF file from stream

You can view the PDF file from code behind, by passing the [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?redirectedfrom=MSDN&view=netcore-3.1) as a parameter to the Load method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). Refer to the following code to perform the same.

{% tabs %}
{% highlight c# %}
using System.IO;
using System.Windows;

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
            FileStream stream = new FileStream(@"HTTP Succinctly.pdf", FileMode.Open);

            //Load PDF file using stream.
            pdfViewer.Load(stream);
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

## View PDF file using the ItemSource property

You can also view a PDF file using the [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) property of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource). The property accepts a string file path, a [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-7.0&redirectedfrom=MSDN), and a [PdfLoadedDocument](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Parsing.PdfLoadedDocument.html) object.

{% tabs %}
{% highlight c# %}
using System.Windows;

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

            //Load PDF file using the `ItemSource` property.
            pdfViewer.ItemSource = @"HTTP Succinctly.pdf";
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

Refer the below code snippet to load a [Stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-7.0&redirectedfrom=MSDN) using the [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) property
{% tabs %}
{% highlight c# %}
//Load PDF file as Stream using the `ItemSource` property.
pdfViewer.ItemSource = new FileStream(@"HTTP Succinctly.pdf",FileMode.Open); 
{% endhighlight %}
{% endtabs %}

Refer the below code snippet to load a [PdfLoadedDocument](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Parsing.PdfLoadedDocument.html) object using the [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) property.
{% tabs %}
{% highlight c# %}
//Load PDF file as PdfLoadedDocument object using the `ItemSource` property.
PdfLoadedDocument pdfLoadedDocument = new PdfLoadedDocument(@"HTTP Succinctly.pdf"); 
pdfViewer.ItemSource = pdfLoadedDocument;  
{% endhighlight %}
{% endtabs %}


## View PDF files without using the toolbar

The [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control allows you to view the PDF files without toolbar using the [Load](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) methods from code behind. Refer to the following steps to perform the same.

1. Add the [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control in the MainWindow.xaml.

   ~~~xaml
	<Window 
		x:Class="PdfViewerDemo.MainWindow"
		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
		WindowState="Maximized"
		xmlns:syncfusion="clr-namespace:Syncfusion.Windows.PdfViewer;assembly=Syncfusion.PdfViewer.WPF">
		<Grid>
			<syncfusion:PdfDocumentView x:Name="pdfViewer"></syncfusion:PdfDocumentView>
		</Grid>
	</Window>
   ~~~
   
2. Load the file using the [Load](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Load_System_String_) method as mentioned in the following code snippet in MainWindow.xaml.cs.
   
   ~~~csharp
	using System.Windows;
	
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

				//Load PDF file using file path.
				pdfViewer.Load(@"HTTP Succinctly.pdf");
			}
			#endregion
		}
	}
   ~~~
   
3. Run the project.

The following picture illustrates how the PDF file being displayed in [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control. ![WPF PDF Viewer File in PdfDocumentView](view-pdf-file-images/wpf-pdf-viewer-file-in-pdfdocumentview.png)

## Avoid exception while loading PDF Document

When opening a PDF document in PdfViewer and attempting to open a new one, unloading the previously opened document is not required. This is due to PdfViewer's internal process: when loading a new document, it automatically unloads and disposes of any previously opened document. Therefore, attempting to explicitly unload the document may lead to an exception, as this action is already handled internally within the WPF PDF Viewer.

For instance, when attempting to open a document through a button click event, utilize the following code snippet:

{% tabs %}
{% highlight c# %}

 private void test_Click(object sender, RoutedEventArgs e)
 {
     //No need to close the existing document because it is internally implemented.
     //pdfViewer.Unload();
     pdfViewer.Load("Document.pdf");    
 }

{% endhighlight %}
{% endtabs %}

## Obtain the PDF file information

You can get the information on the PDF file that is being displayed in the control using the [DocumentInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DocumentInfo) property of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). This property provides you the information such as file name and the folder name from that the PDF file is opened using the [FileName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.DocumentInfo.html#Syncfusion_Windows_PdfViewer_DocumentInfo_FileName) and [FilePath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.DocumentInfo.html#Syncfusion_Windows_PdfViewer_DocumentInfo_FilePath) properties respectively.

Refer to the following code to obtain the document information using the [DocumentInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DocumentInfo) property.

{% tabs %}
{% highlight c# %}
using System.IO;
using System.Windows;

namespace PdfViewerDemo
{
    /// <summary>
    /// Interaction logic for Window1.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        # region Constructor
        public MainWindow()
        {
            InitializeComponent();
            //Load PDF file with the absolute file path.
            pdfViewer.Load(Path.GetFullPath(@"HTTP Succinctly.pdf"));

            //Get the file name
            string fileName = pdfViewer.DocumentInfo.FileName;
            string folder = pdfViewer.DocumentInfo.FilePath;

        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

If you open a file using the toolbar, you can obtain the information in the [DocumentLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) event. Refer to the following code to achieve the same.

{% tabs %}
{% highlight c# %}
using System.Windows;

namespace PdfViewerDemo
{
    /// <summary>
    /// Interaction logic for Window1.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        # region Constructor
        public MainWindow()
        {
            InitializeComponent();
            //wire the DocumentLoaded event
            pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
        }
        #endregion

        private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
        {
            //Get the file name
            string fileName = pdfViewer.DocumentInfo.FileName;
            string folder = pdfViewer.DocumentInfo.FilePath;
        }
    }
}
{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.