---
layout: post
title: Print Diagram content as image files.
description: How to Print the Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---
# Printing

This feature enables you to print a copy of the Diagram with or without Print Preview.

## Print Preview

Print preview is used to show preview the SfDiagram control before printing.

![](Printing_images/Printing_img1.png)

## Customize the Printing
`PrintStretch` and `Orientation` properties of [PrintingService](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PrintingService.html "PrintingService") is used to customize the
page which is to be previewed and printed.

{% tabs %}
{% highlight C# %}
diagram.PrintingService.PrintPreviewStretch = Stretch.Fill;

{% endhighlight %}
{% endtabs %}

## Customize the Appearance

Diagram exposed the print preview as the type of Control. So, the customization can be done by overriding the template of the `PrintPreviewControl`.
