---
layout: post
title: Export-SfChart-as-Image
description: export sfchart as image
platform: wpf
control: Chart (Classic)
documentation: ug
---

## Export SfChart as Image

In order to export the SfChart control as an image, the Save method needs to be called. Two overload methods are available to export the SfChart:

* Save(string fileName)
* Save(Stream stream,BitmapEncoder bitmapEncoder)



The following code examples can be used to export the SfChart as an image:
{% highlight c# %}


chart.Save("my.gif");



 

            SaveFileDialog sfd = new SaveFileDialog();

            sfd.Filter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif              (*.gif)|*.gif|PNG(*.png)|*.png|All files (*.*)|*.*";

            if (sfd.ShowDialog() == true)

            {

                using (Stream fs = sfd.OpenFile())

                {

                    chart.Save(fs,new PngBitmapEncoder());

                }

            }


{% endhighlight  %}
