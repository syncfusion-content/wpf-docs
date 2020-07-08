---
layout: post
title: Day, Week, Work Week views of Syncfusion WPF Scheduler | Scheduler
description: Learn how to customize the Scheduler Day,Week, Work Week views settings and its appearance in SfScheduler in WPF
platform: wpf
control: SfScheduler
documentation: ug
---

# Day View in WPF Scheduler (SfSchedule)
`Scheduler` supports to display the day, week, work week views and current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

## Change time interval
You can customize the interval of timeslots in all the day, week, work week views by using the `TimeInterval` property of `DaysViewSettings`.
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.TimeInterval = new System.TimeSpan(0, 120, 0);
{% endhighlight %}
{% endtabs %}

![Change Time Interval Height in WPF Scheduler](DaysView_Images/adding-Changetimeinterval.png)

N>If you modify the timeInterval value (in minutes), you need to change the time labels format by setting the timeFormat value to hh:mm.

## Change time interval height
You can customize the interval height of timeslots in day, week, work week views by setting `TimeIntervalHeight` property of `DaysViewSettings`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings 
            TimeIntervalHeight="120"/>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.TimeIntervalHeight = 120;
{% endhighlight %}
{% endtabs %}

![Change Time Interval Height in WPF Scheduler](DaysView_Images/adding-ChangeTimeIntervalHeight.png)

## Flexible working days and working hours
The default values for `StartHour` and `EndHour` are 0 and 24 to show all the timeslots in day, week, work week views. You can to set the `StartHour` and `EndHour` properties of `DaysViewSettings` to show only the required time duration for users. You can set `StartHour` and `EndHour` in time duration to show the required time duration in minutes.

{% tabs %}
{% highlight xaml %}
 <syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings 
            StartHour="8"
            EndHour="15"/>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.StartHour = 8;
Schedule.DaysViewSettings.EndHour = 15;
{% endhighlight %}
{% endtabs %}

![Flexible working days and working hours in WPF Scheduler](DaysView_Images/adding-Flexibleworkingdaysandworkinghours.png)

N>
* The `NonWorkingDays` property will applicable only for `workWeek` and `TimelineWorkWeek` views only, and not applicable for the remaining views.
* Scheduler Appointments UI, which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If custom timeInterval is given, then the number of time slots calculated based on the given `TimeInterval` should result in integer value (total minutes % timeInterval = 0), otherwise next immediate time interval that result in integer value when divide total minutes of a day will be considered. For example, if TimeInterval=2 Hours 15 minutes and total minutes = 1440 (24 Hours per day), then `TimeInterval` will be changed to ‘144’ (1440%144=0) by considering (total minutes % TimeInterval = 0), it will return integer value for time slots rendering.
* If the custom `StartHour` and `EndHour` are given, then the number of time slots calculated based on given `StartHour` and `EndHour` should result in integer value, otherwise next immediate `TimeInterval` will be considered until the result is integer value. For example, if `StartHour` is 9 (09:00AM), `EndHour` is 18.25 (06:15 PM), `TimeInterval` is 30 minutes, and total minutes = 555 ((18.25-9)*60), then the `TimeInterval` will be changed to ’37 minutes’ (555%37=0) by considering (total minutes % timeInterval = 0). it will return integer value for time slots rendering.

## Special time regions
You can restrict the user interaction such as selection and highlights specific regions of time in day, week, work week views by adding the `SpecialTimeRegions` property of `SfScheduler`. You need to set the `StartTime` and `EndTime` properties of `SpecialTimeRegion` to create a `SpecialTimeRegion`, you can use the timeZone property to set the specific timezone for Start and end time of `SpecialTimeRegion`. The `SpecialTimeRegion` will display the text or image on it that set to the text or icon property of `SpecialTimeRegion`.

### Selection restriction in timeslots
You can enable or disable the touch interaction of `SpecialTimeRegion` using the `CanEdit` property of `SpecialTimeRegion`. By default, its value is true.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week" >
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings>
            <syncfusion:DaysViewSettings.SpecialTimeRegions>
                <syncfusion:SpecialTimeRegion
                    StartTime="2020/07/07 13:0:0"
                    EndTime="2020/07/07 14:0:0"
                    CanEdit="False"
                    Text="Lunch"
                    Background="Black"
                    Foreground="White"/>
            </syncfusion:DaysViewSettings.SpecialTimeRegions>
        </syncfusion:DaysViewSettings>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.SpecialTimeRegions.Add(new SpecialTimeRegion
{
    StartTime = new System.DateTime(2020, 07, 07, 13, 0, 0),
    EndTime = new System.DateTime(2020, 07, 07, 14, 0, 0),
    Text = "Lunch",
    CanEdit = false,
    Background = Brushes.Black,
    Foreground = Brushes.White
});
{% endhighlight %}
{% endtabs %}

![Selection restriction in timeslots in WPF Scheduler](DaysView_Images/adding-Selectionrestrictionintimeslots.png)

N>NOTE
This property only restricts the interaction on region and it does not restrict the following:
* Programmatic selection (if the user updates the selected date value dynamically)
* Does not clear the selection when the user selects the region and dynamically change
the `CanEdit` property to false
* It does not restrict appointment interaction when the appointment placed
in the region
* It does not restrict the appointment rendering on a region, when appointments are loaded from data services or adding programmatically.

### Recurring time region
The recurring time region on a daily, weekly, monthly, or yearly interval. The recurring special time regions can be created by setting the `RecurrenceRule` property in `SpecialTimeRegion`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week" >
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings>
            <syncfusion:DaysViewSettings.SpecialTimeRegions>
                <syncfusion:SpecialTimeRegion
                    StartTime="2020/07/05 13:0:0"
                    EndTime="2020/07/05 14:0:0"
                    CanEdit="False"
                    Text="Lunch"
                    Background="Black"
                    Foreground="White"
                    RecurrenceRule="FREQ=DAILY;INTERVAL=1"/>
            </syncfusion:DaysViewSettings.SpecialTimeRegions>
        </syncfusion:DaysViewSettings>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.SpecialTimeRegions.Add(new SpecialTimeRegion
{
    StartTime = new System.DateTime(2020, 07, 05, 13, 0, 0),
    EndTime = new System.DateTime(2020, 07, 05, 14, 0, 0),
    Text = "Lunch",
    CanEdit = false,
    Background = Brushes.Black,
    Foreground = Brushes.White,
    RecurrenceRule= "FREQ=DAILY;INTERVAL=1"
});
{% endhighlight %}
{% endtabs %}
![Selection restriction in timeslots in WPF Scheduler](DaysView_Images/adding-Recurringtimeregion.png)

### Recurrence exception dates
You can delete any of occurrence that is an exception from the recurrence pattern time region by using the `RecurrenceExceptionDates` property of `SpecialTimeRegion`. The deleted occurrence date will be considered as a recurrence exception date.
{% tabs %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
DateTime recurrenceExceptionDates = new DateTime(2020, 07, 06, 10, 0, 0);
DateTime recurrenceExceptionDates1 = new DateTime(2020, 07, 08, 10, 0, 0);
DateTime recurrenceExceptionDates2 = new DateTime(2020, 07, 10, 10, 0, 0);
Schedule.DaysViewSettings.SpecialTimeRegions.Add(new SpecialTimeRegion
{
    StartTime = new System.DateTime(2020, 05, 05, 12, 0, 0),
    EndTime = new System.DateTime(2020, 05, 05, 13, 0, 0),
    Text = "Lunch",
    CanEdit = false,
    Background = Brushes.Black,
    Foreground = Brushes.White,
    RecurrenceRule = "FREQ=DAILY;INTERVAL=1",
    RecurrenceExceptionDates = new ObservableCollection<DateTime>()
{
    recurrenceExceptionDates,
    recurrenceExceptionDates1,
    recurrenceExceptionDates2,
}
});
{% endhighlight %}
{% endtabs %}

![Recurrence exception dates in WPF Scheduler](DaysView_Images/adding-Recurrenceexceptiondates.png)

### Special time region customization
The `SpecialTimeRegion` background color can be customized by using the `Background` and `SpecialTimeRegionTemplate` properties of `SpecialTimeRegion` that is used to customize the text style for the image of the `SpecialTimeRegion`.
{% tabs %}
{% highlight xaml %}
 <Window.Resources>
    <DataTemplate x:Key="specialRegionTemplate">
        <Grid Background="{Binding Background}"
            HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch">
        <Image x:Name="Image"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            Source="../Image/Fork.png"/>
        </Grid>
    </DataTemplate>
</Window.Resources>
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings                 SpecialTimeRegionTemplate="{StaticResource specialRegionTemplate}">
            <syncfusion:DaysViewSettings.SpecialTimeRegions>
                <syncfusion:SpecialTimeRegion
                    StartTime="01/01/2020 13:0:0"
                    EndTime="01/01/2020 14:0:0"
                    CanEdit="False"
                    Text="LUNCH"
                    RecurrenceRule="FREQ=DAILY;INTERVAL=1"
                    Foreground="Black"
                    Background="#FFF5F5F5"/>
            </syncfusion:DaysViewSettings.SpecialTimeRegions>
        </syncfusion:DaysViewSettings>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

![Special time region customization in WPF Scheduler](DaysView_Images/adding-Specialtimeregioncustomization.png)

## Full screen scheduler
Scheduler time interval height can be adjusted based on screen height by changing the value of `TimeIntervalHeight` property to -1. It will auto-fit to the screen height and width.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings 
            TimeIntervalHeight="-1"/>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.TimeIntervalHeight = -1;
{% endhighlight %}
{% endtabs %}

![Full screen scheduler in WPF Scheduler](DaysView_Images/adding-FullscreenScheduler.png)

## Change time ruler size
You can customize the size of the time ruler view where the labels mentioning the time are placed by using the `TimeRulerSize` property of `DayViewSettings`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week" >
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings   
            TimeRulerSize="100">
        </syncfusion:DaysViewSettings>
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.TimeRulerSize = 100;
{% endhighlight %}
{% endtabs %}

![Change time ruler size in WPF Scheduler](DaysView_Images/adding-Changetimerulersize.png)

## Minimum appointment duration
The `MinimumAppointmentDuration` property in `DayViewSettings` is to set an arbitrary height to appointments when it has minimum duration, in day, week, work week views, so that the subject can be readable.
{% tabs %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.MinimumAppointmentDuration = new System.TimeSpan(0, 120, 0);
{% endhighlight %}
{% endtabs %}

N>NOTE
* The `MinimumAppointmentDuration` value will be set, when an appointment duration value lesser than `MinimumAppointmentDuration`.
* Appointment duration value will be set, when the appointment duration value greater than `MinimumAppointmentDuration`.
* `TimeInterval` value will be set, when `MinimumAppointmentDuration` greater than `TimeInterval` with lesser appointment duration.
* All day Appointment does not support `MinimumAppointmentDuration`.

## Time text formatting
You can customize the format for the labels mentioning the time, by setting the `TimeRulerFormat` property of `DayViewSettings` in `Scheduler`.
{% tabs %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.TimeRulerFormat = "hh mm";
Schedule.DaysViewSettings.TimeInterval = new System.TimeSpan(0, 30, 0);
{% endhighlight %}
{% endtabs %}
![Time text formatting in WPF Scheduler](DaysView_Images/adding-Timetextformatting.png)

## ViewHeader
You can customize the default appearance of view header in day, week, work week views by setting `ViewHeaderDateFormat`, `ViewHeaderHeight``ViewHeaderDayFormat`and  `ViewHeaderTemplate` of `DaysViewSettings`.

### View header text formatting
You can customize the date and day format of ViewHeader by using the `ViewHeaderDateFormat` and `ViewHeaderDayFormat` properties of `DaysViewSettings`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings 
            ViewHeaderDayFormat="dddd"
            ViewHeaderDateFormat="dd"/>
        </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.ViewHeaderDateFormat = "dd";
Schedule.DaysViewSettings.ViewHeaderDayFormat = "dddd";
{% endhighlight %}
{% endtabs %}
![View header text formatting in WPF Scheduler](DaysView_Images/adding-Viewheadertextformatting.png)

### View header height
You can customize the height of the ViewHeader in day , week , work week views by setting `ViewHeaderHeight` property of `DaysViewSettings` in `SfScheduler`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings
            ViewHeaderHeight="100"/>
        </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.Week;
Schedule.DaysViewSettings.ViewHeaderDateFormat = "100";
{% endhighlight %}
{% endtabs %}
![View header height in WPF Scheduler](DaysView_Images/adding-Viewheaderheight.png)

### ViewHeader appearance customization
You can customize the default appearance of view header by setting `ViewHeaderTemplate` property of `DaysViewSettings` in `SfScheduler`.
{% tabs %}
{% highlight xaml %}
<Window.Resources>
<DataTemplate x:Key="viewHeaderTemplate">
    <StackPanel Background="Green"  
        Width="2000"
        VerticalAlignment="Stretch" 
        HorizontalAlignment="Stretch"
        Orientation="Vertical">
    <TextBlock 
        HorizontalAlignment="Left" 
        Margin="20,0,0,0" 
        Foreground="#FFFFFF"
        FontFamily="Arial"
        Text="{Binding DateText}"
        FontSize="25"
        TextTrimming="CharacterEllipsis"
        TextWrapping="Wrap" />
    <TextBlock 
        HorizontalAlignment="Left"  Margin="20,0,0,0" 
        Foreground="#FFFFFF"
        FontFamily="Arial"
        Text="{Binding DayText}"
        FontSize="10"
        TextTrimming="CharacterEllipsis"
        TextWrapping="Wrap" />
    </StackPanel>
</DataTemplate>
</Window.Resources>
{% endhighlight %}
{% endtabs %}
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings 
            ViewHeaderTemplate="{StaticResource viewHeaderTemplate}" />
        </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

![ViewHeader appearance customization in WPF Scheduler](DaysView_Images/adding-ViewHeaderappearancecustomization.png)

## Change all day appointment display count
The schedule All Day panel appointment count can be customized by `MinimumAllDayAppointmentsCount` and `MaximumAllDayAppointmentsCount` properties of `DaysViewSettings`.

 ### Minimum all day appointments count
 You can customize the all day appointments count of the `AllDay` panel in day , week , work week views by setting `MinimumAllDayAppointmentsCount` property of `DaysViewSettings` in `SfScheduler`.

{% tabs %}
{% highlight xaml %}
 <syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings MaximumAllDayAppointmentsCount="2" />
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

### Maximum all day appointments count
 You can customize the all day appointments count of the `AllDay` panel in day , week , work week views by setting `MaximumAllDayAppointmentsCount` property of `DaysViewSettings` in `SfScheduler`.
 {% tabs %}
{% highlight xaml %}
 <syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
    <syncfusion:SfScheduler.DaysViewSettings>
        <syncfusion:DaysViewSettings MaximumAllDayAppointmentsCount="2" />
    </syncfusion:SfScheduler.DaysViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

![Change all day appointment display count in WPF Scheduler](DaysView_Images/adding-Changealldayappointmentdisplaycount.png)