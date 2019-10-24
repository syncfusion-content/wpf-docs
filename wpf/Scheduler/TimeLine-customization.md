---
layout: post
title: TimeLine customization| SfSchedule | Wpf | Syncfusion
description: timeline customization
platform: wpf
control: SfSchedule
documentation: ug
---

# TimeLine customization

Timeline elements of Day, Week and TimeLine view can be customized by using the following properties.

## Time Interval

Time interval can be customized using the TimeInterval property. The default interval is One hour.

## TimeMode 

SfSchedule Time format can be changed by using the TimeMode property.
{% tabs %}
{% highlight html %}
  



   <Grid Background="White" Name="grid">

        <Schedule:SfSchedule ScheduleType="Week" TimeMode="TwelveHours" >     

        </Schedule:SfSchedule>

    </Grid>


{% endhighlight  %}
{% highlight c# %}






            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.TimeMode = TimeModes.TwelveHours;

            this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}

![](TimeLine-customization_images/TimeLine-customization_img1.png)





![](TimeLine-customization_images/TimeLine-customization_img2.png)





## Major and Minor Tick Visibility

The major and minor tick visibility can be customized by MajorTickVisibility and MinorTickVisibility.

## Major and Minor Tick brush

The major and minor tick brush can be customized using HourStroke and MinuteStroke properties.

## Interval Height

The height between the intervals can be set using IntervalHeight property and its default value is 40.

