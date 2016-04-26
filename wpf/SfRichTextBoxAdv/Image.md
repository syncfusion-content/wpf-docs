---
title: Image
description: image
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: image
---
# Image

The SfRichTextBoxAdv allows you to insert images of various formats such as bitmap images (.bmp), JPEG (.jpg, .jpeg), PNG (.png) except Metafile images.
The following code example illustrates how to insert picture into the SfRichTextBoxAdv document through UI Command.
{% tabs %}
{% highlight xaml %}
<Button Content="Insert Picture" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertPictureCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

## Image Resizer

The SfRichTextBoxAdv also supports built-in image resizer to resize the images present in the document to your wish. The image resizer accepts both touch and mouse interactions.
![](Image_images/Image_img1.jpeg)

