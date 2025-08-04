---
layout: post
title: Exporting Chart as image in WPF Chart | Syncfusion
description: Learn here about getting started with Syncfusion WPF classic Chart control function, its elements and more.
platform: wpf
control: Chart (Classic)
documentation: ug
---

# Getting started with WPF Chart

In order to export the Chart control as an image, the Save method needs to be called. Two overload methods are available to export the Chart:

* Save(Stream stream)
* Save(string fileName)
* Save(Stream stream, BitmapEncoder encoder)
* Save(Stream stream, Rect saveArea)
* Save(string fileName, BitmapEncoder encoder) 
* Save(string fileName, Rect saveArea)
* Save(Stream stream, Rect saveArea, BitmapEncoder encoder)
* Save(string fileName, Rect saveArea, BitmapEncoder encoder)


The following code examples can be used to export the Chart as an image:
{% highlight c# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
string C_imageFilesFilter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif (*.gif)|*.gif|TIFF(*.tiff)|*.tiff|PNG(*.png)|*.png|WDP(*.wdp)|*.wdp|Xps file (*.xps)|*.xps|All files (*.*)|*.*";
 saveFileDialog.Filter = C_imageFilesFilter;

if (saveFileDialog.ShowDialog() == true)
{             
Chart1.Save(saveFileDialog.FileName);
}
{% endhighlight  %}
