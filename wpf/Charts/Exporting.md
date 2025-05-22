---
layout: post
title: Exporting in WPF Charts control | Syncfusion
description: Learn here all about Exporting support in Syncfusion® WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Exporting in WPF Charts (SfChart)

Chart can be exported into image format. The following are the supported image formats:

* JPEG or JPG
* JPG-XR
* GIF
* PNG
* BMP
* TIFF

The following screenshot illustrates the chart, which has to be exported.

![WPF Chart For Printing](Exporting_images/wpf-chart-for-printing.png)

## Methods

Chart contains the following overloading methods for saving a chart as an image.

### Save(string filename)

This method will export chart to the specified location with the given name. By default, i.e., if you don't mention any specific location, it will be exported to the "../bin/debug" location.

The following code example illustrates the usage of this method:

{% highlight C# %}

private void SaveImage_Click(object sender, RoutedEventArgs e)
{
    this.SampleChart.Save("ExportedChart"); //Save in Debug location

    this.SampleChart.Save("D:\\Pictures\\Test\\ExportedChart"); //Save in 'D:\Pictures\Test' location.
}

{% endhighlight %}

T> You can change the image formats in the above code by changing its extension as .jpg, .tiff, etc.

### Save(Stream stream, BitmapEncoder imgEncoderID)

This helps to export the chart to any stream as shown in the below code example.

{% highlight C# %}

private void SaveImageEncoder_Click(object sender, RoutedEventArgs e)
{
    SaveFileDialog sfd = new SaveFileDialog();
    
    sfd.Filter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif (*.gif)|*.gif|PNG(*.png)|*.png|TIFF(*.tif,*.tiff)|*.tif|All files (*.*)|*.*";

    if (sfd.ShowDialog() == true)
    {
        using (Stream fs = sfd.OpenFile())
        {
            SampleChart.Save(fs, new PngBitmapEncoder());
        }
    }
}

{% endhighlight %}

![WPF Chart For Export Location](Exporting_images/wpf-chart-for-export-location.png)

The image will be saved in the specified location in the SaveFileDialog.

![WPF Chart Exported](Exporting_images/wpf-chart-exported.png)

### Export SfChart to image without rendering in UI

You can export the chart to image without rendering in UI by setting the chart to **RootVisual** in **HwndSource** and passing **HwndSourceParameters** to the **HwndSource**. The following code snippet demonstrates this.

{% highlight c# %}

static IntPtr ApplicationMessageFilter(IntPtr hwnd, int message, IntPtr wParam, IntPtr lParam, ref bool handled)
{
    return IntPtr.Zero;
}

HwndSourceParameters sourceParameters = new HwndSourceParameters();

sourceParameters.HwndSourceHook = ApplicationMessageFilter;

HwndSource source = new HwndSource(sourceParameters);

source.RootVisual = chart;

//Save chart
chart.Save("Chart.png");

{% endhighlight %}

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to know various chart types and how to easily configure them with built-in support for creating stunning visual effects.

## See also

[`How to export chart as Image`](https://help.syncfusion.com/wpf/charts/exporting)

[`How to print the chart`](https://help.syncfusion.com/wpf/charts/printing)

[`How to read image byte while rendering chart`](https://www.syncfusion.com/kb/2584/how-to-read-image-byte-while-rendering-chart)