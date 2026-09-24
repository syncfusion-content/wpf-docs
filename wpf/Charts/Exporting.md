---
layout: post
title: Exporting in WPF Charts | Syncfusion®
description: Exporting in the WPF Chart enables chart data and visuals to be saved in supported formats for sharing, printing, and reporting.
platform: wpf
control: SfChart
documentation: ug
appliesto: UI Component Suite, Chart SDK
---

# Exporting in WPF Charts

Chart can be exported into image format. The following are the supported image formats:

* JPEG or JPG
* JPG-XR
* GIF
* PNG
* BMP
* TIFF

## Export chart as an image

Chart provides the following overloaded methods for exporting it as an image.

The following methods used to export the chart as an image:

* [`Save(string filename)`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Save_System_String_) - Exports the chart as an image to the specified location using the provided file name.
* [`Save(Stream, BitmapEncoder)`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Save_System_IO_Stream_System_Windows_Media_Imaging_BitmapEncoder_) - Exports the chart as an image to the specified stream using the provided bitmap encoder.

### Save(string filename)

Use this method to export the chart to a specified location with a custom file name. If a location is not provided, the chart will be exported to the ../bin/Debug directory by default.

The following code examples illustrates the usage of this method:

{% highlight C# %}

private void SaveImage_Click(object sender, RoutedEventArgs e)
{
    this.SampleChart.Save("ExportedChart.png"); //Save in Debug location
}

{% endhighlight %}

T> We can change the image formats in above code by changing its extension as .jpg, .tiff, etc.

### Save(Stream stream, BitmapEncoder imgEncoderID)

Use this method to export the chart to the specified stream using the provided bitmap encoder.

The following code examples illustrates the usage of this method:

{% highlight C# %}

private void SaveImageEncoder_Click(object sender, RoutedEventArgs e)
{
    using (FileStream fileStream = new FileStream("ExportedChart.png", FileMode.Create))
    {
        SampleChart.Save(fileStream, new PngBitmapEncoder());
    }
}

{% endhighlight %}

N> The FileMode argument determines how the output file is created or accessed. The example uses FileMode.Create, which creates a new file or overwrites in an existing file. You can use other FileMode values such as CreateNew, Open, OpenOrCreate, Append, or Truncate depending on your file handling requirements.

### Export without UI rendering

Export the chart as an image without rendering it in the UI by setting the chart as the **RootVisual** of an **HwndSource** and assigning **HwndSourceParameters** to the **HwndSource**. The following code example demonstrates this process.

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

{% endhighlight  %}

## Export chart to XPS

Chart has built-in support for exporting to the XPS file format, providing scalable, print-ready output without any loss of quality when zooming or printing.

The following methods used to export the chart as an XPS file:

* `SaveAsXps(string fileName)` - Exports the chart as an XPS file with the specified file name to the desired location.
* `SaveAsXps(Stream stream)` - Exports the chart as an XPS file using the specified stream.

### SaveAsXps(string fileName)

Use this method to export the chart as a vector-based XPS file to a specified location with a custom file name. If a location is not provided, the chart will be exported to the ../bin/Debug directory by default.

The following code examples illustrates the usage of this method:

{% highlight C# %}

private void ExportAsXps_Click(object sender, RoutedEventArgs e)
{             
    SampleChart.SaveAsXps(Chart_Export.xps);
}

{% endhighlight %}

### SaveAsXps(Stream stream)

Use this method to export the chart as a vector-based XPS file using the specified stream.

The following code examples illustrates the usage of this method:

{% highlight C# %}

private void ExportAsStream_Click(object sender, RoutedEventArgs e)
{
    using (FileStream fileStream = new FileStream("Chart_Export_Stream.xps", FileMode.Create))
    {
        SampleChart.SaveAsXps(fileStream);
    }
}

{% endhighlight %}

N> The FileMode argument determines how the output file is created or accessed. The example uses FileMode.Create, which creates a new file or overwrites in an existing file. You can use other FileMode values such as CreateNew, Open, OpenOrCreate, Append, or Truncate depending on your file handling requirements.

### Export without UI rendering

Export the chart as an vector image without rendering it in the UI by setting the chart as the **RootVisual** of an **HwndSource** and assigning **HwndSourceParameters** to the **HwndSource**. The following code example demonstrates this process.

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
chart.Save("Chart.xps");

{% endhighlight  %}

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos/tree/master/chart/Views/Exporting) to know various chart types and how to easily configure them with built-in support for creating stunning visual effects.

## See also

* [`How to export the multiple WPF Charts`](https://support.syncfusion.com/kb/article/10686/how-to-export-the-multiple-wpf-charts)
* [`How to export multiple WPF Charts using MVVM-Compatible`](https://support.syncfusion.com/kb/article/11481/how-to-export-multiple-wpf-charts-using-mvvm-compatible)
* [`How to read image byte while rendering a WPF Chart (SfChart)`](https://support.syncfusion.com/kb/article/2774/how-to-read-image-byte-while-rendering-a-wpf-chart-sfchart)
