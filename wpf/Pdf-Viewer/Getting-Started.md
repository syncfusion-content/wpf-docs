---
layout: post
title: Getting Started| PDF Viewer | WPF | Syncfusion
description: Getting started section will guide through how to use the PDF viewer WPF control in the WPF application, step by step in MVVM pattern.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Getting Started with PDFViewer

This section demonstrates how to create an application that displays a PDF file using PDF viewer.

To get start quickly with WPF PDFViewer, you can check on this video:
<style>#WPFPDFViewerVideoTutorial{width : 90% !important; height: 400px !important }</style>
<iframe id='WPFPDFViewerVideoTutorial' src='https://www.youtube.com/embed/H1YBX_-QWKc'></iframe>

## Assemblies required

The following assemblies are required in your WPF application to use PDF viewer.

<table>
<tr>
<th>
Required Assemblies</th><th>
Description</th></tr>
<tr>
<td>
Syncfusion.Compression.Base</td><td>
This library handles various compression and decompression operations that are used in the PDF file internally.</td></tr>
<tr>
<td>
Syncfusion.Pdf.Base</td><td>
This library contains the PDF reader and creator that supports the `PdfViewerControl`.</td></tr>
<tr>
<td>
Syncfusion.PdfViewer.WPF</td><td>
This component contains the rendering area and other related UI elements.</td></tr>
<tr>
<td>
Syncfusion.Shared.WPF</td><td>
This component provides various UI styles and themes used in the `PdfViewerControl`.</td></tr>
</table>

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [this link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your WPF application to use our components.

## Create a simple PDF viewer application 

Following steps demonstrates creating a simple PDF viewer application in WPF:

### Drag the PdfViewerControl from toolbox

1. After installing the Syncfusion Essential Studio in your machine, create a new WPF application in Visual Studio.
2. Open the Visual Studio tool box. Navigate to “Syncfusion WPF Toolbox” tab and drag the `PdfViewerControl` toolbox item to the Designer window, it automatically adds the required references to the current application.

   ![Getting started](Getting-Started_images/Getting-Started_img3.png)

    PDF viewer control in toolbox
    {:.caption}

### Creating PdfViewerControl from code

1. To add the `PdfViewerControl` using code, add the required assemblies as reference to the project.
2. Add the following Syncfusion namespace in XAML to make use of the `PdfViewerControl`.

   ~~~xaml

		<Window

		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

		xmlns:Syncfusion="clr-namespace:Syncfusion.Windows.PdfViewer;assembly=Syncfusion.PdfViewer.WPF" 

		x:Class="GettingStartedWPF.MainWindow"

		Title="MainWindow" Height="350" Width="525">

   ~~~		


3. Add the following code in XAML.

   ~~~xaml

		<Syncfusion:PdfViewerControl Name="pdfViewerControl1"/>


   ~~~

## Display PDF file
   
The PdfViewerControl’s [ItemSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ItemSource.html) property allows you to bind PDF documents in XAML. This property accepts a stream input that can be bounded to the viewer during initialization. The following steps demonstrates how to display a PDF file using the `PdfViewerControl`:

1. Create a simple class that loads a PDF document  as illustrated in the following code example. Save the class file as PdfReport.cs.

   ~~~csharp


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

		docStream = new FileStream("Barcode.pdf", FileMode.OpenOrCreate);           

		}





		public void OnPropertyChanged(PropertyChangedEventArgs e)

		{

		if (PropertyChanged != null)

		PropertyChanged(this, e);

		}

		}


   ~~~

2. To bind the DocumentStream property of the PdfReport class, set the DataContext to the Window. To add the DataContext in XAML, use the following code example.

   ~~~xaml

		<Window.DataContext>

		<local:PdfReport/>

		</Window.DataContext>

   ~~~

3. After setting the DataContext, you can set the ItemSource dependency property of `PdfViewerControl` by using the following code example in XAML.

   ~~~xaml

		<Syncfusion:PdfViewerControl ItemSource="{Binding DocumentStream}"/>

   ~~~

N> Alternatively, the Open button in the toolbar can also be used to load and display the PDF documents at runtime.
