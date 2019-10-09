---
layout: post
title: Basic views in SfSchedule | Syncfusion
description: This section explains about types of schedule views and how to use that schedule views in SfSchedule control.
platform: wpf
control: SfSchedule
documentation: ug
---

# Schedule Views

`SfSchedule` control includes five different view styles in showing dates and can be allocated to the control using the property [ScheduleType](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.ScheduleType.html) property. By default the control is assigned with `DayView`. Initially, the latest date will be shown for all views of the calendar..

Schedule provides 5 different types of views which has mentioned below, 

* Day
* Week 
* WorkWeek
* Month
* TimeLine

## Day View
`DayView` is used to view a single day, and by default the current day is shown. Appointments on a specific day will be scheduled on the basis of their duration in the respective time slots.

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
`WeekView` is to view all week days of a particular week. Appointments will be scheduled in the corresponding timeslots on the basis of the week dates.

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
`WorkWeekView` is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. With any days of a week, you can customize it. Appointments scheduled in timeslots with the corresponding day of the week depending on their duration.

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
In `SfSchedule` control, `MonthView` is to view the entire dates of a given month. It is possible to place appointments in the specified date.

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
`TimelineView` displays the dates with the appropriate day count in the horizontal time axis. When moving right or left, you can see the past or future events. With an intuitive drag-and-drop feature, each view shows events accurately through time slots.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine"/>
{% endhighlight%}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.TimeLine;
{% endhighlight %}
{% endtabs %}

![TimeLine-view](Basic-View_images/Basic-View_img5.png)