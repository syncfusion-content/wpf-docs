---
layout: post
title: All Day Panel| They are | Wpf | Syncfusion
description: all-day panel 
platform: wpf
control: SfSchedule
documentation: ug
---

# All-Day Panel 

The schedule All Day panel visibility can be customized by ShowAllDay and its default value is true.

{% tabs %}
{% highlight html %}



<Schedule:SfSchedule x:Name="schedule" ShowAllDay="False"/>


{% endhighlight  %}
{% highlight c# %}



SfSchedule schedule = new SfSchedule();

schedule.ShowAllDay = false;

this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}


![](All-Day-Panel_images/All-Day-Panel_img1.png)



## Date Navigation:                 

In schedule the date navigation can be done using the MoveToDate method of the schedule.
{% highlight c# %}



SfSchedule schedule = new SfSchedule();

schedule.MoveToDate(new DateTime(2014,1,1 ));


{% endhighlight  %}


