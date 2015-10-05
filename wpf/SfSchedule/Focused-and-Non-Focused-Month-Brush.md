---
layout: post
title: Focused and Non Focused Month Brush| SfSchedule | Wpf | Syncfusion
description: focused and non-focused month brush
platform: wpf
control: SfSchedule
documentation: ug
---

# Focused and Non-Focused Month Brush

In Schedule month view, date of the current selected month and date of previous/next months can be differentiated using the FocusedMonth and NonFocusedMonth properties respectively.
{% tabs %}
{% highlight html %}



<Schedule:SfSchedule x:Name="schedule" FocusedMonth="White" 

NonFocusedMonth="WhiteSmoke" ScheduleType="Month" />

{% endhighlight  %}

{% highlight c# %}




SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Month;

schedule.FocusedMonth = new SolidColorBrush(Colors.White);

schedule.NonFocusedMonth = new SolidColorBrush(Colors.WhiteSmoke);

this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}

![](Focused-and-Non-Focused-Month-Brush_images/Focused-and-Non-Focused-Month-Brush_img1.png)





