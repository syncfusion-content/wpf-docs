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

The [CellTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~CellTapped_EV.html) event occurs when the user clicks or touches the cell in Scheduler.
This event receives two arguments namely `this` that handles `SfScheduler` and [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html) as objects.

The [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html) object contains the following properties:

* [Appointment](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~Appointment.html) - returns Tapped appointment values. The tapped appointment is a Recurrence appointment it will return the parent recurrence appointment values. The appointment data get for month view if AppointmentDisplaymode as Appointment,or else it will be null for month view.It used to get the custom appointment details.
* [Appointments](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~Appointments.html)- returns Tapped Month cell appointments values. Tapped Month Cell has a Recurrence appointment it will return the parent recurrence appointment values. It will be null for Day or Week or WorkWeek views.
* [IsMoreAppointments](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~IsMoreAppointments.html)- specifies whether more appointments are tapped or not in month view. It will be applicable for month view cell tapped when appointments are displayed in the month cell.It will be applicable for month view cell tapped when appointments are displayed in the month cell.It will be applicable for month view when set AppointmentDisplaymode as Appointment.
* [CancelNavigation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~CancelNavigation.html)- specifies whether day view navigation should be disabled when clicking more appointments in month view. It will be applicable for month view cell tapped when appointments are displayed in the month cell.It will be applicable for month view cell tapped when appointments are displayed in the month cell.It will be applicable for month view when set AppointmentDisplaymode as Appointment.
* [DateTime](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~DateTime.html)- gets the date-time of the tapped cell.
* [TimeInterval](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs~TimeInterval.html)- gets the date-time interval of the tapped cell. It is not applicable for month view.

## CellDoubleTapped

The [CellDoubleTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~CellDoubleTapped_EV.html) event occurs when the user double clicks the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) as objects.The base class of the [CellDoubleTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellDoubleTappedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

## CellLongPressed

The [CellLongPressed](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~CellLongPressed_EV.html) event occurs when the user long presses the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [CellLongPressedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) as objects.The base class of the [CellLongPressedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellLongPressedEventArgs.html) is [CellTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.CellTappedEventArgs.html)

## SelectionChanged

The [SelectionChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~SelectionChanged_EV.html) event occurs after the selection is changed in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) as objects.

The [SelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs~OldValue.html) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangedEventArgs~NewValue.html)- gets a new selected date.

## SelectionChanging 

The [SelectionChanging](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~SelectionChanging_EV.html) event occurs when the selection gets changing in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [SelectionChangingEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) as objects.

The [SelectionChanging](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs.html) object contains the following properties:

* [OldValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs~OldValue.html) - gets an old selected date.
* [NewValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SelectionChangingEventArgs~NewValue.html)- gets a new selected date.

## ViewHeaderCellTapped

The [ViewHeaderCellTapped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~ViewHeaderCellTapped_EV.html) event occurs when the user clicks or touches the view header in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) as objects.

The [ViewHeaderCellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.ViewHeaderCellTappedEventArgs~DateTime.html) - gets the corresponding date time.

## HeaderTapped

The [HeaderTapped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~HeaderTapped_EV.html) event occurs when the user clicks or touches the Scheduler header. This event receives two arguments namely `this` that handles `SfScheduler` and [HeaderTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) as objects.

The [HeaderTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs.html) object contains the following properties:

* [DateTime](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.HeaderTappedEventArgs~DateTime.html) - gets the corresponding date time.

## WeekNumberTapped

The [WeekNumberTapped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~WeekNumberTapped_EV.html) event occurs when the user clicks or touches the week number in month view. This event receives two arguments namely `this` that handles `SfScheduler` and [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) as objects.

The [WeekNumberTappedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs.html) object contains the following properties:

* [Month](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs~Month.html)- gets the corresponding month.
* [WeekNumber](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs~WeekNumber.html)- gets the corresponding year.
* [Year](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.WeekNumberTappedEventArgs~Year.html)- gets the corresponding week number.

## AppointmentTapped

The [AppointmentTapped](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~AppointmentTapped_EV.html) event occurs when schedule appointments get tapped in all views. This event receives two arguments namely `this` that handles `SfScheduler` and [AppointmentTappedArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) as objects.

The [AppointmentTappedArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs.html) object contains the following properties:

* [Appointment](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs~Appointment.html)- gets the custom appointment details
* [SelectedDate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentTappedArgs~SelectedDate.html)- gets the SelectedDate details