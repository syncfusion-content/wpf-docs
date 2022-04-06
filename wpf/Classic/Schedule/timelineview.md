---
layout: post
title: Timeline View in WPF SfSchedule Control | Syncfusion
description: Learn here all about Timeline View support in Syncfusion WPF Schedule (Classic) control, its elements and more details.
platform: wpf
control: SfSchedule
documentation: ug
---

# Timeline View in WPF Schedule (Classic)
`Timeline` view displays the dates with the appropriate day count in the horizontal time axis. When moving right or left, you can see the past or future events. With an intuitive drag-and-drop feature, each view shows events accurately through time slots.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.ScheduleType= ScheduleType.TimeLine;
{% endhighlight %}
{% endtabs %}

## Header date format
Scheduler supports to customize the header date format of the day, week, workweek and timeline view using [HeaderDateFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_HeaderDateFormat) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule HeaderDateFormat="dd-MMMM-yyyy"/>
{% endhighlight %}
{% highlight c#%}
this.schedule.HeaderDateFormat = "dd-MMMM-yyyy";

{% endhighlight %}
{% endtabs %}

![WPF scheduler timeline view header format](timelineview_images/timelineview-header-date-format.png)

## Time formatting
Scheduler supports to customize time format for day, week, workweek and timeline views using [MajorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickTimeFormat) and [MinorTickTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickTimeFormat) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickTimeFormat="hh mm ss" MinorTickTimeFormat="mm ss"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickTimeFormat = "hh mm ss";
this.schedule.MinorTickTimeFormat = "hh mm ss";
{% endhighlight %}
{% endtabs %}

![WPF schedular timeline view time formatting](timelineview_images/timelineview-time-format.png)

## Change time interval
Scheduler supports to change the time interval using [TimeInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeInterval) property.


{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule TimeInterval = "OneHour" />
{% endhighlight %}
{% highlight c#%}
this.schedule.TimeInterval = TimeInterval.OneHour;
{% endhighlight %}
{% endtabs %}

![WPF scheduler timeline view timeinterval](timelineview_images/timelineview-change-time-interval.png)

## Change time interval height
Scheduler supports to change the time interval height using [IntervalHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_IntervalHeight) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule IntervalHeight = 100 />
{% endhighlight %}
{% highlight c#%}
this.schedule.IntervalHeight = 100;
{% endhighlight %}
{% endtabs %}

![WPF scheduler timeline view interval height](timelineview_images/timelineview-change-time-interval-height.png)

## Change between 12-hour and 24-hour format
Scheduler supports to change the time format from 12hours to 24 hours using [TimeMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeMode) property.

{% tabs %}
{% highlight xaml %}
<Grid Background="White" Name="grid">
    <Schedule:SfSchedule ScheduleType="TimeLine" TimeMode="TwentyFourHours" >     
    </Schedule:SfSchedule>
</Grid>
{% endhighlight  %}
{% highlight c# %}
schedule.ScheduleType = ScheduleType.TimeLine;
schedule.TimeMode = TimeModes.TwentyFourHours;
{% endhighlight  %}
{% endtabs %}

![WPF Scheduler timeline view 24 hours](timelineview_images/timelineview-24-hours-time-mode.png)

## Non-accessible timeslots
Scheduler supports to mark certain timeslots as non-accessible timeslots using [NonAccessibleBlocks](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonAccessibleBlocks) property. User can’t interact over the timeslot marked as non-accessible timeslots. 

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

![WPF scheduler non accessible time slots](timelineview_images/timelineview-non-accessible-timeslots.png)

### Customize non-accessible timeslots using template
Scheduler supports to customize the non-accessible timeslots using [NonAccessibleBlockTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonAccessibleBlockTemplate) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule.NonAccessibleBlockTemplate>
    <DataTemplate>
        <Border Background="{Binding Color}">
            <TextBlock Text="{Binding EventName}" Foreground="White" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
    </DataTemplate>
</syncfusion:SfSchedule.NonAccessibleBlockTemplate>
{% endhighlight %}
{% endtabs %}

![WPF scheduler non accessible time slots using template](timelineview_images/timelineview-non-accessible-timeslots-template.png)

## Collapsed hours
Scheduler supports to hide the selected hours by using [CollapsedHours](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CollapsedHours) property. [ScheduleCollapsedHours](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleCollapsedHour.html) does have the following properties.

[StartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleCollapsedHour.html#Syncfusion_UI_Xaml_Schedule_ScheduleCollapsedHour_StartHour) - To set start time of collapsed hour.
[EndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleCollapsedHour.html#Syncfusion_UI_Xaml_Schedule_ScheduleCollapsedHour_EndHour) - To set end time of collapsed hour.
[Background](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleCollapsedHour.html#Syncfusion_UI_Xaml_Schedule_ScheduleCollapsedHour_Background) - To set the background of collapsed hours.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule Background="White" x:Name="schedule" ScheduleType="TimeLine">
    <schedule:SfSchedule.CollapsedHours>
        <schedule:ScheduleCollapsedHour StartHour="1" EndHour="5"  Background="Red"/>
    </schedule:SfSchedule.CollapsedHours>        
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
this.schedule.CollapsedHours.Add(new ScheduleCollapsedHour() { StartHour = 1, EndHour = 5, Background = new SolidColorBrush(Colors.Red)});
{% endhighlight %}
{% endtabs %}

![WPF Scheduler timeline view collapsed hours](timelineview_images/timelineview-collapse-hour.png)

## Change working hours
Working hours of Scheduler will be differentiated with non-working hours by separate color using [IsHighLightWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_IsHighLightWorkingHours) property for day, week, workweek and timeline views. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkEndHour) properties.

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

![WPF scheduler timeline view working hours](timelineview_images/timelineview-change-working-hour.png)

###  Display working hours only
Scheduler supports to display the working hours only by disabling the [ShowNonWorkingHours](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ShowNonWorkingHours) property.

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

![WPF scheduler timeline view prevent Non working hours diplaying](timelineview_images/timelineview-non-working-hour.png)

### Change non-working hours background
Scheduler supports to change the background color for non-working hours using [NonWorkingHourBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonWorkingHourBrush) property.

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

![WPF scheduler timeline view Non working hours background changes](timelineview_images/timelineview-non-working-hour-background.png)

## Current time indicator
Scheduler supports to display the current time indicator using the [CurrentTimeIndicatorVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CurrentTimeIndicatorVisibility) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule ScheduleType="TimeLine" CurrentTimeIndicatorVisibility="Visible"/>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleType = ScheduleType.TimeLine;
this.schedule.CurrentTimeIndicatorVisibility = Visibility.Visible;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler timeline view current time indicator](timelineview_images/timelineview-current-time-indicator.png)

### Customize current time indicator
Scheduler supports to customize the current time indicator using [CurrentTimeIndicatorTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CurrentTimeIndicatorTemplate) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine" CurrentTimeIndicatorVisibility="Visible">
    <Schedule:SfSchedule.CurrentTimeIndicatorTemplate>
        <DataTemplate>
            <Border Background="DarkGreen" Height="10" Width="100"></Border>
        </DataTemplate>
    </Schedule:SfSchedule.CurrentTimeIndicatorTemplate>
</Schedule:SfSchedule>     
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleType = ScheduleType.TimeLine;
schedule.CurrentTimeIndicatorVisibility = Visibility.Visible;
schedule.CurrentTimeIndicatorTemplate = (DataTemplate)this.Resources["CurrentTimeIndicatorTemplate"];
{% endhighlight %}
{% endtabs %}

![WPF Scheduler timeline view customize current time indicator](timelineview_images/current-time-indicator-template.png)

## Change hours or minutes time label visibility
Scheduler supports to visible/collapse the hours and minutes time label visiblity using [MajorTickVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickVisibility) and [MinorTickVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickVisibility) properties.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule ScheduleType="TimeLine" MajorTickVisibility="Collapsed" MinorTickVisibility="Collapsed" />
{% endhighlight %}
{% highlight c#%}
this.schedule.ScheduleType = ScheduleType.TimeLine;
this.schedule.MajorTickVisibility = Visibility.Collapsed;
this.schedule.MinorTickVisibility = Visibility.Collapsed;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler timeline view hiding time labels](timelineview_images/major-minor-label-visibility.png)

## Appearance

### Changing time label background

Scheduler supports to change the time slot label background using [HeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_HeaderBackground) property.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule HeaderBackground="LightSkyBlue" />
{% endhighlight %}
{% highlight c#%}
this.schedule.HeaderBackground = Brushes.LightSkyBlue;
{% endhighlight %}
{% endtabs %}

![WPF scheduler timeline view header background](timelineview_images/timeline-header-background.png)

### Stroke customization
In Scheduler control, major, minor horizontal and vertical lines drawn in the day, week, workweek and timeline views by using following properties,

####  Property Table

<table>
<tr>
<th>
API Name</th><th>
Data Type</th><th>
Description</th></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickStroke.html">MajorTickStroke</a></td><td>
Brush</td><td>
Used to customize the major line stroke of the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickStroke.html">MinorTickStroke</a></td><td>
Brush</td><td>
Used to customize the minor line stroke of the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MinorTickLabelStroke.html">MajorTickLabelStroke</a></td><td>
Brush</td><td>
Used to customize the major line label stroke in the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~MajorTickLabelStroke.html">MinorTickLabelStroke</a></td><td>
Brush</td><td>
Used to customize the minor line label stroke of the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickStrokeDashArray">MajorTickStrokeDashArray</a></td><td>
DoubleCollection</td><td>
Used to customize the major line stroke dash array of the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickStrokeDashArray">MinorTickStrokeDashArray</a></td><td>
DoubleCollection</td><td>
Used to customize the minor line stroke dash array of the day, week, workweek and timeline views.</td></tr>
<tr>
<td>
<a href="https://help.syncfusion.com/cr/wpf/Syncfusion.SfSchedule.WPF~Syncfusion.UI.Xaml.Schedule.SfSchedule~DayViewVerticalLineStroke.html">DayViewVerticalLineStroke</a></td><td>
Brush</td><td>
Used to customize the vertical line stroke of the day, week and workweek view.</td></tr>
</table>

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule MajorTickLabelStroke="DarkRed" 
                       MinorTickLabelStroke="Red"
                       MajorTickStroke="LawnGreen" 
                       MinorTickStroke="LightBlue"
                       MajorTickStrokeDashArray="5,10" 
                       MinorTickStrokeDashArray="5,5"
                       DayViewVerticalLineStroke="Brown"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.MajorTickLabelStroke = Brushes.DarkRed;
this.schedule.MinorTickLabelStroke = Brushes.Red;
this.schedule.MajorTickStroke = Brushes.LawnGreen;
this.schedule.MinorTickStroke = Brushes.LightBlue;
this.schedule.MajorTickStrokeDashArray = new DoubleCollection(new Double[] { 5, 10 });
this.schedule.MinorTickStrokeDashArray = new DoubleCollection(new Double[] { 5, 5 });
this.schedule.DayViewVerticalLineStroke = Brushes.Brown;
{% endhighlight %}
{% endtabs %}

![WPF scheduler timeline view stroke customization](timelineview_images/timeline-stroke-customization.png)

### Current day highlighting
Scheduler supports to change current day background and foreground for all views using [CurrentDateBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CurrentDateBackground) and [CurrentDateForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CurrentDateForeground) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule CurrentDateBackground="Brown" CurrentDateForeground="White"/>
{% endhighlight %}
{% highlight c# %}
this.schedule.CurrentDateBackground = Brushes.Brown;
this.schedule.CurrentDateForeground = Brushes.White;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler timeline view current date background](timelineview_images/timeline-currentdate-background.png)