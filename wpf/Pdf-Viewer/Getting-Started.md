---
layout: post
title: Getting Started with WPF Pdf Viewer control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
 documentation: ug
---

# Getting Started with WPF Pdf Viewer

This section explains how to create an application that displays a PDF file using the WPF PDF Viewer.

To get started quickly with WPF PDF Viewer, you can check on this video:
<style>#WPFPDFViewerVideoTutorial{width : 90% !important; height: 400px !important }</style>
<iframe id='WPFPDFViewerVideoTutorial' src='https://www.youtube.com/embed/H1YBX_-QWKc'></iframe>

## Assemblies required

The following assemblies are required in your WPF application to use the PDF Viewer.

<table>
<tr>
<th>Required Assemblies</th>
<th>Description</th>
</tr>
<tr>
<td>Syncfusion.Compression.Base</td>
<td>This library handles various compression and decompression operations that are used in the PDF file internally.</td></tr>
<tr>
<td>Syncfusion.Pdf.Base</td>
<td>This library contains the PDF reader and creator that supports the PDF Viewer.</td></tr>
<tr>
<td>Syncfusion.PdfViewer.WPF</td>
<td>This component contains the rendering area and other related UI elements.</td>
</tr>
<tr>
<td>Syncfusion.Shared.WPF</td>
<td>This component contains various UI controls (ColorPickerPalette and Numeric UpDown) that are used in the PDF Viewer.</td></tr>
</table>

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [this link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your WPF application to use our components.

## Create a simple PDF Viewer application 

You can create a PDF Viewer application by simply drag the control from the Visual Studio toolbox and drop in the designer window of your application or by creating the control manually from code.

### Drag and drop the PdfViewerControl from the toolbox
Follow these steps to drag and drop the PdfViewerControl from the toolbox.

1. After installing the Syncfusion Essential Studio in your machine, create a new WPF application in Visual Studio.
2. Open the Visual Studio toolbox.
3. Navigate to <b>Syncfusion WPF Toolbox</b> tab and drag the `PdfViewerControl` toolbox item to the Designer window, it automatically adds the required references to the current application.

   ![Getting started](Getting-Started_images/Toolbox.png)
    PDF viewer control in toolbox
    {:.caption}

### Adding control manually in XAML
To add control manually in XAML, do the following steps,

1. Add the required assemblies as a reference to the project.
2. Add the following Syncfusion namespace in XAML to make use of the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

	~~~xaml
	<Window
		xmlns:syncfusion="clr-namespace:Syncfusion.Windows.PdfViewer;assembly=Syncfusion.PdfViewer.WPF"
	</Window>	
	~~~

3. Declare the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) in the XAML page.

   ~~~xaml
	<Window 
		x:Class="PdfViewerDemo.MainWindow"
		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
		Title="PDF Viewer" WindowState="Maximized"
		xmlns:syncfusion="clr-namespace:Syncfusion.Windows.PdfViewer;assembly=Syncfusion.PdfViewer.WPF">
		<Grid x:Name="HomeGrid">
			<syncfusion:PdfViewerControl x:Name="pdfViewer"></syncfusion:PdfViewerControl>
		</Grid>
	</Window>
   ~~~

### Adding control manually from code

To add control manually from code, follow these steps,

1.	Add the required assemblies as a reference to the project.
2.	Add the following Syncfusion namespace class file.

	~~~csharp
	using Syncfusion.Windows.PdfViewer;
	~~~

3. Create a PdfViewerControl instance and add it to the main window.

   ~~~csharp
	using Syncfusion.Windows.PdfViewer;
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
				PdfViewerControl pdfViewer = new PdfViewerControl();
				HomeGrid.Children.Add(pdfViewer);
			}
			#endregion
		}
	}
   ~~~

## Display PDF file

The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html)’s [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) property allows you to bind PDF documents in XAML. This property accepts a stream input that can be bounded to the viewer during initialization. The following steps explain how to display a PDF file using the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html):

N> From v16.3.0x onwards, PDF Viewer uses PDFium as a default rendering engine to render the PDF pages, which is a more robust and promising rendering engine. Refer to this [link](https://help.syncfusion.com/wpf/pdf-viewer/pdf-rendering-engines) for more details.

1.	Create a simple class in the application that implements [INotifyPropertyChanged](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=netcore-3.1) and declare a file stream property in the class as shown in the following code sample.

	~~~csharp
	using System.ComponentModel;
	using System.IO;

	namespace PdfViewerDemo
	{
		public class PdfReport : INotifyPropertyChanged
		{
			private Stream docStream;

			public event PropertyChangedEventHandler PropertyChanged;

			public Stream DocumentStream
			{
				get
				{
					return docStream;
				}
				set
				{
					docStream = value;
					OnPropertyChanged(new PropertyChangedEventArgs("DocumentStream"));
				}
			}

			public PdfReport()
			{
				//Load the stream from the local system.
				docStream = new FileStream(@"../../Data/HTTP Succinctly.pdf", FileMode.OpenOrCreate);
			}

			public void OnPropertyChanged(PropertyChangedEventArgs e)
			{
				if (PropertyChanged != null)
					PropertyChanged(this, e);
			}
		}
	}
	~~~

2. Set the [DataContext](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.datacontext?view=netcore-3.1) to the Window for data binding. To add the `DataContext` in XAML, use the following code example.

	~~~xaml
	<Window.DataContext>
		<pdfviewerdemo:PdfReport/>
	</Window.DataContext>
	~~~

3.	After setting the `DataContext`, bind the file stream property to the [ItemSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ItemSource) dependency property of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) using the following code sample in XAML.

	~~~xaml
	<syncfusion:PdfViewerControl x:Name="pdfViewer" ItemSource="{Binding DocumentStream}"/>
	~~~

The sample project for displaying PDF files using the PDF Viewer is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-PDFViewer-Examples/tree/master/DisplayPDF).

N> Alternatively, the Open button in the toolbar can also be used to load and display the PDF documents at runtime. Refer to this [link](https://help.syncfusion.com/wpf/pdf-viewer/viewing-pdf-files#open-pdf-file-from-the-local-disk-using-toolbar) for more details.

## Theme

PdfViewerControl supports various built-in themes. Refer to the below links to apply themes for the PdfViewerControl,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme in WPF PDFViewer](Getting-Started_images/Theme.png)