---
layout: post
title: Exporting SfChart to an image.
description: Exporting chart to any standard image formats like JPG, PNG, etc.
platform: wpf
control: SfChart
documentation: ug
---

# Exporting

Chart can be exported into image format. The following are the supported image formats:

* JPEG or JPG
* JPG-XR
* GIF
* PNG
* BMP
* TIFF

## Methods

Chart contains the following overloading methods for saving a chart as an image.

### Save(string filename)

This method will export chart to the specified location with the given name. By default, i.e., if you didn’t mention any specific location. It will be exported to “../bin/debug” location.

The following code examples illustrates the usage of this method:

{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)

{

ExportDemoChart.Save("chart_image.png"); //Save in Debug location



ExportDemoChart.Save("D:\\Pictures\\Test\\chart_image.png"); 

//Save in ‘D:\Picture\Test’ location.



}

{% endhighlight %}

T> We can change the image formats in above code by changing its extension as .jpg, .tiff, etc.

### Save(Stream stream, BitmapEncoder imgEncoder)

This helps to export the chart to any stream as in below code example.

{% highlight C# %}

FileStream fs = File.Create(@"c:\temp\MyTest.png");

**ExportDemoChart****.****Save****(****fs****,** **new** **PngBitmapEncoder****());**

{% endhighlight %}

