---
layout: post
title: Transform axis value to pixel value in WPF Chart Control | Syncfusion
description: Transform axis value to pixel value and vice versa in Syncfusion Essential Studio® WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# Transform axis value to pixel value and vice versa

SfChart provides two utility methods for converting between data points and pixel values (device coordinates):

* `ValueToPoint(ChartAxis axis, double value)` - Converts a data point value to chart coordinates
* `PointToValue(ChartAxis axis, Point point)` - Converts chart coordinates to a data point value

## Example

The following example demonstrates how to use these conversion methods in a mouse move event handler:

{% highlight c# %}
private void LineChart_MouseMove(object sender, MouseEventArgs e)
{
    // Calculate mouse position relative to chart area
    Point mousePoint = new Point
    {
        X = e.GetPosition(LineChart).X - LineChart.SeriesClipRect.Left - LineChart.Margin.Left,
        Y = e.GetPosition(LineChart).Y - LineChart.SeriesClipRect.Top - LineChart.Margin.Top 
    };

    // Convert mouse coordinates to axis values
    double xValue = this.LineChart.PointToValue(this.LineChart.PrimaryAxis, mousePoint);
    double yValue = this.LineChart.PointToValue(this.LineChart.SecondaryAxis, mousePoint);

    // Convert axis values back to chart coordinates
    double chartPointX = this.LineChart.ValueToPoint(this.LineChart.PrimaryAxis, xValue);
    double chartPointY = this.LineChart.ValueToPoint(this.LineChart.SecondaryAxis, yValue);
}
{% endhighlight %}