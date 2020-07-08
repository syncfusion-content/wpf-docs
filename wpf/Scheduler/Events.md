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

The `CellTapped` event occurs when the user clicks or touches the cell in Scheduler.
This event receives two arguments namely `this` that handles `SfScheduler` and `CellTappedEventArgs` as objects.

The `CellTappedEventArgs` object contains the following properties:

* `Appointment` - returns Tapped appointment values. The tapped appointment is a Recurrence appointment it will return the parent recurrence appointment values. It will be null for month view.
* `Appointments`- returns Tapped Month cell appointments values. Tapped Month Cell has a Recurrence appointment it will return the parent recurrence appointment values. It will be null for Day or Week or WorkWeek views.
* `IsMoreAppointments`- specifies whether more appointments are tapped or not in month view. It will be applicable for month view cell tapped when appointments are displayed in the month cell.
* `CancelNavigation`- specifies whether day view navigation should be disabled when clicking more appointments in month view. It will be applicable for month view cell tapped when appointments are displayed in the month cell.
* `DateTime`- gets the date-time of the tapped cell.
* `TimeInterval`- gets the date-time interval of the tapped cell. It is not applicable for month view.

## CellDoubleTapped

The `CellDoubleTapped` event occurs when the user double clicks the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and `CellDoubleTappedEventArgs` as objects.

## CellLongPressed

The `CellLongPressed` event occurs when the user long presses the cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and `CellLongPressedEventArgs` as objects.

## SelectionChanged

The `SelectionChanged` event occurs after the selection is changed in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and `SelectionChangedEventArgs` as objects.

The `SelectionChangedEventArgs` object contains the following properties:

* `OldValue` - gets an old selected date.
* `NewValue`- gets a new selected date.

## SelectionChanging 

The `SelectionChanging` event occurs when the selection gets changing in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and `SelectionChangingEventArgs` as objects.

The `SelectionChanging` object contains the following properties:

* `OldValue` - gets an old selected date.
* `NewValue`- gets a new selected date.

## ViewHeaderCellTapped

The `ViewHeaderCellTapped` event occurs when the user clicks or touches the view header cell in Scheduler. This event receives two arguments namely `this` that handles `SfScheduler` and `ViewHeaderCellTappedEventArgs` as objects.

The `ViewHeaderCellTappedEventArgs` object contains the following properties:

* `DateTime` - gets the corresponding date time.

## HeaderTapped

The `HeaderTapped` event occurs when the user clicks or touches the Scheduler header. This event receives two arguments namely `this` that handles `SfScheduler` and `HeaderTappedEventArgs` as objects.

The `HeaderTappedEventArgs` object contains the following properties:

* `DateTime` - gets the corresponding date time.

## WeekNumberTapped

The `WeekNumberTapped` event occurs when the user clicks or touches the week number in month view. This event receives two arguments namely `this` that handles `SfScheduler` and `WeekNumberTappedEventArgs` as objects.

The `WeekNumberTappedEventArgs` object contains the following properties:

* `Month`- gets the corresponding month.
* `Year`- gets the corresponding year.
* `WeekNumber`- gets the corresponding week number.

## AppointmentTapped

The `AppointmentTapped` event occurs when schedule appointments get tapped in all views. This event receives two arguments namely `this` that handles `SfScheduler` and `AppointmentTappedArgs` as objects.

The `AppointmentTappedArgs` object contains the following properties:

* `Appointment`
* `SelectedDate`
