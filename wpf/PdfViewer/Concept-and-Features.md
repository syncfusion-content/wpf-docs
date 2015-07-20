---
layout: post
title: Concept-and-Features
description: concept and features
platform: wpf
control: PDF Viewer
documentation: ug
---

## Concept and Features

Essential PDF Viewer can display PDF files, and print and export the pages as raster images. This section explains about the various functionalities available in the Essential PDF viewer for WPF.

### Viewing PDF Files 

A PDF can be loaded into the PDF Viewer either through the File Open dialog available in the toolbar or through the Load method. It also requests passwords to open encrypted documents.

[C#]

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Template.pdf");



[VB.NET]

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Template.pdf")



You can load an encrypted document by using the overload in the Load method.

[C#]

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1.Load("Template.pdf", "password");



[VB.NET]

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1.Load("Template.pdf", "password")



You can also load the PDF document by setting its path to the ItemSource property

[C#]

//Initialize PDF Viewer.

PdfViewerControl pdfViewer1 = new PdfViewerControl();



//Load the PDF.

pdfViewer1. ItemSource="Template.pdf";



[VB.NET]

'Initialize PDF Viewer.

Private pdfViewer1 As New PdfViewerControl()



'Load the PDF.

pdfViewer1. ItemSource = "Template.pdf"

### Saving the PDF document

PDF Viewer also allows you to save the PDF document that is being displayed in the PDF Viewer. The following code example illustrates the same.

[C#]



//Acquire the document loaded into the PDF Viewer

PdfLoadedDocument lDoc = pdfviewer1.LoadedDocument;



//Save the document

lDoc.Save("Sample.pdf");



[VB.NET]

'Acquire the document loaded into the PDF Viewer

Dim lDoc As PdfLoadedDocument = pdfviewer1.LoadedDocument



'Save the document

lDoc.Save("Sample.pdf")

### Navigating through the pages

PDF Viewer allows you to navigate through the pages of the PDF document. The following code example illustrates the navigation to page 2 of the PDF document.

[C#]

//Navigate to page 2

pdfviewer1.GotoPage(2);



[VB.NET]

'Navigate to page 2

pdfviewer1.GotoPage(2)

### Magnifying PDF documents

PDF Viewer allows you to magnify the PDF document that is being displayed. The following code examples can be used to perform this action.

[C#]

//Magnify the document to 150%

pdfviewer1.ZoomTo(150);



[VB.NET]

'Magnify the document to 150%

pdfviewer1.ZoomTo(150)



The magnification can also be set by updating the Zoom property of the PDF Viewer.

[C#]

//Magnify the document to 150%

pdfviewer1.Zoom = 250;



[VB.NET]

'Magnify the document to 150%

pdfviewer1.Zoom = 250



Current magnification percentage of the PDF Viewer can be acquired with the use of the property ZoomPercentage

[C#]

//Acquire current zoom percentage

int currentZoomPercentage = pdfviewer1.ZoomPercentage;



[VB.NET]

' Acquire current zoom percentage 

Dim currentZoomPercentage As Integer = pdfviewer1.ZoomPercentage



Zoom mode of the PDF viewer can be set using the following code example.

[C#]

//Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth;



[VB.NET]

'Setting zoom mode to the PDF Viewer

pdfviewer1.ZoomMode = Syncfusion.Windows.PdfViewer.ZoomMode.FitWidth

### Acquiring total number of pages

PDF Viewer provides the total number of the pages in the PDF document that is being loaded into the PDF Viewer. This value can be acquired with the help of PageCount property in the PDF Viewer control, the following code example illustrates the same.

[C#]

// Acquiring the total number of pages in the document being loaded  

int pageCount = pdfviewer1.PageCount;





[VB.NET]

'Acquiring the total number of pages in the document being loaded 

Dim pageCount As Integer = pdfviewer1.PageCount

### Changing the color of the Loading Indicator

PDF Viewer allows you to change the color of the loading indicator displayed when loading the PDF document. The following code example illustrates the same.

[C#]

// Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0);



[VB.NET]

'Changing the color of the loading indicator to Red

pdfviewer1.LoadingIndicator.LoaderColor = System.Windows.Media.Color.FromArgb(255, 255, 0, 0)

### Changing the text displayed in the loading indicator

PDF Viewer allows you to change the text displayed in the loading indicator. The following code example illustrates the same.

[C#]

// Changing the text displayed in the loading indicator

pdfviewer1. LoadingIndicator.LoadingMessage = "Document loading";





[VB.NET]

'Changing the text displayed in the loading indicator

pdfviewer1.LoadingIndicator.LoadingMessage = "Document loading"



### Toggling visibility of the tool bar

PDF Viewer supports showing and hiding toolbar, when you feel to customize the toolbar, you can hide the default toolbar of the PDF Viewer. The following code example hides the default toolbar in the PDF Viewer control.

[C#]

// Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = false;





[VB.NET]

' Hiding the default toolbar of the PDF Viewer

pdfviewer1.ShowToolbar = False

### Toggling visibility of the scroll bar

PDF Viewer supports showing and hiding scrollbar, when you feel to use the PDF Viewer only with the touch support, you can hide the default scrollbars of the PDF Viewer. The following code example hides the scrollbar in the PDF Viewer control.

[C#]

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = false;





[VB.NET]

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.ShowScrollbar = False

### Acquiring current page being displayed

PDF Viewer supports acquiring the index of the page being displayed in the PDF Viewer at any moment. The following code example illustrates the same.

[C#]

// Acquiring the number of page being displayed in the Viewer  

int pageCount = pdfviewer1.CurrentPageIndex;





[VB.NET]

' Acquiring the number of page being displayed in the Viewer  

Dim pageCount As Integer = pdfviewer1. CurrentPageIndex

### Enabling and Disabling Notification bar

Notification bar is a part of the PDF Viewer that is used to display when an unexpected error occurs in the PDF Viewer control. You can suppress the display of the Notification bar by setting the EnableNotificationBar property to false. The following code example illustrate the same.

[C#]

// Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= false;



[VB.NET]

' Hiding the scrollbar of the PDF Viewer

pdfviewer1.EnableNotificationBar= False

### Printing PDF Files 

PDF Viewer allows printing loaded PDFs using the Print button in the toolbar. The following Print dialog opens upon triggering the Print button.

{ ![](Concept-and-Features_images/Concept-and-Features_img1.png) | markdownify }
{:.image }


#### Silent Printing

The PrintDocument property of PdfViewerControl returns System.Drawing.Printing.PrintDocument that helps to complete printing using PrintDialog. This type of printing can be used when trying to print the PDF document with the custom printer settings. The following code sample demonstrates this:

[C#]

PrintDialog dialog = new PrintDialog();

dialog.AllowPrintToFile = true;         

dialog.Document = viewer.PrintDocument;

dialog.Document.Print();



[VB.NET]

Dim dialog As New PrintDialog()

dialog.AllowPrintToFile = True

dialog.Document = viewer.PrintDocument

dialog.Document.Print()



When you prefer to perform Silent printing with the default printer settings, then using Print method in the PDF Viewer control is the best approach. The following code example illustrates the same.

[C#]

// Printing document using Print method

pdfviewer1.Print();





[VB.NET]

' Printing document using Print method

pdfviewer1.Print()

### Exporting PDF

#### Exporting PDFs as Raster Images

Essential PDF Viewer allows selected pages to be exported as raster images. Exporting can be done using the ExportAsImage method. This option helps to convert a PDF into an image.

[C#]

Bitmap img = pdfViewer1.ExportAsImage(0);



// Save the image.

img.Save("Sample.png", ImageFormat.Png);



[VB.NET]

Dim img As Bitmap = pdfViewer1.ExportAsImage(0)



' Save the image.

img.Save("Sample.png", ImageFormat.Png)



You can also specify the page range instead of converting each page.

[C#]

Bitmap[] img = pdfViewer1.ExportAsImage(0, 3);



[VB.NET]

Dim img() As Bitmap = pdfViewer1.ExportAsImage(0, 3)

#### Exporting PDFs as Vector Images

Exporting PDFs as vector images can be done using the ExportAsMetafile method. The following code sample demonstrates how a PDF document can be exported as a metafile.

[C#]

Metafile img = pdfViewer1.ExportAsMetafile(0);



// Save the image

img.Save("Sample.emf", ImageFormat.Emf);



[VB.NET]

Dim img As Metafile = pdfViewer1.ExportAsMetafile(0)



' Save the image

img.Save("Sample.emf", ImageFormat.Emf)



You can also specify the page range instead of converting each page individually.

[C#]

Metafile[] img = pdfViewer1.ExportAsMetafile(0, 3);



[VB.NET]

Dim img() As Metafile = pdfViewer1.ExportAsMetafile(0, 3)

### Searching Text

Essential PDF Viewer allows you to search and highlight the text in the PDF document. The search box appears when Ctrl+F is pressed and searches the text in the PDF document as displayed in the following screenshot.

{ ![C:/Users/Suresh/Desktop/UG Pravin/TextSearchWPF.png](Concept-and-Features_images/Concept-and-Features_img2.png) | markdownify }
{:.image }


The PDF Viewer control also supports searching text in the PDF document with the help of the following API. The FindText method returns true when the text given is found in the document. The dictionary contains the page index and the list of rectangular coordinates of the text found in that page. The following code example illustrates how text search can be achieved in the PDF Viewer control.

[C#]

bool IsMatchFound;

pdfViewerControl1.Load("../../Data/Barcode.pdf");



//Get the occurrences of the target text and location.

Dictionary<int, List<RectangleF>> 

          textSearch = new Dictionary<int, List<RectangleF>>();

IsMatchFound = pdfViewerControl1.FindText("targetText", out textSearch);



[VB.NET]

Dim IsMatchFound As Boolean

pdfViewerControl1.Load("../../Data/Barcode.pdf")



'Get the occurrences of the target text and location.

Dim textSearch As New Dictionary(Of Integer, List(Of RectangleF))()

IsMatchFound = pdfViewerControl1.FindText("targetText", textSearch)

### Working with Hyperlinks 

Essential PDF Viewer provides support for URI annotations (hyperlinks) in the PDF document that enables the URI available in the PDF document to be opened in the browser just by clicking it. This also supports a few events that are listed in the previous table.

_Event Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th></tr>
<tr>
<th>
HyperLinkMouseHover</th><th>
This event is triggered when the mouse pointer is placed over the URL.</th><th>
N/A</th><th>
N/A</th></tr>
<tr>
<th>
HyperLinkMouseClicked</th><th>
This event is triggered when the URL in the PDF document is clicked.</th><th>
N/A</th><th>
N/A</th></tr>
</table>
### Events Supported in the PDF Viewer

The Essential PDF viewer for WPF also provides several events that enables you to design/modify the existing behavior according to your requirement. The following table lists out the events available in the PDF viewer and their functionalities.

_Events Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th></tr>
<tr>
<th>
DocumentLoaded</th><th>
This event is triggered after the PDF is successfully loaded.</th><th>
N/A</th><th>
N/A</th></tr>
<tr>
<th>
HyperLinkMouseHover</th><th>
This event is triggered when the mouse pointer is placed over the URL.</th><th>
N/A</th><th>
N/A</th></tr>
<tr>
<th>
HyperLinkMouseClicked</th><th>
This event is triggered when the URL in the PDF document is clicked.</th><th>
N/A</th><th>
N/A</th></tr>
</table>


In spite of the above event the following events are supported in the PdfDocumentView control.

_Event Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th></tr>
<tr>
<th>
NavigationButtonStatesChanged</th><th>
This event is triggered when there is a change in the states of the navigation buttons</th><th>
N/A</th><th>
N/A</th></tr>
<tr>
<th>
CurrentPageChanged</th><th>
This event is triggered when there is a change in the index of the page being displayed</th><th>
N/A</th><th>
N/A</th></tr>
<tr>
<th>
ZoomChanged</th><th>
This event is triggered when there is change in the current zoom factor. </th><th>
N/A</th><th>
N/A</th></tr>
</table>


