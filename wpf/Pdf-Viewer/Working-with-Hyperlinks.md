---
layout: post
title: Hyperlink Navigation in WPF Pdf Viewer control | Syncfusion
description: Learn about Hyperlink Navigation support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Hyperlink Navigation in WPF Pdf Viewer

Essential PDF Viewer provides support for URI annotations (hyperlinks) in the PDF document that enables the URI available in the PDF document to be opened in the default browser just by clicking on it. This also supports a few events that are listed in the below table.

### Events Table

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th></tr>
<tr>
<td>
HyperlinkMouseOver</td><td>
This event is triggered when the mouse pointer is placed over the hyperlink.</td><td>
N/A</td></tr>
<tr>
<td>
HyperlinkClicked</td><td>
This event is triggered when the hyperlink in the PDF document is clicked.</td><td>
HyperlinkClickedEventArgs</td></tr>
</table>


## How to disable hyperlink navigation in PDF viewer control?

We can disable the hyperlink navigation in PDF viewer control by setting the value of `Handled` in the `HyperlinkClickedEventArgs` parameter as true in the `HyperlinkClicked` Event which is available in the PdfViewerControl and PdfDocumentView class. 
Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

private void Pdfviewer_HyperlinkClicked(object sender, Syncfusion.Windows.PdfViewer.HyperlinkClickedEventArgs args)
{

  // Gets or sets the value to handle the navigation of hyperlink.
  args.Handled = true;
            
}


{% endhighlight %}

{% highlight vbnet %}

' Hooks the event handler for `HyperlinkClicked` event

'Initialize PDF Viewer.

Private pdfViewerControl As New PdfViewerControl()



'Load the PDF.

pdfViewerControl.Load("Sample.pdf")

AddHandler pdfviewer.HyperlinkClicked, AddressOf PdfViewerControl_HyperlinkClicked

Private Sub PdfViewerControl_HyperlinkClicked(obj As Object, args As Syncfusion.Windows.PdfViewer.AnnotEventArgs)

'Your code here...

End Sub

 
' Unhooks the event handler for `HyperlinkClicked` event.
RemoveHandler pdfviewer.HyperlinkClicked, AddressOf PdfViewerControl_HyperlinkClicked

{% endhighlight %}
{% endtabs %}


## How to retrieve the clicked URI from PDF viewer?

We can acquire the details of the hyperlink which is clicked in the PDF file using the `HyperlinkClickedEventArgs` in the `HyperlinkClicked` event. 
Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

private void Pdfviewer_HyperlinkClicked(object sender, Syncfusion.Windows.PdfViewer.HyperlinkClickedEventArgs args)
{
  
 //Returns the URI clicked in the PDF viewer control.
 string URI = args.Uri; 
            
}

{% endhighlight %}

{% highlight vbnet %}

' Hooks the event handler for `HyperlinkClicked` event
AddHandler pdfviewer.HyperlinkClicked, AddressOf PdfViewerControl_HyperlinkClicked

Private Sub PdfViewerControl_HyperlinkClicked(obj As Object, args As Syncfusion.Windows.PdfViewer.AnnotEventArgs)

' Returns the URI clicked in the PDF viewer control.
Dim uri As String = args.URI

End Sub


{% endhighlight %}
{% endtabs %}


## Redirecting to a different Hyperlink

We can navigate to different hyperlink irrespective of the hyperlink clicked. In order to redirect a hyperlink, we need to set the value of `Handled` parameter as true to stop the navigation of the hyperlink clicked. Then open the desired hyperlink that you want to navigate instead of the hyperlink clicked. 
Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

private void Pdfviewer_HyperlinkClicked(object sender, Syncfusion.Windows.PdfViewer.HyperlinkClickedEventArgs args)
{

 // Gets or sets the value to handle the navigation of hyperlink.
  args.Handled = true;

 // Opens the URI (www.google.com) in a default browser.
 System.Diagnostics.Process.Start("www.google.com");
             
}


{% endhighlight %}

{% highlight vbnet %}

' Hooks the event handler for `HyperlinkClicked` event.
AddHandler pdfviewer.HyperlinkClicked, AddressOf PdfViewerControl_HyperlinkClicked

Private Sub PdfViewerControl_HyperlinkClicked(obj As Object, args As Syncfusion.Windows.PdfViewer.AnnotEventArgs)

' Opens the URI (www.google.com) in a default browser.
System.Diagnostics.Process.Start("www.google.com")

End Sub


{% endhighlight %}
{% endtabs %}


## How to get notified when a mouse pointer moves over a hyperlink? 

`HyperlinkMouseOver` event will be raised when we place the mouse pointer over the URI in the PDF viewer control.
 Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkMouseOver` event.    
pdfViewerControl.HyperlinkMouseOver += PdfViewerControl_HyperlinkMouseOver;

private void Pdfviewer_HyperlinkMouseOver(object sender, EventArgs args)
{

//Your code here
            
}

// Unhooks the event handler for `HyperlinkMouseOver` event.
pdfViewerControl.HyperlinkMouseOver -= PdfViewerControl_HyperlinkMouseOver;

{% endhighlight %}

{% highlight vbnet %}

' Hooks the event handler for `HyperlinkMouseOver` event
AddHandler pdfviewer.HyperlinkMouseOver, AddressOf PdfViewerControl_HyperlinkMouseOver

Private Sub PdfViewerControl_HyperlinkMouseOver(obj As Object, args As Syncfusion.Windows.PdfViewer.AnnotEventArgs)

End Sub

 
' Unhooks the event handler for `HyperlinkMouseOver` event.
RemoveHandler pdfviewer.HyperlinkMouseOver, AddressOf PdfViewerControl_HyperlinkMouseOver

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.