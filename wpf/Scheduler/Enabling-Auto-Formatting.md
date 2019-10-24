---
layout: post
title: Enabling Auto Formatting| SfSchedule | Wpf | Syncfusion
description: enabling auto formatting
platform: wpf
control: SfSchedule
documentation: ug
---

# Enabling Auto Formatting

When reducing the size of the schedule in week and month views, headers may be only partially shown. To avoid incompletely displayed headers, automatic formatting can be enabled by setting the EnableAutoFormat property of the SfSchedule control as true.
{% highlight html %}

        <syncfusion:SfSchedule x:Name="schedule" Background="White"

                               Height="400" Width="500"

                               EnableAutoFormat="True"

                               ScheduleType="Week">                           

        </syncfusion:SfSchedule>



{% endhighlight  %}
{% highlight c# %}


            SfSchedule schedule = new SfSchedule();

            schedule.Background = new SolidColorBrush(Colors.White);

            schedule.Height = 400;

            schedule.Width = 500;

            schedule.EnableAutoFormat = true;

            schedule.ScheduleType = ScheduleType.Week;

            this.grid.Children.Add(schedule);

{% endhighlight  %}



![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img1.png)



![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img2.png)



![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img3.png)





![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img4.png)





In the time line view, the width of the hours can be automatically adjusted by enabling EnableAutoFormat. To automatically adjust the width of the hours, IntervalHeight should not be specified with a particular value. If IntervalHeight is specified for the SfSchedule control, then the width of the hours in the time line view will be sized with the specified IntervalHeight.
{% highlight html %}

        <syncfusion:SfSchedule x:Name="schedule" Background="White"

                               Height="400" Width="500"

                               MajorTickTimeFormat="hh- mm- ss tt"

                               EnableAutoFormat="True"

                              ScheduleType="TimeLine">                           

        </syncfusion:SfSchedule>


{% endhighlight  %}


{% highlight c# %}
SfSchedule schedule = new SfSchedule();            schedule.Background = new SolidColorBrush(Colors.White);            schedule.Height = 400;            schedule.Width = 500;            schedule.MajorTickTimeFormat = "hh- mm- ss tt";            schedule.EnableAutoFormat = true;            schedule.ScheduleType = ScheduleType.TimeLine;            this.grid.Children.Add(schedule);
{% endhighlight %}


![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img5.png)





![](Enabling-Auto-Formatting_images/Enabling-Auto-Formatting_img6.png)



