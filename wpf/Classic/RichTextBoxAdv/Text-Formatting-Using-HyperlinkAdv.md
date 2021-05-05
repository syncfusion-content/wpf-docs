---
layout: post
title: Text Formatting Using HyperlinkAdv in WPF RichTextBoxAdv | Syncfusion
description: Learn here all about Text Formatting Using HyperlinkAdv support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Text Formatting Using HyperlinkAdv in WPF RichTextBoxAdv (Classic)

HyperlinkAdv can be kept only inside the ParagraphAdv since the content property of ParagraphAdv is Inline. It allows you to display the formatted text using advanced features like NavigationUrl and TargetType. It simply differs by these properties when compared to SpanAdv.

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
Indicates whether the inline text is subscript or superscript.</td><td>
Dependency Property</td><td>
Baseline</td></tr>
<tr>
<td>
NavigateURL</td><td>
Holds the URL to which the page navigates to.</td><td>
Dependency Property</td><td>
String</td></tr>
<tr>
<td>
TargetType</td><td>
Indicates whether to open the link in the same window or in a new window.</td><td>
Dependency Property</td><td>
HyperlinkTargetType</td></tr>
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
Dependency Property</td><td>
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

##  Add HyperlinkAdv to an Application

HyperlinkAdv can be added directly to an application by using the following code snippet:

{% tabs %}

{% highlight xaml %}


<syncfusion:RichTextBoxAdv Height="300" Width="400" x:Name="richtext">            
<syncfusion:DocumentAdv>                
<syncfusion:SectionAdv>                    
<syncfusion:ParagraphAdv>                       
 <syncfusion:HyperlinkAdv Text="This is Hyperlink text"/>                   
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
 HyperlinkAdv hyperlink = new HyperlinkAdv();         
 hyperlink.Text = "This is Hyperlink text";          
 paragraph.Inlines.Add(hyperlink);           
 section.Blocks.Add(paragraph);           
 document.Sections.Add(section);           
 richtext.Document = document;
{% endhighlight %}
 

{% endtabs %}
