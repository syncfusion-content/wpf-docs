---
layout: post
title: Timeline month view of Syncfusion WPF Scheduler | Scheduler
description: Learn how to customize the Scheduler Timeline month view settings and its appearance in SfScheduler in WPF
platform: wpf
control: SfScheduler
documentation: ug
---
# Timeline month View in WPF Scheduler (SfScheduler)
`TimelineMonth` view of scheduler displays days of a specific  month in horizontal axis and current month will be visible intially by default. You can see the past or future dates by scrolling to the right or left. The current date color is differentiated from other dates of the current month.

## Change time interval size
You can customize the interval size of timeslots in `TimelineMonth` view by setting `TimeIntervalSize` property of `TimelineViewSettings`. By default time interval size for timeline month view is 150.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler" ViewType="TimelineMonth">
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings 
            TimeIntervalSize="100"/>
    </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Scheduler.ViewType = SchedulerViewType.TimelineMonth;
Scheduler.TimelineViewSettings.TimeIntervalSize = 100;
{% endhighlight %}
{% endtabs %}

## Full screen scheduler
Scheduler time interval size can be adjusted based on screen height by changing the value of `TimeIntervalSize` property to -1. It will auto-fit to the screen height and width.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler" ViewType="TimelineMonth">
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings 
            TimeIntervalSize="-1"/>
    </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Scheduler.ViewType = SchedulerViewType.TimelineMonth;
Scheduler.TimelineViewSettings.TimeIntervalSize = -1;
{% endhighlight %}
{% endtabs %}

## Appointment height
You can customize the height of the appointment in `TimelineMonth` view using the [TimelineAppointmentHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.TimelineViewSettings.html#Syncfusion_UI_Xaml_Scheduler_TimelineViewSettings_TimelineAppointmentHeight) property of `TimelineViewSettings`. By default, its value is 20.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="TimelineMonth"> 
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings 
            TimelineAppointmentHeight="50">
        </syncfusion:TimelineViewSettings>
    </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Schedule.ViewType = SchedulerViewType.TimelineMonth;
Schedule.TimelineViewSettings.TimelineAppointmentHeight = 50;
{% endhighlight %}
{% endtabs %}

## Blackout dates
You can disable the interaction for certain dates in the scheduler `TimelineMonth` view by adding those specific dates to the `BlackoutDates` collection property of `SfScheduler`. Using this, you can allocate or restrict specific dates for predefined events.

{% tabs %}
{% highlight c#%}
this.Schedule.ViewType = SchedulerViewType.Month;

this.Schedule.BlackoutDates = GetBlackoutDates();

private ObservableCollection<DateTime> GetBlackoutDates()
        {
            var blackoutDateCollection = new ObservableCollection<DateTime>()
            {
                DateTime.Now.Date.AddDays(1),
                DateTime.Now.Date.AddDays(3),
                DateTime.Now.Date.AddDays(5),
                DateTime.Now.Date.AddDays(7),
                DateTime.Now.Date.AddDays(9)
            };
            return blackoutDateCollection;
        }
{% endhighlight %}
{% endtabs %}

## View header
You can customize the default appearance of view header in `TimelineMonth` view by setting [ViewHeaderDateFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.TimeSlotViewSettings.html#Syncfusion_UI_Xaml_Scheduler_TimeSlotViewSettings_ViewHeaderDateFormat), [ViewHeaderHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewSettingsBase.html#Syncfusion_UI_Xaml_Scheduler_ViewSettingsBase_ViewHeaderHeight), [ViewHeaderDayFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewSettingsBase.html#Syncfusion_UI_Xaml_Scheduler_ViewSettingsBase_ViewHeaderDayFormat) and  [ViewHeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewSettingsBase.html#Syncfusion_UI_Xaml_Scheduler_ViewSettingsBase_ViewHeaderTemplate) properties of `TimelineViewSettings`.

### View header text formatting
You can customize the date format of ViewHeader by using the `ViewHeaderDateFormat` property of `TimelineViewSettings`.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler" ViewType="TimelineMonth">
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings      ViewHeaderDateFormat="dd/dddd"/>
    </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}TimelineMonth
{% highlight c# %}
Scheduler.ViewType = SchedulerViewType.TimelineMonth;
Scheduler.TimelineViewSettings.ViewHeaderDateFormat="dd/dddd";
{% endhighlight %}
{% endtabs %}

### View header height
You can customize the height of the ViewHeader in `TimelineMonth` view by setting `ViewHeaderHeight` property of `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler" ViewType="TimelineMonth">
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings
            ViewHeaderHeight="100"/>
        </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
Scheduler.ViewType = SchedulerViewType.TimelineMonth;
Scheduler.TimelineViewSettings.ViewHeaderHeight = 100;
{% endhighlight %}
{% endtabs %}

### View header appearance customization
You can customize the default appearance of view header by setting `ViewHeaderTemplate` property of `TimelineViewSettings` in `SfScheduler`.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <DataTemplate x:Key="viewHeaderTemplate">
        <StackPanel Background="Green" Width="2000">
            <TextBlock 
                HorizontalAlignment="Left" 
                VerticalAlignment="Center"
                Foreground="#FFFFFF"
                FontFamily="Arial"
                Text="{Binding DateText}"
                FontSize="25"
                TextTrimming="CharacterEllipsis" />
        </StackPanel>
    </DataTemplate>
</Window.Resources>
{% endhighlight %}
{% endtabs %}
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler" ViewType="TimelineMonth">
    <syncfusion:SfScheduler.TimelineViewSettings>
        <syncfusion:TimelineViewSettings 
            ViewHeaderTemplate="{StaticResource viewHeaderTemplate}" />
        </syncfusion:SfScheduler.TimelineViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}