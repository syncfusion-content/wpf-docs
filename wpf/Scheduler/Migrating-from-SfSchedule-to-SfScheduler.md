---
layout: post
title: Migrating from classic WPF Schedule to new WPF Scheduler control |Syncfusion | 
description: Learn here all about to migrating from classic WPF Schedule to new WPF Scheduler control and the rich set of features of Scheduler control and more.
platform: wpf
control: SfScheduler
documentation: ug
---

# Migrating from SfSchedule to SfScheduler

SfScheduler is a new Scheduler control introduced in 18.2.0.45 Version. The SfScheduler control is used to schedule and manage appointments through an intuitive user interface, similar to the Outlook calendar. This section helps you to identify equivalent SfSchedule features or APIs in SfScheduler.

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

Both [SfSchedule](https://help.syncfusion.com/wpf/schedule/overview) and [SfScheduler](https://help.syncfusion.com/wpf/scheduler/getting-started) almost have the same set of features. But the SfScheduler control offers a rich set of features over SfSchedule. 

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
<td>{{'[ScheduleType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleType)'| markdownify }}</td>
<td>{{'[ViewType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ViewType)'| markdownify }}</td>
<td>Gets or sets a value which determines Scheduler ViewType.</td></tr>
<tr>
<td>{{'[FirstDayOfWeek](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_FirstDayOfWeek)'| markdownify }}</td>
<td>{{'[FirstDayOfWeek](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_FirstDayOfWeek)'| markdownify }}</td>
<td>Gets or sets the day of the week in Schedule.</td></tr>
<tr>
<td>{{'[NonWorkingDays](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonWorkingDays)'| markdownify }}</td>
<td>{{'[NonWorkingDays](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.TimeSlotViewSettings.html#Syncfusion_UI_Xaml_Scheduler_TimeSlotViewSettings_NonWorkingDays)'| markdownify }}</td>
<td>Gets or sets the non working days.</td></tr>
<tr>
<td>{{'[Appointments](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Appointments)'| markdownify }}, {{'[ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ItemsSource)'| markdownify }}</td>
<td>{{'[ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ItemsSource)'| markdownify }}</td>
<td>Gets or sets a items source to the scheduler.</td></tr>
<tr>
<td>{{'[ScheduleAppointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html)'| markdownify }}</td>
<td>{{'[ScheduleAppointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html)'| markdownify }}</td>
<td>Gets or sets the appointments data in schedule control.</td></tr>
<tr>
<td>{{'[AppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_AppointmentMapping)'| markdownify }}</td>
<td>{{'[AppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_AppointmentMapping)'| markdownify }}</td>
<td>Gets or sets the mapping to the appointment.</td></tr>
<tr>
<td>{{'[Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Resource)'| markdownify }}</td>
<td>{{'[ResourceCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ResourceCollection)'| markdownify }}</td>
<td>Gets or sets the Resource grouping for schedule.</td></tr>
</table>

The following table compares the [ScheduleAppointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html) APIs,

<table>
<tr>
<th>SfSchedule(ScheduleAppointment)</th>
<th>SfScheduler(ScheduleAppointment)</th>
<th>Description</th></tr>
<tr>
<td>{{'[Subject](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_Subject)'| markdownify }}</td>
<td>{{'[Subject](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Subject)'| markdownify }}</td>
<td>Gets or sets the subject for the appointment.</td></tr>
<tr>
<td>{{'[Notes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_Notes)'| markdownify }}</td>
<td>{{'[Notes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Notes)'| markdownify }}</td>
<td>Gets or sets the notes for an appointment.</td></tr>
<tr>
<td>{{'[Location](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_Location)'| markdownify }}</td>
<td>{{'[Location](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Location)'| markdownify }}</td>
<td>Gets or sets the location for an appointment.</td></tr>
<tr>
<td>{{'[AppointmentBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_AppointmentBackground)'| markdownify }}</td>
<td>{{'[AppointmentBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_AppointmentBackground)'| markdownify }}</td>
<td>Gets or sets the appointment color.</td></tr>
<tr>
<td>{{'[StartTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_StartTime)'| markdownify }}</td>
<td>{{'[StartTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_StartTime)'| markdownify }}</td>
<td>Gets or sets the start date and time of the appointment.</td></tr>
<tr>
<td>{{'[EndTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_EndTime)'| markdownify }}</td>
<td>{{'[EndTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_EndTime)'| markdownify }}</td>
<td>Gets or sets the end date and time of the appointment.</td></tr>
<tr>
<td>-</td>
<td>{{'[ActualStartTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_ActualStartTime)'| markdownify }}</td>
<td>Gets the internal start time which is converted based on start time zone applied.</td></tr>
<tr>
<td>-</td>
<td>{{'[ActualEndTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_ActualEndTime)'| markdownify }}</td>
<td>Gets the internal end time which is converted based on start time zone applied.</td></tr>
<tr>
<td>{{'[StartTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_StartTimeZone)'| markdownify }}</td>
<td>{{'[StartTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_StartTimeZone)'| markdownify }}</td>
<td>Gets or sets time zone for the start time of the appointment.</td></tr>
<tr>
<td>{{'[EndTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_EndTimeZone)'| markdownify }}</td>
<td>{{'[EndTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_EndTimeZone)'| markdownify }}</td>
<td>Gets or sets time zone for the end time of the appointment.</td></tr>
<tr>
<td>{{'[IsRecursive](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_IsRecursive)'| markdownify }}</td>
<td>{{'[IsRecursive](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_IsRecursive)'| markdownify }}</td>
<td>Gets a value indicating whether the appointment is recurrence appointment or not.</td></tr>
<tr>
<td>{{'[AllDay](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_AllDay)'| markdownify }}</td>
<td>{{'[IsAllDay](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_IsAllDay)'| markdownify }}</td>
<td>Gets or sets a value indicating whether the appointment's duration is equal one day or not.</td></tr>
<tr>
<td>{{'[RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_RecurrenceRule)'| markdownify }}</td>
<td>{{'[RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_RecurrenceRule)'| markdownify }}</td>
<td> Gets or sets a value indicating whether the appointment should be recursive.</td></tr>
<tr>
<td>{{'[RecursiveExceptionDates](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_RecursiveExceptionDates)'| markdownify }}</td>
<td>{{'[RecurrenceExceptionDates](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_RecurrenceExceptionDates)'| markdownify }}</td>
<td>Gets or sets the properties for maintaining recurrence rule exception Dates.</td></tr>
<tr>
<td>-</td>
<td>{{'[RecurrenceId](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_RecurrenceId)'| markdownify }}</td>
<td>Gets or sets an unique ID for referring recurrence appointment.</td></tr>
<tr>
<td>-</td>
<td>{{'[Data](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Data)'| markdownify }}</td>
<td>Gets the data object associated with appointment.</td></tr>
<tr>
<td>-</td>
<td>{{'[Type](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_Type)'| markdownify }}</td>
<td>Gets the type of appointment.</td></tr>
</table>

The following table compares the [AppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html) APIs,

<table>
<tr>
<th>SfSchedule(AppointmentMapping)</th>
<th>SfScheduler(AppointmentMapping)</th>
<th>Description</th></tr>
<tr>
<td>{{'[SubjectMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_SubjectMappingProperty)'| markdownify }}</td>
<td>{{'[Subject](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_Subject)'| markdownify }}</td>
<td>Gets or sets the Subject property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[NotesMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_NotesMappingProperty)'| markdownify }}</td>
<td>{{'[Notes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_Notes)'| markdownify }}</td>
<td>Gets or sets the Notes property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[LocationMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_LocationMappingProperty)'| markdownify }}</td>
<td>{{'[Location](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_Location)'| markdownify }}</td>
<td>Gets or sets the Location property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[AppointmentBackgroundMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_AppointmentBackgroundMappingProperty)'| markdownify }}</td>
<td>{{'[AppointmentBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_AppointmentBackground)'| markdownify }}</td>
<td>Gets or sets the AppointmentBackground property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[StartTimeMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_StartTimeMappingProperty)'| markdownify }}</td>
<td>{{'[StartTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_StartTime)'| markdownify }}</td>
<td>Gets or sets the StartTime property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[EndTimeMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_EndTimeMappingProperty)'| markdownify }}</td>
<td>{{'[EndTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_EndTime)'| markdownify }}</td>
<td>Gets or sets the EndTime property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[StartTimeZoneMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_StartTimeZoneMappingProperty)'| markdownify }}</td>
<td>{{'[StartTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_StartTimeZone)'| markdownify }}</td>
<td>Gets or sets the StartTimeZone property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[EndTimeZoneMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_EndTimeZoneMappingProperty)'| markdownify }}</td>
<td>{{'[EndTimeZone](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_EndTimeZone)'| markdownify }}</td>
<td>Gets or sets the EndTimeZone property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[AllDayMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_AllDayMappingProperty)'| markdownify }}</td>
<td>{{'[IsAllDay](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_IsAllDay)'| markdownify }}</td>
<td>Gets or sets the IsAllDay property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[RecurrenceRuleMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_RecurrenceRuleMappingProperty)'| markdownify }}</td>
<td>{{'[RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_RecurrenceRule)'| markdownify }}</td>
<td> Gets or sets the RecurrenceRule property for mapping to the schedule appointment.</td></tr>
<tr>
<td>{{'[RecursiveExceptionDatesMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointmentMapping_RecursiveExceptionDatesMappingProperty)'| markdownify }}</td>
<td>{{'[RecurrenceExceptionDates](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_RecurrenceExceptionDates)'| markdownify }}</td>
<td> Gets or sets the RecurrenceExceptionDates property for mapping to the schedule appointment.</td></tr>
<tr>
<td>-</td>
<td>{{'[RecurrenceId](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentMapping.html#Syncfusion_UI_Xaml_Scheduler_AppointmentMapping_RecurrenceId)'| markdownify }}</td>
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
