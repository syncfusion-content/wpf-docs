---
title: Image in WPF RichTextBox control | Syncfusion
description: Learn here all about Image support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: image
---
# Image in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv allows you to insert images of various formats such as bitmap images (.bmp), JPEG (.jpg, .jpeg), PNG (.png) except Metafile images.
The following code example illustrates how to insert picture into the SfRichTextBoxAdv document through UI Command.
{% tabs %}
{% highlight xaml %}
<Button Content="Insert Picture" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertPictureCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

## Image Resizer

The SfRichTextBoxAdv also supports built-in image resizer to resize the images present in the document to your wish. The image resizer accepts both touch and mouse interactions.
![Image_img1](Image_images/Image_img1.jpeg)

## Text wrapping
Text wrapping refers to how images are positioned about to text in a document. Please [refer to this page](https://help.syncfusion.com/wpf/richtextbox/text-wrapping) for more information about text wrapping.

## Positioning
Currently, SfRichTextBoxAdv doesn’t have support for change or move the position of the image. The image will move as text is added or removed if it is positioned relative to the line or paragraph.

N> The image can be positioned anywhere in the document by drag and drop. if the image’s wrapping style is in line with the text.
