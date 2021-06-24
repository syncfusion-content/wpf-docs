---
layout: post
title: Events in WPF Scheduler control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF Scheduler (SfScheduler) control, its elements and more.
platform: wpf
control: SfScheduler
documentation: ug
---

# Events in WPF Scheduler (SfScheduler)

## CellTapped

The [CellTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the cell in Scheduler.
This event receives two arguments namely `this` that handles `SfScheduler` and [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html) as objects.

The [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html) object contains the following properties:

* [Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Appointment) - returns Tapped appointment values.

    1. If [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ItemsSourceProperty) added with custom business object then tapped custom Appointment details can get by using Appointment [Data](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Data) property in Cell tapped arguments. 

    2. The tapped appointment is a Recurrence appointment it will return the parent recurrence appointment values. 

    3. The appointment details get for month view if [AppointmentDisplaymode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.MonthViewSettings.html#Syncfusion_UI_Xaml_Scheduler_MonthViewSettings_AppointmentDisplayMode) as [Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Appointment), or else it will be null for month view.
* [Appointments](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Appointments)- returns Tapped Month cell appointments values if AppointmentDisplayMode as indicator. Tapped Month Cell has a Recurrence appointment it will return the parent recurrence appointment values. It will be null for Day or Week or WorkWeek views.
* [IsMoreAppointments](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_IsMoreAppointments)- specifies whether more appointments are tapped or not in month view. It will be applicable only for Month view which has AppointmentDisplaymode as Appointment.
* [CancelNavigation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_CancelNavigation)- specifies whether day view navigation should be disabled when clicking more appointments in month view. It will be applicable for month view which has AppointmentDisplaymode as Appointment and click the More appointments in month cell.
* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_DateTime)- gets the date-time of the tapped cell.
* [TimeInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_TimeInterval)- gets the date-time interval of the tapped cell. It is not applicable for month view.
* [Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Resource) - gets the resource associated with the timeslot cell where user tapped.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month"
                        CellTapped="Scheduler_CellTapped" >
</syncfusion:SfScheduler>  
{% endhighlight %}
{% highlight c#%}
private void Scheduler_CellTapped(object sender, CellTappedEventArgs e)
{
    var dateTime = e.DateTime.ToString();
}
{% endhighlight %}
{% endtabs %}

## CellDoubleTapped

The [CellDoubleTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user double clicks the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) as objects. The base class of the [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						CellDoubleTapped="Scheduler_CellDoubleTapped">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Scheduler_CellDoubleTapped(object sender, CellDoubleTappedEventArgs e)
{
    var dateTime = e.DateTime.ToString();
}
{% endhighlight %}
{% endtabs %}

## CellLongPressed

The [CellLongPressed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user long presses the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellLongPressedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) as objects. The base class of the [CellLongPressedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						CellLongPressed="Schedule_CellLongPressed">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_CellLongPressed(object sender, CellLongPressedEventArgs e)
{
    var dateTime = e.DateTime.ToString();
}
{% endhighlight %}
{% endtabs %}

## SelectionChanged

The [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs after the selection is changed in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) as objects.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						SelectionChanged="Schedule_SelectionChanged">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    var newdate = e.NewValue.ToString();
    var olddate = e.OldValue.ToString();
}
{% endhighlight %}
{% endtabs %}

The [SelectionChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangedEventArgs_OldValue) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangedEventArgs_NewValue)- gets a new selected date.

## SelectionChanging 

The [SelectionChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the selection gets changing in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) as objects.

The [SelectionChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangingEventArgs_OldValue) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangingEventArgs_NewValue)- gets a new selected date.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						SelectionChanging="Schedule_SelectionChanging">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_SelectionChanging(object sender, SelectionChangingEventArgs e)
{
    var newdate = e.NewValue.ToString();
    var olddate = e.OldValue.ToString();
}
{% endhighlight %}
{% endtabs %}

## ViewHeaderCellTapped

The [ViewHeaderCellTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the view header in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) as objects.

The [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_ViewHeaderCellTappedEventArgs_DateTime) - gets the corresponding date time.
* [Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_ViewHeaderCellTappedEventArgs_Resource) - gets the resource when tapped on view header in day, week, work week and timeline views.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						ViewHeaderCellTapped="Schedule_ViewHeaderCellTapped">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_ViewHeaderCellTapped(object sender, ViewHeaderCellTappedEventArgs e)
{
    var dateTime = e.DateTime.ToString();
}
{% endhighlight %}
{% endtabs %}

## HeaderTapped

The [HeaderTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the Scheduler header. This event receives two arguments namely `this` that handles `SfScheduler` and [HeaderTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) as objects.

The [HeaderTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_HeaderTappedEventArgs_DateTime) - gets the corresponding date time.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						HeaderTapped="Schedule_HeaderTapped">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_HeaderTapped(object sender, HeaderTappedEventArgs e)
{
    var dateTime = e.DateTime.ToString();
}
{% endhighlight %}
{% endtabs %}

## WeekNumberTapped

The [WeekNumberTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the week number in month view. This event receives two arguments namely `this` that handles `SfScheduler` and [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) as objects.

The [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) object contains the following properties:

* [Month](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_Month)- gets the corresponding month.
* [WeekNumber](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_WeekNumber)- gets the corresponding week number.
* [Year](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_Year)- gets the corresponding year.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						WeekNumberTapped="Schedule_WeekNumberTapped">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_WeekNumberTapped(object sender, WeekNumberTappedEventArgs e)
{
    var weeknumber = e.WeekNumber.ToString();
}
{% endhighlight %}
{% endtabs %}

## AppointmentTapped

The [AppointmentTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when schedule appointments get tapped in all views. This event receives two arguments namely `this` that handles `SfScheduler` and [AppointmentTappedArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) as objects.

The [AppointmentTappedArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) object contains the following properties:

* [Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentTappedArgs_Appointment)- gets the custom appointment details
* [SelectedDate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentTappedArgs_SelectedDate)- gets the SelectedDate details
* [Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentTappedArgs_Resource) - gets the resource details under which the appointment is located.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        ViewType="Month" 
						AppointmentTapped="Schedule_AppointmentTapped">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
private void Schedule_AppointmentTapped(object sender, AppointmentTappedArgs e)
{
    var appointment = e.Appointment.ToString();
}
{% endhighlight %}
{% endtabs %}
