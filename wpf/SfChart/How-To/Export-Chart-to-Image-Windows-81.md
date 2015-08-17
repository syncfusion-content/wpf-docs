---
layout: post
title: Export-Chart-to-Image-Windows-81
description: export chart to image (windows 8.1)
platform: wpf
control: SfChart
documentation: ug
---

### Export Chart to Image (Windows 8.1)

The export chart to image feature in the SfChart control enables the user to export the image of the chart in different image file formats. 

Supported Formats

* JPG or JPEG
* JPG-XR
* GIF
* TIFF
* PNG
* BMP



Method Table

<table>
<tr>
<td>
Method</td><td>
Prototype</td><td>
Description</td></tr>
<tr>
<td>
Save</td><td>
Save()</td><td>
Export the chart image to the particular location using FileSavePicker. </td></tr>
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


[C#]



#Method 1

chart.Save();



#Method 2

chart.Save("sfchart.jpg", KnownFolders.PicturesLibrary);



#Method 3

var memoryStream = new InMemoryRandomAccessStream();

            chart.Save(memoryStream, BitmapEncoder.BmpEncoderId);



            StorageFolder storageFolder = Windows.ApplicationModel.Package.Current.InstalledLocation;



            var file = await storageFolder.CreateFileAsync("chartwithstream.jpg", CreationCollisionOption.GenerateUniqueName);



            var stream = await file.OpenAsync(Windows.Storage.FileAccessMode.ReadWrite);

            {

                chart.Save(stream, BitmapEncoder.BmpEncoderId);

            }    



