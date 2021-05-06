---
layout: post
title: Viewing PDF Files in WPF Pdf Viewer control | Syncfusion
description: Learn about Viewing PDF Files support in Syncfusion WPF Pdf Viewer control and more.
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
   
2. Click the <b>Open</b> button in the toolbar, as shown in the following picture. ![Open PDF file](view-pdf-file-images/Openfile.png)
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

You can view the PDF file from code behind, by passing the [Stream](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream?redirectedfrom=MSDN&view=netcore-3.1) as a parameter to the Load method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). Refer to the following code to perform the same.

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

You can also view a PDF file using the [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) property of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource). The property accepts the string file path as well as [Stream](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream?redirectedfrom=MSDN&view=netcore-3.1).

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

            //Load PDF file using the` ItemSource` property.
            pdfViewer.ItemSource = @"HTTP Succinctly.pdf";
        }
        #endregion
    }
}
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

The following picture illustrates how the PDF file being displayed in [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) control. ![PDF file in PdfDocumentView](view-pdf-file-images/PdfDocumentView.png)

## Obtain the PDF file information

You can get the information on the PDF file that is being displayed in the control using the [DocumentInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DocumentInfo) property of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html). This property provides you the information such as file name and the folder name from that the PDF file is opened using the [FileName](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.DocumentInfo.html#Syncfusion_Windows_PdfViewer_DocumentInfo_FileName) and [FilePath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.DocumentInfo.html#Syncfusion_Windows_PdfViewer_DocumentInfo_FileName) properties respectively.

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
