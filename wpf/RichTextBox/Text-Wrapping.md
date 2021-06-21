---
title: Text Wrapping in WPF RichTextBox control | Syncfusion
description: Learn here all about Text Wrapping support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: text-wrapping, wrapping-style
---
# Text Wrapping in WPF RichTextBox (SfRichTextBoxAdv)
Text wrapping refers to how images and shapes are positioned to text in a document. Currently, SfRichTextBoxAdv has only preservation support, for image and textbox shape with below wrapping styles.  The image can be inserted with inline wrapping style alone.

## In-Line with Text
This option places an image on the same line as the surrounding text. The image will thus move as text is added or removed, whereas the other options here mean the image stays in one position while text is shifts and wraps around it.

![In Line](Text-Wrapping_images/inline.PNG)

## Behind
Places an image behind the text, allowing you to add like watermark or background image on a page.

![Behind](Text-Wrapping_images/behind.PNG)

## In Front of Text
Places the picture in front of the text. This can be used to place an image around some text or to add shape to highlight the part of a passage.

![In Front](Text-Wrapping_images/infront.PNG)

## Top and Bottom
Text wraps above and below the image so it is on its own line. This is most useful for larger images that occupy most of the width of a page.

![Top and Bottom](Text-Wrapping_images/TopandBottom.PNG)

## Square
This wraps text around an image on all sides at right angles, as if it had a rectangular box around it.
N> Tight and Through types also preserved as Square wrapping style in SfRichTextBoxAdv.

![Square](Text-Wrapping_images/Square.PNG)


N> The square and top and bottom wrapping style preservation is supported from V19.2.0.X.
 


