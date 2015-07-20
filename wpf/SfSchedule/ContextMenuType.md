---
layout: post
title: ContextMenuType
description: contextmenutype 
platform: wpf
control: SfSchedule
documentation: ug
---

# ContextMenuType 

The collection of MenuItem elements can be organized by ContextMenuType property.

[XAML]



        &lt;Schedule:SfSchedule x:Name="schedule"   ScheduleType="Week" ContextMenuType="RadialMenu"&gt;

        &lt;/Schedule:SfSchedule&gt;





[C#]



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

           schedule.EnableTouch = true;  

            this.grid.Children.Add(schedule);





{ ![](ContextMenuType_images/ContextMenuType_img1.png) | markdownify }
{:.image }


{ ![](ContextMenuType_images/ContextMenuType_img2.png) | markdownify }
{:.image }




