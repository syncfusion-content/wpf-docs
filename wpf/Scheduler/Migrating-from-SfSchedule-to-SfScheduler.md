---
layout: post
title: Migrating from SfSchedule to SfScheduler|SfScheduler| Wpf| Syncfusion
description: This section explains how to migrating from  WPF SfSchedule to SfScheduler control and the rich set of features of SfScheduler control.
platform: wpf
control: SfScheduler
documentation: ug
---

# Migrating from SfSchedule to SfScheduler

SfScheduler is a new Scheduler control introduced in 18.1 Version. The SfScheduler control is used to schedule and manage appointments through an intuitive user interface, similar to the Outlook calendar. This section helps you to identify equivalent SfSchedule features or APIs in SfScheduler.

## Adding Reference

SfSchedule Assembly Name: Syncfusion.SfSchedule.WPF
SfSchedule Namespace Name: Syncfusion.UI.Xaml.Schedule

SfScheduler Assembly Name: Syncfusion.SfScheduler.WPF
SfScheduler Namespace Name: Syncfusion.UI.Xaml.Scheduler


The following code example shows xmlns namespace for SfScheduler control. You can include the Syncfusion schema in WPF and both the charts are available in the WPF schema.

### SfSchedule

{% highlight xaml %}
xmlns:schedule="http://schemas.syncfusion.com/wpf"
{% endhighlight %}

### SfScheduler

{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

  (or)

xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Scheduler;assembly=Syncfusion.SfScheduler.WPF"

{% endhighlight %}

## Initialization

Both [SfSchedule](https://help.syncfusion.com/wpf/schedule/overview) and [SfScheduler](https://help.syncfusion.com/wpf/scheduler/overview) almost have the same set of features. But the SfScheduler control offers a rich set of features over SfSchedule. 

## Major improvements of SfScheduler

* Improved the scheduler control rendering performance.
* Improved the performance on switching the views such as day, week, work week, month, and timeline views.
* Performance has been improved while loading more events or appointments.
* Schedule view or date swiping and scrolling interaction improved.
* Schedule elements easily customized using the Style and Template according to the WPF standard such as events or appointments, month cell.
* Support Recurrence pattern exception dates and exception appointments.
* Support special time region for Timeslot views.

N>  In the future, new features & enhancements will be added only in `SfScheduler`. It recommended using the  ` SfScheduler`.

The following table shows the API comparison between SfSchedule and SfScheduler.

<table>
<tr>
<th>
SfSchedule</th><th>
SfScheduler</th><th>
Description</th></tr>
<tr>
<td>ScheduleViewType</td>
<td>ViewType</td>
<td>Gets or sets a value which determines Scheduler ViewType.</td></tr>
<tr>
<td>FirstDayOfWeek</td>
<td>FirstDayOfWeek</td>
<td>Gets or sets the day of the week in Schedule.</td></tr>
<tr>
<td>NonWorkingDays</td>
<td>NonWorkingDays </td>
<td>Gets or sets the non working days.</td></tr>
<tr>
<td>Appointments,ItemsSource</td>
<td>ItemsSource</td>
<td>Gets or sets a items source to the scheduler.</td></tr>
<tr>
<td>AppointmentMapping</td>
<td>AppointmentMapping</td>
<td>Gets or sets the mapping to the appointment.</td></tr>
<tr>
<td>AppointmentMapping</td>
<td>AppointmentMapping</td>
<td>Gets or sets the mapping to the appointment.</td></tr>
</table>

The following table compares the `ScheduleAppointment` APIs,

<table>
<tr>
<th>
SfSchedule(ScheduleAppointment)</th><th>
SfScheduler(ScheduleAppointment)</th><th>
Description</th></tr>
<tr>
<td>Subject</td>
<td>Subject</td>
<td>Gets or sets the subject for the appointment.</td></tr>
<tr>
<td>Notes</td>
<td>Notes</td>
<td>Gets or sets the notes for an appointment.</td></tr>
<tr>
<td>Location</td>
<td>Location</td>
<td>Gets or sets the location for an appointment.</td></tr>
<tr>
<td>AppointmentBackground</td>
<td>AppointmentBackground</td>
<td>Gets or sets the appointment color.</td></tr>
<tr>
<td>StartTime</td>
<td>StartTime</td>
<td>Gets or sets the start date and time of the appointment.</td></tr>
<tr>
<td>EndTime</td>
<td>EndTime</td>
<td>Gets or sets the end date and time of the appointment.</td></tr>
<tr>
<td>-</td>
<td>ActualStartTime</td>
<td>Gets the internal start time which is converted based on start time zone applied.</td></tr>
<tr>
<td>-</td>
<td>ActualEndTime</td>
<td>Gets the internal end time which is converted based on start time zone applied.</td></tr>
<tr>
<td>StartTimeZone</td>
<td>StartTimeZone</td>
<td>Gets or sets time zone for the start time of the appointment.</td></tr>
<tr>
<td>EndTimeZone</td>
<td>EndTimeZone</td>
<td>Gets or sets time zone for the end time of the appointment.</td></tr>
<tr>
<td>IsRecursive</td>
<td>IsRecursive</td>
<td>Gets a value indicating whether the appointment is recurrence appointment or not.</td></tr>
<tr>
<td>AllDay</td>
<td>IsAllDay</td>
<td>Gets or sets a value indicating whether the appointment's duration is equal one day or not.</td></tr>
<tr>
<td>RecurrenceRule</td>
<td>RecurrenceRule</td>
<td> Gets or sets a value indicating whether the appointment should be recursive.</td></tr>
<tr>
<td>RecursiveExceptionDates</td>
<td>RecurrenceExceptionDates</td>
<td>Gets or sets the properties for maintaining recurrence rule exception Dates.</td></tr>
<tr>
<td>-</td>
<td>RecurrenceId</td>
<td>Gets or sets an unique ID for referring recurrence appointment.</td></tr>
<tr>
<td>-</td>
<td>Data</td>
<td>Gets the data object associated with appointment.</td></tr>
<tr>
<td>-</td>
<td>Type</td>
<td>Gets the type of appointment.</td></tr>
</table>

The following table compares the `AppointmentMapping` APIs,

<table>
<tr>
<th>
SfSchedule(AppointmentMapping)</th><th>
SfScheduler(AppointmentMapping)</th><th>
Description</th></tr>
<tr>
<td>SubjectMapping</td>
<td>Subject</td>
<td>Gets or sets the Subject property for mapping to the schedule appointment.</td></tr>
<tr>
<td>NotesMapping</td>
<td>Notes</td>
<td>Gets or sets the Notes property for mapping to the schedule appointment.</td></tr>
<tr>
<td>LocationMapping</td>
<td>Location</td>
<td>Gets or sets the Location property for mapping to the schedule appointment.</td></tr>
<tr>
<td>AppointmentBackgroundMapping</td>
<td>AppointmentBackground</td>
<td>Gets or sets the AppointmentBackground property for mapping to the schedule appointment.</td></tr>
<tr>
<td>StartTimeMapping</td>
<td>StartTime</td>
<td>Gets or sets the StartTime property for mapping to the schedule appointment.</td></tr>
<tr>
<td>EndTimeMapping</td>
<td>EndTime</td>
<td>Gets or sets the EndTime property for mapping to the schedule appointment.</td></tr>
<tr>
<td>StartTimeZoneMapping</td>
<td>StartTimeZone</td>
<td>Gets or sets the StartTimeZone property for mapping to the schedule appointment.</td></tr>
<tr>
<td>EndTimeZoneMapping</td>
<td>EndTimeZone</td>
<td>Gets or sets the EndTimeZone property for mapping to the schedule appointment.</td></tr>
<tr>
<td>AllDayMapping</td>
<td>IsAllDay</td>
<td>Gets or sets the IsAllDay property for mapping to the schedule appointment.</td></tr>
<tr>
<td>RecurrenceRuleMapping</td>
<td>RecurrenceRule</td>
<td> Gets or sets the RecurrenceRule property for mapping to the schedule appointment.</td></tr>
<tr>
<td>RecursiveExceptionDatesMapping</td>
<td>RecurrenceExceptionDates</td>
<td> Gets or sets the RecurrenceExceptionDates property for mapping to the schedule appointment.</td></tr>
<tr>
<td>-</td>
<td>RecurrenceId</td>
<td>Gets or sets the RecurrenceId property for mapping to the schedule appointment.</td></tr>
</table>

You can see the list of the rich set of features in `SfScheduler` over `SfSchedule` as follows:

Rich set of features in `SfScheduler` over `SfSchedule`.

<table>
<tr>
<th>Feature</th>
<th>Description</th>
</tr>
<tr>
<td>Events</td>
<td>
Appointments contain information on events scheduled at specific times. In addition to default appointments, the users can use their own collections to connect a business entity to an appointment by mapping their fields, such as start time, end time, subject, notes, and recurrence.
</td>
</tr>
<tr>
<td>
 Data Binding
</td>
<td>
The scheduler control supports to bind any collection that implements the IEnumerable interface to populate appointments.
</td>
</tr>
<tr>
<td>
Recurring Events
</td>
<td>
Easily configure recurring events on a daily, weekly, monthly, or yearly basis. You can also skip or change the occurrence of a recurring appointment.
</td>
</tr>
</table>
