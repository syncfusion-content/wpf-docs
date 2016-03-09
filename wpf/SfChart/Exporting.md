---
layout: post
title: Exporting | SfChart | Wpf | Syncfusion
description: exporting
platform: wpf
control: SfChart
documentation: ug
---

# Exporting

Chart can be exported into image format. The following image formats are supported by the SfChart.

* .jpeg or .jpg
* .jpg-XR
* .gif
* .png
* .bmp
* .tiff

**Methods**

<table>
<tr>
<th>
Name
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
Save(string filename)
</td>
<td>
Export the chart to selected image file format
</td>
</tr>
<tr>
<td>
Save(Stream stream, BitmapEncoder  imgEncoder)
</td>
<td>
Export the chart by using stream and its corresponding encoder.
</td>
</tr>
</table>
You can use the following code example to save the chart in button click event.

{% highlight c# %}
private void Button_Click(object sender, RoutedEventArgs e)

{

  SaveFileDialog sfd = new SaveFileDialog();

  sfd.Filter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif   

  (*.gif)|*.gif|PNG(*.png)|*.png|All files (*.*)|*.*";

  if (sfd.ShowDialog() == true)

  {

    using (Stream fs = sfd.OpenFile())

    {

       ExportDemoChart.Save(fs, new PngBitmapEncoder());

     }

   }

 }





{% endhighlight %}

![](Exporting_images/Exporting_img1.png)


