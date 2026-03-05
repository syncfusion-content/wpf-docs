---
layout: post
title: Event in WPF Markdown Viewer (SfMarkdownViewer) | Syncfusion
description: Learn here all about Events support in Syncfusion MarkdownViewer control, its elements and more details.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Event in WPF Markdown Viewer (SfMarkdownViewer)

## Hyperlink Clicked event

This event is triggered when the hyperlink in the control is clicked.

## How to disable hyperlink navigation in Markdown viewer control

You can disable the hyperlink navigation in Markdown viewer control by setting the value of `Cancel` in the `MarkdownHyperlinkClickedEventArgs` parameter as true in the `HyperlinkClicked` event which is available in the PdfViewerControl and PdfDocumentView class. 
Please refer to the following example for more details.

we have introduced `Cancel` property in the event arguments to disable the hyperlink navigation based on the standards. You need to change its value to `true` to disable the navigation.

{% highlight c# %}

// Wires the event handler for `HyperlinkClicked` event.    
markdownViewer.HyperlinkClicked += MarkdownViewer_HyperlinkClicked;

private void MarkdownViewer_HyperlinkClicked(object? sender, MarkdownHyperlinkClickedEventArgs args)
{
    // Gets or sets the value to handle the navigation of hyperlink.
    args.Cancel = true;
}

{% endhighlight %}


## How to retrieve the clicked URI from Markdown viewer

You can acquire the details of the hyperlink, which is clicked in the Markdown viewer control using the `MarkdownHyperlinkClickedEventArgs` in the `HyperlinkClicked` event. 
Please refer to the following example for more details.

{% highlight c# %}

// Wires the event handler for `HyperlinkClicked` event.    
markdownViewer.HyperlinkClicked += MarkdownViewer_HyperlinkClicked;

private void MarkdownViewer_HyperlinkClicked(object? sender, MarkdownHyperlinkClickedEventArgs args)
{
    //Returns the URL clicked in the Markdown viewer control.
    string URL = args.Url;
}

{% endhighlight %}
