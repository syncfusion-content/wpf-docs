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

Both SfSchedule and SfScheduler almost have the same set of features. But the SfScheduler control offers a rich set of features over SfSchedule. 

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
</table>

The following table compares the AppointmentMapping APIs,

<table>
<tr>
<th>
SfSchedule</th><th>
SfScheduler</th><th>
Description</th></tr>
<tr>
<td>AppointmentMapping</td>
<td>AppointmentMapping</td>
<td>Gets or sets the mapping to the appointment.</td></tr>
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
