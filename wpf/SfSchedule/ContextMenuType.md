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
{% highlight html %}



        <Schedule:SfSchedule x:Name="schedule"   ScheduleType="Week" ContextMenuType="RadialMenu">

        </Schedule:SfSchedule>

{% endhighlight  %}


{% highlight c# %}



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

           schedule.EnableTouch = true;  

            this.grid.Children.Add(schedule);



{% endhighlight  %}

![](ContextMenuType_images/ContextMenuType_img1.png)



![](ContextMenuType_images/ContextMenuType_img2.png)





