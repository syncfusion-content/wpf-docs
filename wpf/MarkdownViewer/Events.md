---
layout: post
title: Event in WPF Markdown Viewer (SfMarkdownViewer) | Syncfusion
description: Learn here all about events support in Syncfusion MarkdownViewer control, its elements and more details.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Event in WPF Markdown Viewer (SfMarkdownViewer)

This section explains how to handle hyperlink interactions in the SfMarkdownViewer using the HyperlinkClicked event.
The HyperlinkClicked event is triggered when a hyperlink in the Markdown content is clicked. It provides access to the clicked URL and allows you to control or cancel the default navigation behavior.

## HyperlinkClicked Event

The HyperlinkClicked event provides details about the clicked hyperlink through the MarkdownHyperlinkClickedEventArgs.

This event argument exposes the following properties:

**URL** : Gets the URL of the clicked hyperlink.
**Cancel** : Gets or sets a value indicating whether to cancel the default navigation behavior

## Disable hyperlink navigation

You can disable hyperlink navigation by setting the Cancel property of the `MarkdownHyperlinkClickedEventArgs` to true in the `HyperlinkClicked` event handler. 

{% highlight c# %}

// Wires the event handler for `HyperlinkClicked` event.    
markdownViewer.HyperlinkClicked += MarkdownViewer_HyperlinkClicked;

private void MarkdownViewer_HyperlinkClicked(object? sender, MarkdownHyperlinkClickedEventArgs args)
{
    // Gets or sets the value to handle the navigation of hyperlink.
    args.Cancel = true;
}

{% endhighlight %}

## Retrieve the clicked URI

You can retrieve the URL of the clicked hyperlink by accessing the Url property of the event arguments.

{% highlight c# %}

// Wires the event handler for `HyperlinkClicked` event.    
markdownViewer.HyperlinkClicked += MarkdownViewer_HyperlinkClicked;

private void MarkdownViewer_HyperlinkClicked(object? sender, MarkdownHyperlinkClickedEventArgs args)
{
    //Returns the URL clicked in the Markdown viewer control.
    string URL = args.Url;
}

{% endhighlight %}
