---
layout: post
title: Current Day Highlighting| SfSchedule | Wpf | Syncfusion
description: current day highlighting
platform: wpf
control: SfSchedule
documentation: ug
---

# Current Day Highlighting

The current day highlighting brush in all view can be customized by CurrentDateBackground property.
{% tabs %}
{% highlight html %}

<Schedule:SfSchedule x:Name="schedule" ScheduleType="Week"

CurrentDateBackground=" LightSkyBlue " /> 



{% endhighlight  %}
{% highlight c# %}




SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Week;

schedule.CurrentDateBackground = new SolidColorBrush(Colors.LightSkyBlue);

this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}

![](Current-Day-Highlighting_images/Current-Day-Highlighting_img1.png)





