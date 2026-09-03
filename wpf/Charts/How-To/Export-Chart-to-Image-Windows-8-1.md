---
layout: post
title: How to export chart to image in WPF Chart | Syncfusion®
description: Export a chart to an image in the WPF Chart on Windows 8.1 to save chart visuals for sharing, printing, or further use.
platform: wpf
control: SfChart
documentation: ug
---

# How to export chart to image in WPF Chart

The export chart to image feature in the WPF Charts control enables the user to export the image of the chart in different image file formats. 

## Supported Formats

* JPG or JPEG
* JPG-XR
* GIF
* TIFF
* PNG
* BMP

### Method Table
<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Save</td><td>
Save(string fileName, StorageFolder folderLocation)</td><td>
Export the chart image with the given file name to the mentioned location.If folderLocation is null then it exports the image to the app installed location.</td></tr>
<tr>
<td>
Save</td><td>
Save(IRandomAccessStream stream, Guid bitmapEncoderID)</td><td>
Export the chart image using the stream and its corresponding encoder.</td></tr>
</table>



### Method 1
{% highlight c# %}
chart.Save("sfchart.jpg", KnownFolders.PicturesLibrary);
{% endhighlight  %}


### Method 2
{% highlight c# %}
var memoryStream = new InMemoryRandomAccessStream();

chart.Save(memoryStream, BitmapEncoder.BmpEncoderId);

StorageFolder storageFolder = Windows.ApplicationModel.Package.Current.InstalledLocation;

var file = await storageFolder.CreateFileAsync("chartwithstream.jpg", CreationCollisionOption.GenerateUniqueName);

var stream = await file.OpenAsync(Windows.Storage.FileAccessMode.ReadWrite);
{
    chart.Save(stream, BitmapEncoder.BmpEncoderId);
}   

{% endhighlight  %}

