---
layout: post
title: Focused-and-Non-Focused-Month-Brush
description: focused and non-focused month brush
platform: wpf
control: SfSchedule
documentation: ug
---

# Focused and Non-Focused Month Brush

In Schedule month view, date of the current selected month and date of previous/next months can be differentiated using the FocusedMonth and NonFocusedMonth properties respectively.

[XAML]



     <Schedule:SfSchedule x:Name="schedule" FocusedMonth="White" 

                          NonFocusedMonth="WhiteSmoke" ScheduleType="Month" />





[C#]



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Month;

            schedule.FocusedMonth = new SolidColorBrush(Colors.White);

            schedule.NonFocusedMonth = new SolidColorBrush(Colors.WhiteSmoke);

            this.grid.Children.Add(schedule);





{ ![](Focused-and-Non-Focused-Month-Brush_images/Focused-and-Non-Focused-Month-Brush_img1.png) | markdownify }
{:.image }




