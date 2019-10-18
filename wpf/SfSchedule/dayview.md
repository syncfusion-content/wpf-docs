---
layout: post
title: DayView with WPF Scheduler | Syncfusion
description: This section explains about the DayView settings and that appearance customization for WPF Scheduler.
platform: wpf
control: SfSchedule
documentation: ug
---

## DayView
DayView is used to view a single day. By default, the current day will be visible. Appointments on a specific day will be scheduled on the basis of their duration in the respective time slots.

## Day Header Date Format
The default Header date format of the DayView can be customized by using the [HeaderDateFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~HeaderDateFormat.html) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule  ScheduleType="Day"
HeaderDateFormat="dd-MMMM-yyyy">
</Schedule:SfSchedule>
{% endhighlight %}
{% highlight c#%}
SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Day;

schedule.HeaderDateFormat = "dd-MMMM-yyyy";

{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview header format](dayview_images/dayview-header-format.png)

## Day Header Background

The Header background can be changed by [HeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~HeaderBackground.html) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule  ScheduleType="Day" HeaderBackground="LightSkyBlue" />
{% endhighlight %}
{% highlight c#%}
schedule.ScheduleType = ScheduleType.Day;

schedule.HeaderBackground = Brushes.LightSkyBlue;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview header background](dayview_images/dayview-header-background.png)

## Change Time Interval
By setting schedulers [TimeInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~TimeInterval.html) property, you can configure the timeslots interval for day view.


{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule  ScheduleType="Day" TimeInterval = "OneHour" />
{% endhighlight %}
{% highlight c#%}
schedule.ScheduleType = ScheduleType.Day;
schedule.TimeInterval = TimeInterval.OneHour;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview timeinterval](dayview_images/dayview-time-interval.png)

## Change Time Interval Height
By setting schedulers [IntervalHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~IntervalHeight.html) property, you can configure the timeslots interval for day view.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule  ScheduleType="Day" IntervalHeight = 100 />
{% endhighlight %}
{% highlight c#%}
schedule.ScheduleType = ScheduleType.Day;
schedule.IntervalHeight = 100;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview interval height](dayview_images/dayview-interval-height.png)

### Full screen scheduler
Schedule time interval height can be adjusted based on screen height by changing the value of `IntervalHeight` property to -1. It will auto-fit to the screen height and width.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule  ScheduleType="Day" IntervalHeight = -1 />
{% endhighlight %}
{% highlight c#%}
schedule.ScheduleType = ScheduleType.Day;
schedule.IntervalHeight = -1;
{% endhighlight %}
{% endtabs %}

## Change Working hours
Working hours in day view of Scheduler will be differentiated with non-working hours by separate color using [IsHighLightWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~IsHighLightWorkingHours.html) property. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~WorkEndHour.html) properties.

{% tabs %}
{% higligh xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="Day" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     IsHighLightWorkingHours="True"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.Day;
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.IsHighLightWorkingHours = true;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView working hours](dayview_images/dayview-working-hours.png)

### Change Non-Working hours Background
Scheduler uses the [NonWorkingHourBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonWorkingHourBrush.html) property to adjust the background color for non-working hours.

{% tabs %}
{% higligh xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="Day" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     NonWorkingHourBrush="LightSteelBlue"
                     IsHighLightWorkingHours="True"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.Day;
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.NonWorkingHourBrush = Brushes.LightSteelBlue;
this.schedule.IsHighLightWorkingHours = true;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView Non working hours background changes](dayview_images/dayview-non-working-hours-background.png)

###  Display Working hours only
Scheduler supports to display the working hours only by disabling the [ShowNonWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~ShowNonWorkingHours.html) property.

{% tabs %}
{% higligh xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="Day" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     ShowNonWorkingHours="False"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.Day;
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.ShowNonWorkingHours = false;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView prevent Non working hours diplaying](dayview_images/dayview-display-working-hours)

## Non-Accessible timeslots
By using [NonAccessibleBlocks](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonAccessibleBlocks.html), you could limit or assign those time slots as non-accessible blocks, so you can allocate certain time slots to pre-defined events / activities such as lunch hour using `NonAccessibleBlocks` [StartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~StartHour.html), [EndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~EndHour.html), [Label](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~Label.html) and [Background](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~Background.html) properties.

{% tabs %}
{% higligh xaml %}
<Schedule:SfSchedule ScheduleType="Day">
    <Schedule:SfSchedule.NonAccessibleBlocks>
        <Schedule:NonAccessibleBlock Background="Black" StartHour="13" EndHour="14" Label="Lunch">
        </Schedule:NonAccessibleBlock> 
    </Schedule:SfSchedule.NonAccessibleBlocks>
</Schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Day;
schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock() { Background = new SolidColorBrush(Colors.Black), StartHour = 13, EndHour = 14, Label = "Lunch" });
this.grid.Children.Add(schedule);
{% endhighlight %}
{% endtabs %}

![WPF scheduler non accessible time slots](dayview_images/non-accessible-blocks.png)

### Customize Non-Accessible timeslots using template
The NonAccessible timeslots can be customized by [NonAccessibleBlockTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonAccessibleBlockTemplate.html) property.

{% tabs %}
{% higligh xaml %}
<syncfusion:SfSchedule.NonAccessibleBlockTemplate>
    <DataTemplate>
        <Border Background="LightGreen">
            <TextBlock Text="Meeting" Foreground="White" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
    </DataTemplate>
</syncfusion:SfSchedule.NonAccessibleBlockTemplate>
{% endhighlight %}
{% endtabs %}

![WPF scheduler non accessible time slots using template](dayview_images/non-accessible-blocks-template.png)

## Time formatting
You can customize the format for the time in day view by setting [MajorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickTimeFormat.html) and [MinorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickTimeFormat.html) property.

{% tabs %}
{% higligh xaml %}
<syncfusion:SfSchedule ScheduleType="Day" MajorTickTimeFormat="hh mm ss" MinorTickTimeFormat="mm ss"/>
{% endhighlight %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Day;
schedule.MajorTickTimeFormat = "hh mm ss";
schedule.MinorTickTimeFormat = "hh mm ss";
{% endhighlight %}
{% endtabs %}

![WPF schedular dayview time formatting](dayview_images/dayview-time-formatting.png)

## Time Label Appearance
### Changing Time Label Foreground
By setting scheduler's [MinorTickLabelStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickLabelStroke.html) and [MajorTickLabelStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickLabelStroke.html). you can customize the color for the labels that mention the time.

{% tabs %}
{% higligh xaml %}
<syncfusion:SfSchedule ScheduleType="Day" MajorTickLabelStroke="DarkRed" MinorTickLabelStroke="Red"/>
{% endhighlight %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Day;
schedule.MajorTickLabelStroke = Brushes.DarkRed;
schedule.MinorTickLabelStroke = Brushes.Red;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview time label foreground changes](dayview_images/dayview-time-label-foreground.png)

### Changing Time Label Strokes
By setting Scheduler's [MajorTickStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickStroke.html) and [MinorTickStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickStroke.html) property, you can customize the border color of the labels that mention the time. 

{% tabs %}
{% higligh xaml %}
<syncfusion:SfSchedule ScheduleType="Day" MajorTickStroke="LawnGreen" MinorTickStroke="LightBlue"/>
{% endhighlight %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Day;
schedule.MajorTickStroke = Brushes.LawnGreen;
schedule.MinorTickStroke = Brushes.LightBlue;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview time label border color changes](dayview_images/dayview-time-label-border.png)