---
layout: post
title: Text Formatting Using SpanAdv in WPF RichTextBoxAdv | Syncfusion
description: Learn here all about Text Formatting Using SpanAdv support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
 documentation: ug
---

# Text Formatting Using SpanAdv in WPF RichTextBoxAdv (Classic)

As Inline will be the content property of ParagraphAdv, SpanAdv can be added only inside the ParagraphAdv. Every ParagraphAdv can keep _n_ number of inline elements inside it. It allows you to display the formatted text using advanced features like font size, font family, strikethrough, and baseline.

### Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
Text </td><td>
Contains the text information.</td><td>
Dependency Property</td><td>
String</td></tr>
<tr>
<td>
Baseline</td><td>
Indicates whether the inline’s text is subscript or superscript.</td><td>
Dependency Property</td><td>
Baseline</td></tr>
<tr>
<td>
FontFamily</td><td>
Specifies the font family of the text.</td><td>
Dependency Property</td><td>
FontFamily</td></tr>
<tr>
<td>
FontSize</td><td>
Specifies the size of the font.</td><td>
Dependency Property.</td><td>
Double</td></tr>
<tr>
<td>
Foreground</td><td>
Designates the font color.</td><td>
Dependency Property</td><td>
Color</td></tr>
<tr>
<td>
HighlightColor</td><td>
Designates the highlight color of the text.</td><td>
Dependency Property</td><td>
Color</td></tr>
<tr>
<td>
Strikethrough</td><td>
Shows whether the text has SingleStrikeThrough or DoubleStrikeThrough.</td><td>
Dependency Property</td><td>
StrikeThrough</td></tr>
<tr>
<td>
FontWeight</td><td>
Indicates the font weight of the text.</td><td>
Dependency Property</td><td>
FontWeight</td></tr>
<tr>
<td>
Underline</td><td>
Indicates whether the text should be underlined.</td><td>
Dependency Property</td><td>
Underline</td></tr>
</table>


## Adding SpanAdv to an Application

SpanAdv can be added directly to an application using the following code snippet:


{% tabs %}
{% highlight xaml %}


<syncfusion:RichTextBoxAdv Height="300" Width="400" x:Name="richtext">            
<syncfusion:DocumentAdv>                
<syncfusion:SectionAdv>                   
 <syncfusion:ParagraphAdv>                       
 <syncfusion:SpanAdv Text="This is Span text"/>                   
 </syncfusion:ParagraphAdv>               
 </syncfusion:SectionAdv>           
 </syncfusion:DocumentAdv>       
 </syncfusion:RichTextBoxAdv>
{% endhighlight %}

{% highlight C# %}

          
 RichTextBoxAdv richtext = new RichTextBoxAdv();          
 DocumentAdv document = new DocumentAdv();           
 SectionAdv section = new SectionAdv();           
 ParagraphAdv paragraph = new ParagraphAdv();           
 SpanAdv span = new SpanAdv();           
 span.Text = "This is span text";           
 paragraph.Inlines.Add(span);           
 section.Blocks.Add(paragraph);           
 document.Sections.Add(section);           
 richtext.Document = document;

{% endhighlight %}
{% endtabs %}
