---
layout: post
title: Paragraph Alignment and Indentation in WPF RichTextBoxAdv | Syncfusion
description: Learn here all about Paragraph Alignment and Indentation support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
 documentation: ug
---

# Paragraph Alignment and Indentation in WPF RichTextBoxAdv (Classic)

The paragraph alignment and indentation features allow you to define content in paragraphs. They can be added only inside the sections. We can keep _n_ number of paragraphs inside SectionAdv. Each paragraph may contain inline elements such as SpanAdv, HyperlinkAdv, ImageContainerAdv, and UIContainerAdv. 

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
TextAlignment</td><td>
Aligns the paragraph to left, right, center, and justified.</td><td>
Dependency Property</td><td>
TextAlignment</td></tr>
<tr>
<td>
AfterSpacing</td><td>
Changes the spacing between the current paragraph and the next paragraph.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
BeforeSpacing</td><td>
Changes the spacing between the current paragraph and previous paragraph.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
LineSpacing</td><td>
Changes the spacing between lines of text.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
LeftIndent</td><td>
Specifies the indent at the left side of the paragraph.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
RightIndent</td><td>
Specifies the indent at the right side of the paragraph.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
ListType</td><td>
Indicates whether the current paragraph is bulleted or numbered.</td><td>
Dependency Property</td><td>
ListType</td></tr>
<tr>
<td>
Inlines</td><td>
Contains the inline elements to be added in the paragraph.</td><td>
Dependency Property</td><td>
InlineCollection</td></tr>
</table>


## Adding Paragraph Alignment to an Application

ParagraphAdv can be added directly to an application using the following code snippet:


{% tabs %}
{% highlight xaml %}

<syncfusion:RichTextBoxAdv Height="300" Width="400" x:Name="richtext">            
<syncfusion:DocumentAdv>                
<syncfusion:SectionAdv><syncfusion:ParagraphAdv TextAlignment="Center" AfterSpacing=".3" ListType="Bulleted">                    
</syncfusion:ParagraphAdv>                </syncfusion:SectionAdv>            
</syncfusion:DocumentAdv>        
</syncfusion:RichTextBoxAdv>
{% endhighlight %}

{% highlight C# %}

     
 RichTextBoxAdv richtext = new RichTextBoxAdv();      
 DocumentAdv document = new DocumentAdv();      
 SectionAdv section = new SectionAdv();      
 ParagraphAdv paragraph = new ParagraphAdv();      
 paragraph.TextAlignment = TextAlignment.Center;     
 paragraph.AfterSpacing = .3;       
 paragraph.ListType = ListType.Bulleted;       
 section.Blocks.Add(paragraph);      
 document.Sections.Add(section);      
 richtext.Document = document;

{% endhighlight %}
{% endtabs %}
