---
title: Hyperlink
description: hyperlink
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: hyperlink
---
# Hyperlink

The SfRichTextBoxAdv supports hyperlink field similar to the Microsoft Word. You can link part of the document content to internet or file location, mail address or any text.
The following code example illustrates how to insert a hyperlink field.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:ParagraphAdv><br/><RichTextBoxAdv:FieldBeginAdv></RichTextBoxAdv:FieldBeginAdv><br/><RichTextBoxAdv:SpanAdv Text=" HYPERLINK &quot;http://www.syncfusion.com&quot; "></RichTextBoxAdv:SpanAdv><br/><RichTextBoxAdv:FieldSeparatorAdv></RichTextBoxAdv:FieldSeparatorAdv><br/><RichTextBoxAdv:SpanAdv Text="Syncfusion"><br/><RichTextBoxAdv:SpanAdv.CharacterFormat><br/><RichTextBoxAdv:CharacterFormat Underline="Single" FontColor="#ff0563c1"/><br/></RichTextBoxAdv:SpanAdv.CharacterFormat><br/></RichTextBoxAdv:SpanAdv><br/><RichTextBoxAdv:FieldEndAdv></RichTextBoxAdv:FieldEndAdv><br/></RichTextBoxAdv:ParagraphAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Appends the field start.<br/>paragraphAdv.Inlines.Add(new FieldBeginAdv());<br/>// Appends the field code.<br/>SpanAdv fieldCode = new SpanAdv();<br/>string url = "www.syncfusion.com";<br/>fieldCode.Text = " HYPERLINK \"" + url + "\" ";<br/>paragraphAdv.Inlines.Add(fieldCode);<br/>// Appends the field separator<br/>paragraphAdv.Inlines.Add(new FieldSeparatorAdv());<br/>// Appends the field result.<br/>SpanAdv fieldResult = new SpanAdv();<br/>fieldResult.Text = "Syncfusion";<br/>fieldResult.CharacterFormat.Underline = Underline.Single;<br/>fieldResult.CharacterFormat.FontColor = Color.FromArgb(0xff, 0x05, 0x63, 0xc1);<br/>paragraphAdv.Inlines.Add(fieldResult);<br/>// Appends the field end.<br/>paragraphAdv.Inlines.Add(new FieldEndAdv());<br/></td></tr>
</table>
The following code example illustrates how to insert hyperlink field into SfRichTextBoxAdv Document through UI command.
{% tabs %}
{% highlight c# %}
<Button Content="Insert Hyperlink" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertHyperlinkCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="www.google.com"/>


{% endhighlight %}

## Hyperlink Navigation

The SfRichTextBoxAdv supports event to identify whenever hyperlink navigation is requested. This allows you to easily customize the hyperlink navigation functionality.
The following code example demonstrates how to customize hyperlink navigation functionality for the SfRichTextBoxAdv instance.
{% highlight c# %}
// Hooks the event handler for RequestNavigate event.
richTextBoxAdv.RequestNavigate += RichTextBoxAdv_RequestNavigate;
/// <summary>
/// Handles the RequestNavigate event of the richTextBoxAdv control.
/// </summary>
/// <param name="obj">The source of the event.</param>
/// <param name="args">The <see cref="RequestNavigateEventArgs"/> instance containing the event data.</param>
private void RichTextBoxAdv_RequestNavigate(object obj, Syncfusion.Windows.Controls.RichTextBoxAdv.RequestNavigateEventArgs args)
{
if (args.Hyperlink.LinkType == HyperlinkType.Webpage || args.Hyperlink.LinkType == HyperlinkType.Email)
Process.Start(new ProcessStartInfo(new Uri(args.Hyperlink.NavigationLink).AbsoluteUri));
else if (args.Hyperlink.LinkType == HyperlinkType.File && File.Exists(args.Hyperlink.NavigationLink))
Process.Start(args.Hyperlink.NavigationLink);
}
// Unhooks the event handler for RequestNavigate event.
richTextBoxAdv.RequestNavigate -= RichTextBoxAdv_RequestNavigate;


{% endhighlight %}

{% endtabs %}
