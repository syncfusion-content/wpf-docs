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

## Text wrapping style
Text wrapping refers to how images are fit with surrounding text in a document. Please [refer to this page](/wpf/richtextbox/text-wrapping-style) for more information about text wrapping styles available in Word documents.

## Positioning the image
Starting from v19.1.0.x, RichTextBox preserves the position properties of the image and displays the image based on position properties. It does not support modifying the position properties. Whereas the image will be automatically moved along with text edited if it is positioned relative to the line or paragraph.

N> At present, the image with text wrapping style `In-Line with Text` can only be dragged and dropped anywhere in the document.
