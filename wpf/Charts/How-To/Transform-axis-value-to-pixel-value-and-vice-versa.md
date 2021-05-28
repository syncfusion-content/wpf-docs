---
layout: post
title: Transform axis value to pixel value and vice versa| SfChart | Wpf | Syncfusion
description: transform axis value to pixel value and vice versa
platform: wpf
control: SfChart
 documentation: ug
---

## Transform axis value to pixel value and vice versa

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



           // Converts mouse co-ordinate points into a value related to ChartAxis.



            double xValue = this.LineChart.PointToValue(this.LineChart.PrimaryAxis, mousePoint);

            double yValue = this.LineChart.PointToValue(this.LineChart.SecondaryAxis, mousePoint);





            // Converts the data point value of the chart to Chart coordinate.

            double chartPointX = this.LineChart.ValueToPoint(this.LineChart.PrimaryAxis, xValue);

            double chartPointY = this.LineChart.ValueToPoint(this.LineChart.SecondaryAxis, yValue);



        }


{% endhighlight  %}
