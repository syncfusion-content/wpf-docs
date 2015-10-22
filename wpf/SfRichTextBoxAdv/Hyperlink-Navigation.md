---
layout: post
title: Hyperlink-Navigation
description: hyperlink navigation
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Hyperlink Navigation

RichTextBoxAdv provides support for inserting or editing a hyperlink field and the RequestNavigate event to handle hyperlink navigation. It is easy to customize hyperlink navigation functionality by using the RequestNavigate event. This event is triggered when the hyperlink field in SfRichTextBoxAdv is tapped or left button of the mouse is clicked with the Ctrl key.

_Table_ _1_: _Hyperlink Navigation properties_

<table>
<tr>
<th>
Properties</th><th>
Types</th><th>
Class</th><th>
Description</th></tr>
<tr>
<td>
Hyperlink</td><td>
Hyperlink</td><td>
RequestNavigateEventArgs</td><td>
Specifies the hyperlink for navigation.</td></tr>
<tr>
<td>
NavigationLink</td><td>
string</td><td>
Hyperlink</td><td>
Specifies the navigation link.</td></tr>
<tr>
<td>
LinkType</td><td>
HyperlinkType</td><td>
Hyperlink</td><td>
Specifies the navigation link type (File, Webpage, Email, or Bookmark).</td></tr>
</table>


_Table_ _2_: _Hyperlink Navigation Event_

<table>
<tr>
<th>
Event</th><th>
Parameter</th><th>
Class</th><th>
Description</th></tr>
<tr>
<td>
RequestNavigate</td><td>
RequestNavigateEventArgs</td><td>
SfRichTextBoxAdv </td><td>
Occurs when a Hyperlink in the SfRichTextBoxAdv document is clicked or tapped.</td></tr>
</table>


The following code example demonstrates how to define a Hyperlink field in the RichTextBoxAdv document by using XAML.

{% highlight html %}

<syncfusion:ParagraphAdv >

    <syncfusion:FieldBeginAdv></syncfusion:FieldBeginAdv>

    <syncfusion:SpanAdv Text=" HYPERLINK &quot;http://www.syncfusion.com&quot; "></syncfusion:SpanAdv>

    <syncfusion:FieldSeparatorAdv></syncfusion:FieldSeparatorAdv>

    <syncfusion:SpanAdv Text="Syncfusion">

        <syncfusion:SpanAdv.CharacterFormat>

            <syncfusion:CharacterFormat Underline="Single" FontColor="#ff0563c1"/>

        </syncfusion:SpanAdv.CharacterFormat>

    </syncfusion:SpanAdv>

    <syncfusion:FieldEndAdv></syncfusion:FieldEndAdv>

</syncfusion:ParagraphAdv>

{% endhighlight %}

The following code example demonstrates how to implement the RequestNavigate event handler for the RichTextBoxAdv instance.

{% highlight c# %}

//Hooks the event handler for RequestNavigate event.

richTextBoxAdv.RequestNavigate += richTextBoxAdv_RequestNavigate;



/// <summary>

/// Handles the RequestNavigate event of the richTextBoxAdv control.

/// </summary>

/// <param name="obj">The source of the event.</param>

/// <param name="args">The <see cref="RequestNavigateEventArgs"/> instance containing the event data.</param>

void richTextBoxAdv_RequestNavigate(object obj, RequestNavigateEventArgs args)

{

    if (args.Hyperlink.LinkType == Syncfusion.Windows.Controls.RichTextBoxAdv.HyperlinkType.Webpage || args.Hyperlink.LinkType == Syncfusion.Windows.Controls.RichTextBoxAdv.HyperlinkType.Email)
    {
        Uri uri = new Uri(args.Hyperlink.NavigationLink);
        Process.Start(new ProcessStartInfo(uri.AbsoluteUri));
    }
    else if (args.Hyperlink.LinkType == HyperlinkType.File && File.Exists(args.Hyperlink.NavigationLink))
        Process.Start(args.Hyperlink.NavigationLink);
}

{% endhighlight %}