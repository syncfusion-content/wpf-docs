---
layout: post
title: Collapsed Hours| SfSchedule | Wpf | Syncfusion
description: Collapsed Hours 
platform: wpf
control: SfSchedule
documentation: ug
---

# Collapsed Hours

For a particular Start and End time the selected hours can be hidden by using CollapsedHours property of Schedule.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule Background="White" x:Name="schedule" ScheduleType="Week">
    <schedule:SfSchedule.CollapsedHours>
    <schedule:ScheduleCollapsedHour StartHour="1" EndHour="5"  Background="Red"/>
    </schedule:SfSchedule.CollapsedHours>        
    </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    SfSchedule schedule = new SfSchedule();
    schedule.ScheduleType = ScheduleType.Week;
    schedule.CollapsedHours.Add(new ScheduleCollapsedHour() { StartHour = 10, EndHour = 11, Background = new SolidColorBrush(Colors.Red)});
    this.grid.Children.Add(schedule);
    
{% endhighlight %}

{% endtabs %}

![](CollapsedHours_images/CollapsedHours_img1.jpeg)
