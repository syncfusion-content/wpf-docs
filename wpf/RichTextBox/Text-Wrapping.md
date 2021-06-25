---
title: Text Wrapping in WPF RichTextBox control | Syncfusion
description: Learn here all about Text Wrapping support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: text-wrapping, wrapping-style
---
# Text Wrapping in WPF RichTextBox (SfRichTextBoxAdv)
Text wrapping refers to how images and shapes are fit with surrounding text in a document. Currently, RichTextBox has only preservation support for image and textbox shape with below wrapping styles. The image or shape can only be inserted with an `In-Line with Text` wrapping style. 

## In-Line with Text
In this option, the image or shape is placed on the same line surrounding with text like any other word or letter. This image or shape will be automatically moved along with the text while editing, whereas the other options denote that the image or shape stays in a fixed position while the text shifts and wraps around it.

![view of image with inline wrapping style in RichTextBox](Text-Wrapping_images/inline-textwrapping.PNG)

## Behind
In this option, the image or shape is placed behind the text. This can be used when you need to add a watermark or background image to a document.

![view of image with behind wrapping style in RichTextBox](Text-Wrapping_images/behind-textwrapping.PNG)

## In Front of Text
In this option, the image or shape is placed in front of the text. This can be used to place an image around some text or to add shape to highlight the part in a paragraph.

![view of image with in front of text wrapping style in RichTextBox](Text-Wrapping_images/infront-textwrapping.PNG)

N> Starting from v18.3.0.x, the in front of and behind text wrapping styles are supported.

## Top and Bottom
In this option, Text wraps above and below the image or shape. No text is to the left or right of the image or shape. This can be used for larger images or shapes that occupy most of the width in a document.

N> Starting from v19.1.0.x, the top and bottom wrapping style is supported.

![view of image with top and bottom wrapping style in RichTextBox](Text-Wrapping_images/topandbottom-textwrapping.PNG)

## Square
In this option, Text wraps around the image or text box in a square shape.

N> Tight and Through types are also displayed like square wrapping style in RichTextBox which is supported from v19.2.0.x.

![view of shape with square wrapping style in RichTextBox](Text-Wrapping_images/square-textwrapping.PNG)

 


