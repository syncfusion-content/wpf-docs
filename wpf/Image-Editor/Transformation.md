---
layout: post
title: Image Transformation in Syncfusion SfImageEditor WPF
description: Image transformation in Syncfusion Essential Studio WPF ImageEditor (SfImageEditor) control, its elements and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Transformation in WPF ImageEditor (SfImageEditor) Control

The image editor control provides the following two transformations:

* Flip
* Rotate

## Flip

Images can be flipped in either the horizontal or vertical direction. By default, images will be flipped in the horizontal direction.

### Using toolbar

To flip an image, click the Flip icon in the toolbar. A popup will be displayed prompting for whether to perform a horizontal flip or a vertical flip. Select the required flip direction to flip the image.

### Using code

Programmatically, you can flip an image using the `Flip` method. This method takes the [`FlipDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.Enums.FlipDirection.html) as the parameter to specify whether it is a horizontal flip or a vertical flip.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;
using Syncfusion.UI.Xaml.ImageEditor.Enums;

editor.Flip(FlipDirection.Horizontal);

{% endhighlight %}

{% endtabs %}

The following screenshot depicts the horizontal flip.

![Horizontal flip](Images/HorizontalFlip.jpg)

Vertical flip of the image.

![Vertical flip](Images/VerticalFlip.jpg)

## Rotate

### Using toolbar

To rotate an image, click the Rotate icon in the toolbar. This rotates the image by 90 degrees from the current state. On continuous clicks, the angle will be increased because the image is rotated from the current state.

### Using code

Use the `Rotate` method to rotate an image by 90 degrees from the current state.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.Rotate();

{% endhighlight %}

{% endtabs %}

![Rotate](Images/Rotate.jpg) 
