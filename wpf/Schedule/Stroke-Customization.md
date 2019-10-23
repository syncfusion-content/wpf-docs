---
layout: post
title: Stroke Customization| SfSchedule | Wpf | Syncfusion
description: stroke customization
platform: wpf
control: SfSchedule
documentation: ug
---

# Stroke Customization

In the SfSchedule control, major, minor, and horizontal lines drawn in the day and week views, and horizontal and vertical lines drawn in the month view can be customized.

In the day, week, work week, and time line views, the color of major lines can be customized by setting the Brush property MajorTickStroke, and a dashed line pattern can be set for major lines through MajorTickStrokeDashArray, a double collection property. Similarly, the color of minor lines and a dashed line pattern can be set through MinorTickStroke and MinorTickStrokeDashArray, respectively.The color of the vertical lines that separate dates in the week view can be customized through the DayViewVerticalLineStroke property. Major and minor tick labels can also be customized using MajorTickLabelStroke and MinorTickLabelStroke.

In the month view, the horizontal and vertical line strokes can be customized by using the MonthViewLineStroke property.



###  Property Table

<table>
<tr>
<th>
API Name</th><th>
Data Type</th><th>
Description</th></tr>
<tr>
<td>
MajorTickStroke</td><td>
Brush</td><td>
Used to customize the major line stroke of the day and time line views.</td></tr>
<tr>
<td>
MinorTickStroke</td><td>
Brush</td><td>
Used to customize the minor line stroke of the day and time line views.</td></tr>
<tr>
<td>
MajorTickLabelStroke</td><td>
Brush</td><td>
Used to customize the major line label stroke in the day and time line views.</td></tr>
<tr>
<td>
MinorTickLabelStroke</td><td>
Brush</td><td>
Used to customize the minor line label stroke of the day and time line views.</td></tr>
<tr>
<td>
MajorTickStrokeDashArray</td><td>
DoubleCollection</td><td>
Used to customize the major line stroke dash array of the day and time line views.</td></tr>
<tr>
<td>
MinorTickStrokeDashArray</td><td>
DoubleCollection</td><td>
Used to customize the minor line stroke dash array of the day and time line views.</td></tr>
<tr>
<td>
DayViewVerticalLineStroke</td><td>
Brush</td><td>
Used to customize the vertical line stroke of the day view.</td></tr>
<tr>
<td>
MonthViewLineStroke</td><td>
Brush</td><td>
Used to customize the line stroke of month view.</td></tr>
</table>

{% tabs %}
{% highlight html %}


<syncfusion:SfSchedule x:Name="Schedule1" TimeInterval="ThirtyMin"IntervalHeight="40"

                               ScheduleType="WorkWeek"

                               MajorTickStroke="Red"

                               MinorTickStroke="Green"

                               MajorTickLabelStroke="Red"

                               MinorTickLabelStroke="Green"

                               DayViewVerticalLineStroke="Blue"

                               MonthViewLineStroke="Orange"

                               MajorTickStrokeDashArray="5,10"

                               MinorTickStrokeDashArray="5,5"></syncfusion:SfSchedule>

{% endhighlight  %}
{% highlight c# %}





            SfSchedule schedule = new SfSchedule();

            schedule.TimeInterval = TimeInterval.ThirtyMin;

            schedule.IntervalHeight = 40;

            schedule.ScheduleType = ScheduleType.WorkWeek;

            schedule.MajorTickStroke = new SolidColorBrush(Colors.Red);

            schedule.MinorTickStroke = new SolidColorBrush(Colors.Green);

            schedule.MajorTickLabelStroke = new SolidColorBrush(Colors.Red);

            schedule.MinorTickLabelStroke = new SolidColorBrush(Colors.Green);

            schedule.DayViewVerticalLineStroke = new SolidColorBrush(Colors.Blue);

            schedule.MonthViewLineStroke = new SolidColorBrush(Colors.Orange); 

            schedule.MajorTickStrokeDashArray = new DoubleCollection() { 5,10};

            schedule.MinorTickStrokeDashArray = new DoubleCollection() {10,10 };

            this.grid.Children.Add(schedule);

{% endhighlight  %}
{% endtabs %}


![](Stroke-Customization_images/Stroke-Customization_img1.png)



