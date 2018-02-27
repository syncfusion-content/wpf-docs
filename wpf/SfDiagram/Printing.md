---
layout: post
title: Print Diagram content as image files.
description: How to Print the Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---
# Printing

This feature enables you to print a copy of the Diagram with and without Print Preview.

## Print Preview

Print preview is used to show preview the SfDiagram control before printing.

![](Printing_images/Printing_img1.png)

## Customization of Print Preview

The SfDiagram control provides support to customize the appearance of print preview by using the `PrintStretch` and `Orientation` properties of [PrintingService](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PrintingService.html "PrintingService").

{% tabs %}
{% highlight C# %}
diagram.PrintingService.PrintPreviewStretch = Stretch.Fill;

{% endhighlight %}
{% endtabs %}

## Customize the Appearance

The SfDiagram control provides support to customize the appearance of page to be printed, using ControlTemplate in Print Preview Control. The customization is also shown in PrintPreview. This is helpful when a header or footer has been added to the page.

For more details about the customization of PrintPreviewControl, refer to the Print and Export sample from our dashboard samples.

