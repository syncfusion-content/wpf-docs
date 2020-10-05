---
layout: post
title: Events in WPF SfScheduler control | Syncfusion
description: This section explain about Events in the Syncfusion WPF Scheduler (SfScheduler) control and more details. 
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

    3. The appointment details get for month view if [AppointmentDisplaymode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.MonthViewSettings.html#Syncfusion_UI_Xaml_Scheduler_MonthViewSettings_AppointmentDisplayMode) as [Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Appointment),or else it will be null for month view.
* [Appointments](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_Appointments)- returns Tapped Month cell appointments values if AppointmentDisplayMode as indicator. Tapped Month Cell has a Recurrence appointment it will return the parent recurrence appointment values. It will be null for Day or Week or WorkWeek views.
* [IsMoreAppointments](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_IsMoreAppointments)- specifies whether more appointments are tapped or not in month view.It will be applicable only for Month view has  AppointmentDisplaymode as Appointment.
* [CancelNavigation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_CancelNavigation)- specifies whether day view navigation should be disabled when clicking more appointments in month view. It will be applicable for month view has AppointmentDisplaymode as Appointment. and click the More appointments in month cell.
* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_DateTime)- gets the date-time of the tapped cell.
* [TimeInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_CellTappedEventArgs_TimeInterval)- gets the date-time interval of the tapped cell. It is not applicable for month view.
* `Resource` - gets the resource associated with the timeslot cell where user tapped.

## CellDoubleTapped

The [CellDoubleTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user double clicks the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) as objects.The base class of the [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

## CellLongPressed

The [CellLongPressed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user long presses the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellLongPressedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) as objects.The base class of the [CellLongPressedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

## SelectionChanged

The [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs after the selection is changed in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) as objects.

The [SelectionChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangedEventArgs_OldValue) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangedEventArgs_NewValue)- gets a new selected date.

## SelectionChanging 

The [SelectionChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the selection gets changing in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) as objects.

The [SelectionChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangingEventArgs_OldValue) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_SelectionChangingEventArgs_NewValue)- gets a new selected date.

## ViewHeaderCellTapped

The [ViewHeaderCellTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the view header in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) as objects.

The [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_ViewHeaderCellTappedEventArgs_DateTime) - gets the corresponding date time.
* `Resource` - gets the resource when tapped on view header in day, week, work week and timeline views.

## HeaderTapped

The [HeaderTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the Scheduler header. This event receives two arguments namely `this` that handles `SfScheduler` and [HeaderTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) as objects.

The [HeaderTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_HeaderTappedEventArgs_DateTime) - gets the corresponding date time.

## WeekNumberTapped

The [WeekNumberTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when the user clicks or touches the week number in month view. This event receives two arguments namely `this` that handles `SfScheduler` and [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) as objects.

The [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) object contains the following properties:

* [Month](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_Month)- gets the corresponding month.
* [WeekNumber](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_WeekNumber)- gets the corresponding week number.
* [Year](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html#Syncfusion_UI_Xaml_Scheduler_WeekNumberTappedEventArgs_Year)- gets the corresponding year.

## AppointmentTapped

The [AppointmentTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) event occurs when schedule appointments get tapped in all views. This event receives two arguments namely `this` that handles `SfScheduler` and [AppointmentTappedArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) as objects.

The [AppointmentTappedArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) object contains the following properties:

* [Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentTappedArgs_Appointment)- gets the custom appointment details
* [SelectedDate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentTappedArgs_SelectedDate)- gets the SelectedDate details
* `Resource` - gets the resource details under which the appointment is located.