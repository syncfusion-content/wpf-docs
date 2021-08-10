---
layout: post
title: Hyperlink Navigation in WPF Pdf Viewer control | Syncfusion
description: Learn about Hyperlink Navigation support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Hyperlink Navigation in WPF Pdf Viewer

Essential PDF Viewer provides support for URI annotations (hyperlinks) in the PDF document that enables the URI available in the PDF document to be opened in the default browser just by clicking on it. This also supports a few events that are listed in the previous table.

### Events Table

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th></tr>
<tr>
<td>
HyperlinkMouseOver</td><td>
This event is triggered when the mouse pointer is placed over the URL.</td><td>
N/A</td><td>
N/A</td></tr>
<tr>
<td>
HyperlinkClicked</td><td>
This event is triggered when the URL in the PDF document is clicked.</td><td>
N/A</td><td>
N/A</td></tr>
</table>


## How to disable hyperlink navigation in PDF viewer control?

We can disable the hyperlink navigation in PDF viewer control by wiring the event [HyperlinkClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) which is available in PdfViewerControl and PdfDocumentView like below,

{% tabs %}
{% highlight c# %}

//Initialize PDF Viewer.

PdfViewerControl pdfViewerControl = new PdfViewerControl();



//Load the PDF.

pdfViewerControl.Load("Sample.pdf");

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

public void PdfViewerControl_HyperlinkClicked(object sender, AnnotEventArgs e)
{

//Your code here...
            
}

// Unhooks the event handler for `HyperlinkClicked` event.
pdfViewerControl.HyperlinkClicked -= PdfViewerControl_HyperlinkClicked;

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

We can get the URI which is clicked in the PDF viewer control from the [AnnotEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.AnnotEventArgs.html) which is passed as a parameter of the [HyperlinkClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) event. Please refer the below example for more details.

We can navigate to different URL irrespective of the URI clicked in the PDF viewer. Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

public void PdfViewerControl_HyperlinkClicked(object sender, AnnotEventArgs args)
{
  
 //Returns the URI clicked in the PDF viewer control.
 string URI = args.URI; 
            
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


## How to redirect to a different URL?

We can navigate to different URL irrespective of the URI clicked in the PDF viewer. Please refer the below example for more details.

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkClicked` event.    
pdfViewerControl.HyperlinkClicked += PdfViewerControl_HyperlinkClicked;

public void PdfViewerControl_HyperlinkClicked(object sender, AnnotEventArgs e)
{
 
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


## How to identify hyperlink detection? 

[HyperlinkMouseOver](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) event will be raised when we place the mouse pointer over the URI in the PDF viewer control. 

{% tabs %}
{% highlight c# %}

// Hooks the event handler for `HyperlinkMouseOver` event.    
pdfViewerControl.HyperlinkMouseOver += PdfViewerControl_HyperlinkMouseOver;

public void PdfViewerControl_HyperlinkMouseOver(object sender, AnnotEventArgs e)
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