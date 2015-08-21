---
layout: post
title: Basic-View
description: basic view
platform: wpf
control: SfSchedule
documentation: ug
---

# Basic View

Schedule provides 4 different types of viewing the calendar, 

* Day
* Week 
* Month
* TimeLine



Using the property “ScheduleType” of SfSchedule, we can set the above view. Refer to the following code to set the View type of schedule.

Code Example:
{% highlight html %}



<Window x:Class="SfScheduleWpf.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:schedule="http://schemas.syncfusion.com/wpf"

        Title="MainWindow" Height="350" Width="525"

        WindowState="Maximized">

    <Grid>

        <schedule:SfSchedule></schedule:SfSchedule>

    </Grid>

</Window>

{% endhighlight  %}


{% highlight c# %}



SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Month;

this.grid.Children.Add(schedule);


{% endhighlight %}


![](Basic-View_images/Basic-View_img1.png)



Month View Scheduling



