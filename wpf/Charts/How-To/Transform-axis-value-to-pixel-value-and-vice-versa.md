---
layout: post
title: How to transform axis value to pixel in WPF Chart | Syncfusion®
description: Transform axis values to pixel values and convert pixel values back to axis values in the WPF Chart for coordinate-based interactions.
platform: wpf
control: SfChart
documentation: ug
---

# How to transform axis value to pixel value in WPF Chart

SfChart offers two utility methods for converting your data points into pixel values (device coordinates).

* ValueToPoint(ChartAxis axis, double value)
* PointToValue(ChartAxis axis, Point point)


{% highlight c# %}

private void LineChart_MouseMove(object sender, MouseEventArgs e)
{
    Point mousePoint = new Point                
    {
        X = e.GetPosition(LineChart).X - LineChart.SeriesClipRect.Left - LineChart.Margin.Left,
        Y = e.GetPosition(LineChart).Y - LineChart.SeriesClipRect.Top - LineChart.Margin.Top
    };

    // Converts mouse co-ordinate points into a value related to ChartAxis.                
    double xValue = this.LineChart.PointToValue(this.LineChart.PrimaryAxis, mousePoint);
    double yValue = this.LineChart.PointToValue(this.LineChart.SecondaryAxis, mousePoint);

    // Converts the data point value of the chart to Chart coordinate.
    double chartPointX = this.LineChart.ValueToPoint(this.LineChart.PrimaryAxis, xValue);
    double chartPointY = this.LineChart.ValueToPoint(this.LineChart.SecondaryAxis, yValue);
}

{% endhighlight  %}
