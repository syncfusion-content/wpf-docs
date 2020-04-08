---
layout: post
title: Exporting PDF | PDF Viewer | Wpf | Syncfusion
description: Convert pages of a PDF file into JPG, PNG, TIFF, and BMP formats using PDF Viewer WPF. The scaler exportation comes with the customization of dimension and DPI. 
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting PDF

Essential PDF Viewer allows exporting pages of a PDF file into JPG, PNG, TIFF, and BMP formats using [ExportAsImage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ExportAsImage.html) methods. This option helps to convert PDF pages into images.

## Export a page of the PDF file into image

You can export a single page of the PDF file into image by passing the page index as a parameter of the [ExportAsImage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ExportAsImage(Int32).html) method. Refer to the following code to export a single page of PDF into JPEG image.

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

## Export a specific range of PDF pages into images

You can export a specific range of PDF pages into images by passing the start and end page indexes as parameters of the [ExportAsImage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PdfViewer.WPF~Syncfusion.Windows.PdfViewer.PdfViewerControl~ExportAsImage(Int32,Int32).html) method. Refer to the following code to export the pages of PDF into JPEG images.

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

N> You can follow a similar step for exporting PDF into images in all the other image formats.