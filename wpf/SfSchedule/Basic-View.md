---
layout: post
title: Types of Schedule views at Syncfusion schedule for Wpf
description: Learn what and all schedule views are available and how to use that views in SfSchedule control.
platform: wpf
control: SfSchedule
documentation: ug
---

# Schedule Views

SfSchedule control provides five different types of views to display dates and it can be assigned to the control by using [ScheduleType](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.ScheduleType.html) property. By default the control is assigned with `DayView`. Current date will be displayed initially for all the Schedule views.

Schedule provides 5 different types of views which has mentioned below, 

* Day
* Week 
* WorkWeek
* Month
* TimeLine

## Day View

`DayView` is used to display a single day, current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

{% tabs %}
{% highlight xaml %}

<Window x:Class="SfScheduleWpf.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:schedule="http://schemas.syncfusion.com/wpf"

        Title="MainWindow" Height="350" Width="525"

        WindowState="Maximized">

    <Grid>

        <schedule:SfSchedule ScheduleType="Day"/>

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

        schedule.ScheduleType = ScheduleType.Day;
		
		this.Content = schedule;
	}
	
}
{% endhighlight %}
{% endtabs %}

![Day-View](Basic-View_images/Basic-View_img1.png)

## Week View
`WeekView` is to view all days of a particular week. Appointments will be arranged based on the dates on the week in respective timeslots.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="Week"/>
{% endhighlight%}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.Week;
{% endhighlight %}
{% endtabs %}

![Week-view](Basic-View_images/Basic-View_img2.png)

## Work Week View
`WorkWeekView` is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="WorkWeek"/>
{% endhighlight%}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.WorkWeek;
{% endhighlight %}
{% endtabs %}
![WorkWeek-view](Basic-View_images/Basic-View_img3.png)

## Month View
`MonthView` in Schedule control is to view entire dates of a particular month. Appointments can be placed in specified date.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="Month"/>
{% endhighlight%}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.Month;
{% endhighlight %}
{% endtabs %}
![Month-view](Basic-View_images/Basic-View_img4.png)

## TimeLine View
`TimelineView` displays the dates in horizontal time axis with the desired day’s count. You can see the past or future dates by scrolling to the right or left. Each view displays events accurately across the time slots with an intuitive drag-and-drop feature.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine"/>
{% endhighlight%}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.TimeLine;
{% endhighlight %}
{% endtabs %}

![TimeLine-view](Basic-View_images/Basic-View_img4.png)