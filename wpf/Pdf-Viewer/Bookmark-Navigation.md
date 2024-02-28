---
layout: post
title: Bookmark Navigation in WPF Pdf Viewer control | Syncfusion
description: Learn about Bookmark Navigation support in Syncfusion WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Bookmark Navigation in WPF Pdf Viewer

PDF Viewer control allows users to navigate to the bookmarks present in the loaded PDF document at UI level. 


## Displaying bookmark
The bookmark are displayed by clicking the bookmark icon in the left pane.By default the bookmark pane expand is false. To display bookmark pane from code behind,  use the following code example.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
	PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
  	pdfviewer.BookMarkSettings.IsExpanded = true;
}

{% endhighlight %}


{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
	pdfviewer.BookMarkSettings.IsExpanded = true
End Sub

{% endhighlight %}
{% endtabs %}

## Steps to perform bookmark navigation in PdfViewerControl.

1.	Open the bookmarks contained PDF document to enable the bookmark button in `PdfViewerControl`.
2.	Clicking on the bookmark button from the left pane, will list the bookmarks present in the PDF document.
3.	To jump to a specific section, click its name in the bookmark pane.
4.	If the bookmark has some children, you can explore them by clicking on the “+” button to the left of it.

![WPF PDF Viewer Bookmark Button](Bookmark_Navigation_images/wpf-pdf-viewer-bookmark-button.png)  

## Programmatically navigate to a bookmark destination

The user can navigate to the desired bookmark destination using the [GoToBookmark](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_GoToBookmark_Syncfusion_Pdf_Interactive_PdfBookmark_) method of PDF Viewer after loading the document. You should provide the target/destination bookmark as the parameter to this method. Refer to the following code sample to retrieve the bookmarks collection in the document and navigate to a bookmark.

{% tabs %}
{% highlight c# %}

void GoToBookmark()
{
    //Get the loadedDocument object from PDF Viewer
    PdfLoadedDocument pdfLoadedDocument = pdfViewer.LoadedDocument;
    //Get the complete bookmarks in the PDF.
    PdfBookmarkBase bookmarks = pdfLoadedDocument.Bookmarks;
    //In this example, we get the first bookmark in the PDF bookmarks collection at the index of 0.
    PdfBookmark firstBookmark = bookmarks[0];

    //Navigates to the first bookmark present in the PDF.
    pdfViewer.GoToBookmark(firstBookmark);
}

{% endhighlight %}
{% endtabs %}

The user can also navigate to the child bookmarks in the PDF Viewer. Please refer to the following code sample to retrieve the child bookmarks in the document and navigate to the bookmark.

{% tabs %}
{% highlight c# %}

void GoToChildBookmark()
{
    //Get the loadedDocument object from PDF Viewer
    PdfLoadedDocument pdfLoadedDocument = pdfViewer.LoadedDocument;
    //Get the complete bookmarks in the PDF.
    PdfBookmarkBase bookmarks = pdfLoadedDocument.Bookmarks;
    //Gets the fourth bookmark in the PDF bookmarks collection at the index of 3.
    PdfBookmark fourthBookmark = bookmarks[3];
    //Check whether it has child bookmarks.
    if (fourthBookmark.Count > 0)
    {
        //Navigates to the first child of the fourth bookmark in the PDF.
        pdfViewer.GoToBookmark(bookmarks[3][0]);
    }
}

{% endhighlight %}
{% endtabs %}

The user needs to call the above methods after the document is loaded. You can wire the [DocumentLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DocumentLoaded) event of PDF Viewer to notify you when the document is loaded, as shown in the following code sample:

{% tabs %}
{% highlight c# %}

//Constructor
public MainWindow()
{
    InitializeComponent();
    //Wire the DocumentLoaded event of PDF Viewer
    pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
    //Load the PDF file in PDF Viewer.
    pdfViewer.Load("../../LayerAndBookmarks.pdf");
}

//Handle the DocumentLoaded event of PDF Viewer
private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
{
    //Call the logic for bookmark navigation
    GoToBookmark();
}

{% endhighlight %}
{% endtabs %}

## Enabling and disabling bookmark feature

You can enable and disable the bookmark button from the built-in toolbar using the `IsBookmarkEnabled` property available in `PdfViewerControl`.

<table>
<tr>
<th>
Property</th><th>
Action</th></tr>
<tr>
<td>
{{'[IsBookmarkEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_IsBookmarkEnabled)'| markdownify }}</td><td>
Enables or disables the bookmark feature.</td></tr>
</table>

This property removes the bookmark button and disable the bookmark feature, when it is set to false and vice versa.

{% tabs %}
{% highlight c# %}

//Bookmark feature is disabled
pdfViewerControl.IsBookmarkEnabled = false;

{% endhighlight %}
{% highlight VB %}

'Bookmark feature is disabled
pdfViewerControl.IsBookmarkEnabled = false

{% endhighlight %}
{% endtabs %}

The following screenshot shown the Bookmark navigation in `PdfViewerControl`,

![WPF PDF Viewer Enabling and Disabling Bookmark Feature](Bookmark_Navigation_images/wpf-pdf-viewer-enabling-and-disabling-bookmark-feature.png)


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.