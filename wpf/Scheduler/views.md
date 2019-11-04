---
layout: post
title: Customization of Day, Week and WorkWeek in WPF Scheduler | Syncfusion.
description: This section explains about the  appearance customization of Day, Week and WorkWeek views for WPF Scheduler.
platform: wpf
control: SfSchedule
documentation: ug
---

## Views (DayView, WeekView and WorkWeekView)
Scheduler provides the following different types of views.

* Day view
* Week view
* WorkWeek view
* Timeline View - Refer [scheduler timeline view](https://help.syncfusion.com/wpf/sfschedule/getting-started#timeline-view) documentation for more customization details.
* Month View - Refer [scheduler month view](https://help.syncfusion.com/wpf/sfschedule/getting-started#month-view) documentation for more customization details.

This topic covers customization of day, week and workweek views of the scheduler which shares common properties.

N> This topic explains all customization using day view. But the same applies for week and workweek views also. if you want to make customization specific to views, then please refer [link](#change-the-settings-based-on-the-views-at-run-time)

## Header date format
Scheduler supports to customize the default header date format of the day, week, workweek and timeline view by using the [HeaderDateFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~HeaderDateFormat.html) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule HeaderDateFormat="dd-MMMM-yyyy"/>
{% endhighlight %}
{% highlight c#%}
this.schedule.HeaderDateFormat = "dd-MMMM-yyyy";

{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview header format](views_images/dayview-header-format.png)

## Time formatting
Scheduler supports to customize time format for day, week, workweek and timeline views by using [MajorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickTimeFormat.html) and [MinorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickTimeFormat.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickTimeFormat="hh mm ss" MinorTickTimeFormat="mm ss"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickTimeFormat = "hh mm ss";
this.schedule.MinorTickTimeFormat = "hh mm ss";
{% endhighlight %}
{% endtabs %}

![WPF schedular dayview time formatting](views_images/dayview-time-formatting.png)

## Enable auto formatting
When reducing the size of the schedule in week and month views, headers may be only partially shown. To avoid incompletely displayed headers, automatic formatting can be enabled by setting the [EnableAutoFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~EnableAutoFormat.html) property of the Scheduler control as `true`. If this preopty enbaled, `HeaderDateFormat` settings will not apply.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="schedule" Background="White"
                        Height="400" Width="500"
                        EnableAutoFormat="True"
                        ScheduleType="Week">
</syncfusion:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.Background = new SolidColorBrush(Colors.White);
schedule.Height = 400;
schedule.Width = 500;
schedule.EnableAutoFormat = true;
schedule.ScheduleType = ScheduleType.Week;
{% endhighlight %}
{% endtabs %}

![WPF WeekView enabling auto formatting](views_images/weekview-enabling-auto-formatting.png)

After changing the window size by resizing the window.

![WPF WeekView resizing window with enabling auto formatting](views_images/weekview-enabling-auto-formatting-sizechanged.png)


## Change time interval
Scheduler supports to change the time interval by using [TimeInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~TimeInterval.html) property.


{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule TimeInterval = "OneHour" />
{% endhighlight %}
{% highlight c#%}
this.schedule.TimeInterval = TimeInterval.OneHour;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview timeinterval](views_images/dayview-time-interval.png)

## Change time interval height
Scheduler supports to change the time interval height by using [IntervalHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~IntervalHeight.html) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule IntervalHeight = 100 />
{% endhighlight %}
{% highlight c#%}
this.schedule.IntervalHeight = 100;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview interval height](views_images/dayview-interval-height.png)

## Non-accessible timeslots
Scheduler supports to limit or assign those time slots as non-accessible timeslots by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonAccessibleBlocks.html) property. So, you can allocate certain time slots to pre-defined events / activities such as lunch hour using `NonAccessibleBlocks` [StartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~StartHour.html), [EndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~EndHour.html), [Label](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~Label.html) and [Background](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.NonAccessibleBlock~Background.html) properties.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule>
    <Schedule:SfSchedule.NonAccessibleBlocks>
        <Schedule:NonAccessibleBlock Background="Black" StartHour="13" EndHour="14" Label="Lunch">
        </Schedule:NonAccessibleBlock> 
    </Schedule:SfSchedule.NonAccessibleBlocks>
</Schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
this.schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock() { Background = new SolidColorBrush(Colors.Black), StartHour = 13, EndHour = 14, Label = "Lunch" });
{% endhighlight %}
{% endtabs %}

![WPF scheduler non accessible time slots](views_images/non-accessible-blocks.png)

### Customize non-accessible timeslots using template
Scheduler supports to customize the non-accessible timeslots by using [NonAccessibleBlockTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonAccessibleBlockTemplate.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule.NonAccessibleBlockTemplate>
    <DataTemplate>
        <Border Background="LightGreen">
            <TextBlock Text="Meeting" Foreground="White" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
    </DataTemplate>
</syncfusion:SfSchedule.NonAccessibleBlockTemplate>
{% endhighlight %}
{% endtabs %}

![WPF scheduler non accessible time slots using template](views_images/non-accessible-blocks-template.png)

## Change first day of week
Scheduler supports to switch the first week with any day by using [FirstDayOfWeek](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~FirstDayOfWeek.html) property.

`Day` - `FirstDayOfWeek` of Scheduler is not applicable for day view as it displays only one day.

`Week` - By default, scheduler control will be rendered with `Sunday` as the first day of the week.

`WorkWeek` - By default, scheduler control will be rendered with `Monday` as the first day. `Saturday` and `Sunday` has considered as a non working days. 

## Change non-working days
By default Schedule, will be considered `Saturday` and `Sunday` as a non working days. You can customize that using [NonWorkingDays](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonWorkingDays.html) property.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="WorkWeek" NonWorkingDays="Monday,Tuesday"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.WorkWeek;
this.schedule.NonWorkingDays = DayOfWeek.Monday.ToString() + "," + DayOfWeek.Tuesday.ToString();
{% endhighlight %}
{% endtabs %}

![WPF Scheduler WorkWeekView non working days](views_images/workweek-non-working-days.png)

## Collapsed hours
Scheduler supports to hide the selected hours by using [CollapsedHours](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~CollapsedHours.html) property. 

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule Background="White" x:Name="schedule" ScheduleType="Week">
    <schedule:SfSchedule.CollapsedHours>
        <schedule:ScheduleCollapsedHour StartHour="1" EndHour="5"  Background="Red"/>
    </schedule:SfSchedule.CollapsedHours>        
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
this.schedule.CollapsedHours.Add(new ScheduleCollapsedHour() { StartHour = 1, EndHour = 5, Background = new SolidColorBrush(Colors.Red)});
{% endhighlight %}
{% endtabs %}

![WPF Scheduler DayView collapsed hours](views_images/dayview-collapsed-hours.png)

## Change working hours
Working hours of Scheduler will be differentiated with non-working hours by separate color using [IsHighLightWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~IsHighLightWorkingHours.html) property for day, week, workweek and timeline views. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~WorkEndHour.html) properties.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     IsHighLightWorkingHours="True"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.IsHighLightWorkingHours = true;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView working hours](views_images/dayview-working-hours.png)

###  Display working hours only
Scheduler supports to display the working hours only by disabling the [ShowNonWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~ShowNonWorkingHours.html) property.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     ShowNonWorkingHours="False"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.ShowNonWorkingHours = false;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView prevent Non working hours diplaying](views_images/dayview-display-working-hours.png)

### Change non-working hours background
Scheduler supports to change the background color for non-working hours by using [NonWorkingHourBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~NonWorkingHourBrush.html) property.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" 
                     WorkStartHour="9"
                     WorkEndHour="12"
                     NonWorkingHourBrush="LightSteelBlue"
                     IsHighLightWorkingHours="True"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.WorkStartHour = 9;
this.schedule.WorkEndHour = 12;
this.schedule.NonWorkingHourBrush = Brushes.LightSteelBlue;
this.schedule.IsHighLightWorkingHours = true;
{% endhighlight %}
{% endtabs %}

![WPF scheduler DayView Non working hours background changes](views_images/dayview-non-working-hours-background.png)

## Appearance

### Changing time label background

Scheduler supports to change the time slot label background by using [HeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~HeaderBackground.html) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule HeaderBackground="LightSkyBlue" />
{% endhighlight %}
{% highlight c#%}
this.schedule.HeaderBackground = Brushes.LightSkyBlue;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview header background](views_images/dayview-header-background.png)

### Changing time label foreground
Scheduler supports to change the time label foreground by using [MinorTickLabelStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickLabelStroke.html) and [MajorTickLabelStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickLabelStroke.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickLabelStroke="DarkRed" MinorTickLabelStroke="Red"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickLabelStroke = Brushes.DarkRed;
this.schedule.MinorTickLabelStroke = Brushes.Red;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview time label foreground changes](views_images/dayview-time-label-foreground.png)

### Changing timeslots line color
Scheduler supports to change the time slots line color by using [MajorTickStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickStroke.html) and [MinorTickStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickStroke.html) property. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickStroke="LawnGreen" MinorTickStroke="LightBlue"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickStroke = Brushes.LawnGreen;
this.schedule.MinorTickStroke = Brushes.LightBlue;
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview time label border color changes](views_images/dayview-time-label-border.png)

### Changing timeslots line style
Scheduler supports to customize the major/minor line stroke style of the day, week, workweek and time line views.

 {% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickStroke="Red" MajorTickStrokeDashArray="5,10" MinorTickStroke="Blue" MinorTickStrokeDashArray="5,5"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickStroke = Brushes.Red;
this.schedule.MajorTickStrokeDashArray="5,10";
this.schedule.MinorTickStroke = Brushes.Blue;
this.schedule.MinorTickStrokeDashArray="5,5";
{% endhighlight %}
{% endtabs %}

![WPF scheduler dayview time slots line style](views_images/dayview-timeslots-line-style.png)

### Changing vertical line color
Scheduler supports to change the vertical line for day, week and workweek view by using [DayViewVerticalLineStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~DayViewVerticalLineStroke.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule ScheduleType="WorkWeek" DayViewVerticalLineStroke="Brown"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType = ScheduleType.WorkWeek;
this.schedule.DayViewVerticalLineStroke = Brushes.Brown;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler WorkweekView vertical line color changes](views_images/workweekview-vertical-line-color.png)

## Current day highlighting
Scheduler supports to change current day background and foreground for all views by using [CurrentDateBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~CurrentDateBackground.html) and [CurrentDateForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~CurrentDateForeground.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule CurrentDateBackground="Brown" CurrentDateForeground="White"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.CurrentDateBackground = Brushes.Brown;
this.schedule.CurrentDateForeground = Brushes.White;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler WorkWeekView current date background](views_images/workweek-current-date-background.png)

## Change schedule view settings based on the views at run time
Scheduler supports to notify before that changing the schedule view by using [ScheduleTypeChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~ScheduleTypeChanging_EV.html) event. By this event, the appearance can be adjusted depending on the view.

For example, if you want to change the header date format based on the schedule view, you can use this event. Please refer the following code example,

{% tabs %}
{% highlight c# %}
this.schedule.ScheduleTypeChanging += Schedule_ScheduleTypeChanging;
private void Schedule_ScheduleTypeChanging(object sender, ScheduleTypeChangingEventArgs e)
{      
    switch (e.NewValue)
    {
        case ScheduleType.Day:
            this.schedule.HeaderDateFormat = "dd-MMM-yyyy";
            break;
        case ScheduleType.Week:
            this.schedule.HeaderDateFormat = "dd-MMM";
            break;
        case ScheduleType.WorkWeek:
            this.schedule.HeaderDateFormat = "dd MMM";
            break;
    }
}
{% endhighlight %}
{% endtabs %}

![WPF Scheduler appearance customization based on ScheduleType at run time](views_images/dayview-runtime-changes.png)
