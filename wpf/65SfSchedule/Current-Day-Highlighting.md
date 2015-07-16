---
layout: post
title: Current-Day-Highlighting
description: current day highlighting
platform: wpf
control: SfSchedule
documentation: ug
---

# Current Day Highlighting

The current day highlighting brush in all view can be customized by CurrentDateBackground property.

[XAML]

        <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week"

          CurrentDateBackground=" LightSkyBlue " /> 





[C#]



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.CurrentDateBackground = new SolidColorBrush(Colors.LightSkyBlue);

            this.grid.Children.Add(schedule);





{ ![](Current-Day-Highlighting_images/Current-Day-Highlighting_img1.png) | markdownify }
{:.image }




