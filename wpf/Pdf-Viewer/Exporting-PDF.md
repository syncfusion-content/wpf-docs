---
layout: post
title: Exporting PDF pages in WPF Pdf Viewer control | Syncfusion
description: Learn about Exporting PDF pages support in Syncfusion WPF Pdf Viewer control, its elements and more details.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting PDF pages in WPF Pdf Viewer

Essential PDF Viewer allows exporting pages of a PDF file into JPG, PNG, TIFF, and BMP formats using [ExportAsImage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAsImage_System_Int32_) methods. This option helps to convert PDF pages into images.

## Exporting a single page

You can export a single page of the PDF file into an image by passing the page index as a parameter of the [ExportAsImage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAsImage_System_Int32_) method. Refer to the following code to export a single page of PDF into JPEG image.

{% tabs %}
{% highlight C# %}

PdfViewerControl pdfViewer = new PdfViewerControl();

//Load the input PDF file
PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Sample.pdf");
pdfViewer.Load(loadedDocument);

//Export the particular PDF page as image at the page index of 0
BitmapSource image = pdfViewer.ExportAsImage(0);
//Set up the output path
string output = @"..\..\Output\Image";
if (image != null)
{
	//Initialize the new Jpeg bitmap encoder
	BitmapEncoder encoder = new JpegBitmapEncoder();
	//Create the bitmap frame using the bitmap source and add it to the encoder
	encoder.Frames.Add(BitmapFrame.Create(image));
	//Create the file stream for the output in the desired image format
	FileStream stream = new FileStream(output + ".Jpeg", FileMode.Create);
	//Save the stream, so that the image will be generated in the output location
	encoder.Save(stream);
}

//Dispose the document
loadedDocument.Dispose();
loadedDocument = null;

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewer As PdfViewerControl = New PdfViewerControl()

'Load the input PDF file
Dim loadedDocument As PdfLoadedDocument = New PdfLoadedDocument("Sample.pdf")
pdfViewer.Load(loadedDocument)

'Export the particular PDF page as image at the page index of 0
Dim image As BitmapSource = pdfViewer.ExportAsImage(0)
'Set up the output path
Dim output As String = "..\..\Output\Image"
If image IsNot Nothing Then
	'Initialize the new Jpeg bitmap encoder
	Dim encoder As BitmapEncoder = New JpegBitmapEncoder()
	'Create the bitmap frame using the bitmap source and add it to the encoder.
	encoder.Frames.Add(BitmapFrame.Create(image))
	'Create the file stream for the output in the desired image format
	Dim stream As FileStream = New FileStream(output & ".Jpeg", FileMode.Create)
	'Save the stream, so that the image will be generated in the output location
	encoder.Save(stream)
End If

'Dispose the document
loadedDocument.Dispose()
loadedDocument = Nothing

{% endhighlight %}
{% endtabs %}

N> You can follow a similar step for exporting PDF into images in all the other image formats.

## Exporting a specific range of pages

You can export a specific range of PDF pages into images by passing the start and end page indexes as parameters of the [ExportAsImage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAsImage_System_Int32_System_Int32_) method. Refer to the following code to export the pages of PDF into JPEG images.

{% tabs %}
{% highlight C# %}

PdfViewerControl pdfViewer = new PdfViewerControl();

//Load the input PDF file
PdfLoadedDocument loadedDocument = new PdfLoadedDocument("Sample.pdf");
pdfViewer.Load(loadedDocument);

//Export all the pages as images at the specific page range
BitmapSource[] image = pdfViewer.ExportAsImage(0, loadedDocument.Pages.Count - 1);

//Set up the output path
string output = @"..\..\Output\Image";
if (image != null)
{
	for (int i = 0; i < image.Length; i++)
	{
		//Initialize the new Jpeg bitmap encoder
		BitmapEncoder encoder = new JpegBitmapEncoder();
		//Create the bitmap frame using the bitmap source and add it to the encoder
		encoder.Frames.Add(BitmapFrame.Create(image[i]));
		//Create the file stream for the output in the desired image format
		FileStream stream = new FileStream(output + i.ToString() + ".Jpeg", FileMode.Create);
		//Save the stream, so that the image will be generated in the output location
		encoder.Save(stream);
	}
}

//Dispose the document
loadedDocument.Dispose();
loadedDocument = null;

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewer As PdfViewerControl = New PdfViewerControl()

'Load the input PDF file
Dim loadedDocument As PdfLoadedDocument = New PdfLoadedDocument("Sample.pdf")
pdfViewer.Load(loadedDocument)

'Export all the pages as images at the specific page range
Dim image As BitmapSource() = pdfViewer.ExportAsImage(0, loadedDocument.Pages.Count - 1)
'Set up the output path
Dim output As String = "..\..\Output\Image"
If image IsNot Nothing Then
	For i As Integer = 0 To image.Length - 1
		'Initialize the new Jpeg bitmap encoder
		Dim encoder As BitmapEncoder = New JpegBitmapEncoder()
		'Create the bitmap frame using the bitmap source and add it to the encoder
		encoder.Frames.Add(BitmapFrame.Create(image(i)))
		'Create the file stream for the output in the desired image format
		Dim stream As FileStream = New FileStream(output & i.ToString() & ".Jpeg", FileMode.Create)
		'Save the stream, so that the image will be generated in the output location
		encoder.Save(stream)
	Next
End If

'Dispose the document
loadedDocument.Dispose()
loadedDocument = Nothing

{% endhighlight %}
{% endtabs %}

## Exporting with a custom image size

You can export PDF pages as images with custom width and height by passing the required size as a parameter of the [ExportAsImage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAsImage_System_Int32_System_Drawing_SizeF_System_Boolean_) method. Refer to the following code to export the pages of PDF into JPEG images. Refer to the following code to export the page at the index of 0 into JPEG image with the width and the height of 1836 and 2372 in pixels respectively.

{% tabs %}
{% highlight C# %}

//Export the particular PDF page as image at the page index of 0
BitmapSource image = pdfViewerControl.ExportAsImage(0, new SizeF(1836, 2372), false);

//Set up the output path
string output = @"..\..\Output\Image";
if (image != null)
{
	//Initialize the new Jpeg bitmap encoder
	BitmapEncoder encoder = new JpegBitmapEncoder();
	//Create the bitmap frame using the bitmap source and add it to the encoder
	encoder.Frames.Add(BitmapFrame.Create(image));
	//Create the file stream for the output in the desired image format
	FileStream stream = new FileStream(output + ".Jpeg", FileMode.Create);
	//Save the stream, so that the image will be generated in the output location
	encoder.Save(stream);
}

{% endhighlight %}
{% endtabs %}

N> To maintain the aspect ratio of output images, you are required to pass the value `true` for the `keepAspectRatio` parameter.

## Exporting with a custom image resolution

You can export PDF pages as images with a custom horizontal and vertical resolution by passing the required `DpiX` and `DpiY` values as parameters of the [ExportAsImage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAsImage_System_Int32_System_Int32_System_Single_System_Single_) method respectively. Refer to the following code to export the pages of PDF into JPEG images with the horizontal and vertical resolution of 200 respectively.

{% tabs %}
{% highlight C# %}

int startPageIndex = 0;
int endPageIndex = 3;
float dpiX=200;
float dpiY=200;

BitmapSource[] images = pdfViewerControl.ExportAsImage(startPageIndex, endPageIndex, dpiX, dpiY);
//Set up the output path
string output = @"..\..\Output\Image";
if (images != null)
{
	for (int i = 0; i < images.Length; i++)
	{
		//Initialize the new Jpeg bitmap encoder
		BitmapEncoder encoder = new JpegBitmapEncoder();
		//Create the bitmap frame using the bitmap source and add it to the encoder
		encoder.Frames.Add(BitmapFrame.Create(images[i]));
		//Create the file stream for the output in the desired image format
		FileStream stream = new FileStream(output + i.ToString() + ".Jpeg", FileMode.Create);
		//Save the stream, so that the image will be generated in the output location
		encoder.Save(stream);
	}
}

{% endhighlight %}
{% endtabs %}

N> The complete sample project of exporting the PDF pages to images using the Syncfusion PDF viewer is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-PDFViewer-Examples/tree/master/Export/PDFToImage).
