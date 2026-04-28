---
layout: post
title: Event in WPF Markdown Viewer (SfMarkdownViewer) | Syncfusion
description: Learn here all about events support in Syncfusion MarkdownViewer control, its elements and more details.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Event in WPF Markdown Viewer (SfMarkdownViewer)

HyperlinkClicked is triggered when a Markdown link is clicked, providing the URL via MarkdownHyperlinkClickedEventArgs and allowing navigation to be canceled.

## HyperlinkClicked

The HyperlinkClicked event is triggered whenever a hyperlink in the Markdown content is clicked. This event provides access to the URL being navigated to and allows developers to cancel the default navigation behavior.
The URL link and its details are passed through the MarkdownHyperlinkClickedEventArgs. This argument provides the following details:

**URL** : Gets the URL of the clicked hyperlink.
**Cancel** : Gets or sets whether to cancel the default navigation behavior.

## Disable hyperlink navigation

You can disable the hyperlink navigation in Markdown viewer control by setting the value of `Cancel` in the `MarkdownHyperlinkClickedEventArgs` parameter as true in the `HyperlinkClicked` event.
Please refer to the following example for more details.

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

You can acquire the details of the hyperlink, which is clicked in the Markdown viewer control using the arguments of `HyperlinkClicked` event. 
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
