---
layout: post
title: Hiding Non Working Hours| SfSchedule | Wpf | Syncfusion
description: hiding non-working hours
platform: wpf
control: SfSchedule
documentation: ug
---

# Hiding Non-Working Hours

To hide non-working hours in the schedule, the ShowNonWorkingHours property in the schedule must be set as false. The working hours specified using the WorkStartHour and WorkEndHour properties are simply shown in the schedule without showing non-working hours.

{% tabs %}
{% highlight html %}


         <syncfusion:SfSchedule x:Name="schedule" Background="White"

                               ScheduleType="Week"

                               WorkStartHour="9" WorkEndHour="18"

                               ShowNonWorkingHours="False">

        </syncfusion:SfSchedule>      


{% endhighlight  %}
{% highlight c# %}




            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.WorkStartHour=9;

            schedule.WorkEndHour=18;

            schedule.ShowNonWorkingHours=false;

             this.grid.Children.Add(schedule);
{% endhighlight  %}
{% endtabs %}

![](Hiding-Non-Working-Hours_images/Hiding-Non-Working-Hours_img1.png)





