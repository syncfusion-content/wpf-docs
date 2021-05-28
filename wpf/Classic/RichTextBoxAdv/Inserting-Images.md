---
layout: post
title: Inserting-Images in WPF Wizard Control control | Syncfusion
description: Learn here all about Inserting-Images support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
 documentation: ug
---

# Inserting-Images in WPF RichTextBoxAdv (Classic)

In order to insert an image in the document, ParagraphAdv provides an inline called ImageContainerAdv. 

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
Height</td><td>
Specifies the height of the image.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
Width</td><td>
Specifies the width of the image.</td><td>
Dependency Property</td><td>
Double</td></tr>
<tr>
<td>
ImageSource</td><td>
Source of the image. It can be bytes or URL.</td><td>
Dependency Property</td><td>
ImageSource.</td></tr>
<tr>
<td>
ImageBytes</td><td>
Image source can be represented as byte array.</td><td>
Dependency Property</td><td>
Byte[]</td></tr>
<tr>
<td>
FitToContent</td><td>
Fits the image inside the layout when it exceeds the size limit.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
</table>


##  Adding Images to an Application

ImageContainerAdv can be used to add an image directly to an application using the following code snippet:


{% tabs %}
{% highlight xaml %}

 
<syncfusion:RichTextBoxAdv Height="300" Width="400" x:Name="richtext">            
<syncfusion:DocumentAdv>                
<syncfusion:SectionAdv>                    
<syncfusion:ParagraphAdv >                        
<syncfusion:ImageContainerAdv ImageSource="/RibbonAndRichTextBox;component/OfficeUI/calender.png" Width="100" Height="100"/>                    
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
 ImageContainerAdv imagecontainer = new ImageContainerAdv();       
 BitmapImage bitmap = new BitmapImage();         
 bitmap.UriSource = new Uri("/RibbonAndRichTextBox;component/OfficeUI/calender.png");         
 imagecontainer.ImageSource = bitmap;         
 paragraph.Inlines.Add(imagecontainer);         
 section.Blocks.Add(paragraph);          
 document.Sections.Add(section);         
 richtext.Document = document;
{% endhighlight %}
{% endtabs %}


##  Limitations

Inserting an image has the following limitations:

1. It does not have a separate context menu.
2. It does not deal with brightness, reflection, or glow effects of the image.



