---
layout: post
title: Basic View| SfSchedule | Wpf | Syncfusion
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

{% tabs %}
{% highlight xaml %}

<Window x:Class="SfScheduleWpf.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:schedule="http://schemas.syncfusion.com/wpf"

        Title="MainWindow" Height="350" Width="525"

        WindowState="Maximized">

    <Grid>

        <schedule:SfSchedule ScheduleType="Month"/>

    </Grid>

</Window>

{% endhighlight  %}


{% highlight c# %}

using Syncfusion.UI.Xaml.Schedule;
namespace GettingStarted
{
    public partial class MainWindow : Window
    {

        SfSchedule schedule = new SfSchedule();

        schedule.ScheduleType = ScheduleType.Month;
		
		this.Content = schedule;
	}
	
}

this.grid.Children.Add(schedule);


{% endhighlight %}
{% endtabs %}

![](Basic-View_images/Basic-View_img1.png)



Month View Scheduling
{:.caption}



