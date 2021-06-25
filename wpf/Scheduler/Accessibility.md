---
layout: post
title: Accessibility in WPF SfScheduler control | Syncfusion
description: Learn here about Accessibility support with the Syncfusion WPF Scheduler (SfScheduler) control, its elements and more.
platform: WPF
control: SfScheduler
documentation: ug
---

#  Accessibility Support in WPF Scheduler (SfScheduler)

## Screen reader support

The SfScheduler can easily be accessed by screen readers. Please find the following table to get spoken feedback about the inner element contents of the screen.

### Month view

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Month cell<br/><br/></td><td>dddd, MMMM d, yyyy<br/><br/></td>
<td>Sunday, May 30, 2021<br/><br></td></tr>
<tr>
<td>
ViewHeader<br/><br/></td><td>dddd<br/><br/></td>
<td>Sunday<br/><br></td></tr>
<tr>
<td>
Appointment (allday)<br/><br/></td><td>Subject Allday <br/><br/></td>
<td>Meeting All day <br/><br></td></tr>
<tr>
<td>
Appointment<br/><br/></td><td>Subject h:mm t - h:mm tt  dddd, MMMM d, yyyy <br/><br/></td>
<td>General Meeting 10:00 AM-11:00 AM Tuesday, June 8, 2021<br/><br></td></tr>
<tr>
<td>
Spanning Appointment<br/><br/></td><td>Subject dddd, MMMM d, yyyy h:mm:ss tt - dddd, MMMM d, yyyy h:mm:ss tt <br/><br/></td>
<td>Plan Execution Friday, May 28, 2021 10:00:00 AM-Sunday, May 30, 2021 11:00:00 AM<br/><br></td></tr>
<tr>
<td>
Week number<br/><br/></td><td>WeekNumber weeknumber <br/><br/></td>
<td>Week Number 22<br/><br></td></tr>
<tr>
<td>
Month agenda view  with No date selected<br/><br/></td><td>NoEventTextBlock.Text <br/><br/></td>
<td>No Date Selected<br/><br></td></tr>
<tr>
<td>
Month Agenda view with No events<br/><br/></td><td>dddd, MMMM d, yyyy NoEventTextBlock.Text<br/><br/></td>
<td>Wednesday, June 2, 2021 No Events<br/><br></td></tr>
<tr>
<td>
Month Agenda view list appointment<br/><br/></td><td>dddd, dddd, MMMM d, yyyy<br/><br/></td>
<td>Thursday, June 24, 2021<br/><br></td></tr>
<tr>
<td>
BlackoutDates <br/><br/></td><td>BlackoutDay.Text - dddd, MMMM d, yyyy<br/><br/></td>
<td>Blackout Day-Saturday, June 26, 2021<br/><br></td></tr>
</table>

### Day, week and workweek views

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Timeslot cell<br/><br/></td><td>dddd, MMMM d, yyyy h:mm:ss tt<br/><br/></td>
<td>Sunday, June 20, 2021 12:00:00 AM<br/><br></td></tr>
<tr>
<td>
ViewHeader<br/><br/></td><td>dddd, MMMM d, yyyy<br/><br/></td>
<td>Sunday, June 20, 2021<br/><br></td></tr>
<tr>
<td>
Appointment (allday)<br/><br/></td><td>Subject Allday <br/><br/></td>
<td>Meeting All day <br/><br></td></tr>
<tr>
<td>
Appointment<br/><br/></td><td>Subject h:mm t - h:mm tt  dddd, MMMM d, yyyy <br/><br/></td>
<td>General Meeting 10:00 AM-11:00 AM Tuesday, June 8, 2021<br/><br></td></tr>
<tr>
<td>
Spanning Appointment<br/><br/></td><td>Subject dddd, MMMM d, yyyy h:mm:ss tt - dddd, MMMM d, yyyy h:mm:ss tt <br/><br/></td>
<td>Plan Execution Friday, May 28, 2021 10:00:00 AM-Sunday, May 30, 2021 11:00:00 AM<br/><br></td></tr>
<tr>
<td>
Time ruler<br/><br/></td><td>TimeRuler.Content <br/><br/></td>
<td>12 AM<br/><br></td></tr>
</table>

### Timeline views

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Timeslot cell<br/><br/></td><td>dddd, MMMM d, yyyy h:mm:ss tt<br/><br/></td>
<td>Sunday, June 20, 2021 12:00:00 AM<br/><br></td></tr>
<tr>
<td>
ViewHeader<br/><br/></td><td>dddd, MMMM d, yyyy<br/><br/></td>
<td>Sunday, June 20, 2021<br/><br></td></tr>
<tr>
<td>
Appointment (allday)<br/><br/></td><td>Subject Allday <br/><br/></td>
<td>Meeting All day <br/><br></td></tr>
<tr>
<td>
Appointment<br/><br/></td><td>Subject h:mm t - h:mm tt  dddd, MMMM d, yyyy <br/><br/></td>
<td>General Meeting 10:00 AM-11:00 AM Tuesday, June 8, 2021<br/><br></td></tr>
<tr>
<td>
Spanning Appointment<br/><br/></td><td>Subject dddd, MMMM d, yyyy h:mm:ss tt - dddd, MMMM d, yyyy h:mm:ss tt <br/><br/></td>
<td>Plan Execution Friday, May 28, 2021 10:00:00 AM-Sunday, May 30, 2021 11:00:00 AM<br/><br></td></tr>
<tr>
<td>
Time ruler<br/><br/></td><td>TimeRuler.Content <br/><br/></td>
<td>12 AM<br/><br></td></tr>
</table>

### Scheduler and resource header

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Day, Week, Work week, Month, Timeline day and Timeline month<br/><br/></td><td>MMMM yyyy<br/><br/></td>
<td>June 2021<br/><br></td></tr>
<tr>
<td>
Timeline week and Timeline work week<br/><br/></td><td>MMMM yyyy - MMMM yyyy<br/><br/></td>
<td>28 June - 2 July 2021<br/><br></td></tr>
<tr>
<td>
Resource header<br/><br/></td><td>Name Id <br/><br/></td>
<td>Sophia 1000<br/><br></td></tr>
</table>

### Appointment editor window

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Add appointment <br/><br/></td><td>Title<br/><br/></td>
<td>New event <br/><br></td></tr>
<tr>
<td>
Edit appointment <br/><br/></td><td>Title<br/><br/></td>
<td>Edit event  <br/><br></td></tr>
<tr>
<td>
Title textbox<br/><br/></td><td>Title Edit Text Enter line<br/><br/></td>
<td>Title Edit Meeting Enter line<br/><br></td></tr>
<tr>
<td>
Location textbox<br/><br/></td><td>Title Edit Text  Enter line<br/><br/></td>
<td>Location Edit Chennai Enter line<br/><br></td></tr>
<tr>
<td>
Notes textbox<br/><br/></td><td>Title Edit Text Enter line<br/><br/></td>
<td>Notes Edit (description) Enter line<br/><br></td></tr>
<tr>
<td>
Save button<br/><br/></td><td>content button<br/><br/></td>
<td>Save button<br/><br></td></tr>
<tr>
<td>
Cancel button<br/><br/></td><td>content button<br/><br/></td>
<td>Cancel button<br/><br></td></tr>
<tr>
<td>
Delete button<br/><br/></td><td>content button<br/><br/></td>
<td>Delete button<br/><br></td></tr>
<tr>
<td>
Timezone/Allday check box<br/><br/></td><td>content checkbox<br/><br/></td>
<td>All day checkbox checked/Unchecked<br/><br></td></tr>
<tr>
<td>
Date/time picker<br/><br/></td><td>value edit<br/><br/></td>
<td>12/1/2021 edit <br/><br></td></tr>
<tr>
<td>
Combo box<br/><br/></td><td>content combobox<br/><br/></td>
<td>Custom<br/><br></td></tr>
</table>

### Recurrence editing  window

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Editing or Deleting an recurrence appointment <br/><br/></td><td>Title<br/><br/></td>
<td>Open Recurring Item / Confirm Delete <br/><br></td></tr>
<tr>
<td>
Radio button <br/><br/></td><td>Content ControlType<br/><br/></td>
<td>Just this one RadioButton / Delete this occurrence <br/><br></td></tr>
<tr>
<td>
Button <br/><br/></td><td>Content ControlType<br/><br/></td>
<td>Ok button / Cancel button <br/><br></td></tr>
</table>

### Reminder window

<table>
<tr>
<td>
<b> View </b> <br/><br/></td><td>
<b> Accessibility Format </b> <br/><br/></td>
<td> <b> Example </b><br/><br/></td></tr>
<tr>
<td>
Reminder window <br/><br/></td><td>Title<br/><br/></td>
<td>4 reminders<br/><br></td></tr>
<tr>
<td>
Dismiss all button<br/><br/></td><td>content button<br/><br></td>
<td>Dismiss all button <br/><br></td></tr>
<tr>
<td>
Snooze button <br/><br/></td><td>content button<br/><br></td>
<td>Snooze button  <br/><br></td></tr>
<tr>
<td>
Dismiss button <br/><br/></td><td>content button<br/><br></td>
<td>Dismiss button  <br/><br></td></tr>
<tr>
<td>
Reminder appointments selected <br/><br/></td><td>subject Selected appointment index out of over all index.<br/><br></td>
<td>Conference 1 of 4<br/><br></td></tr>
</table>

## Keyboard navigation

The `SfScheduler` supports selection using keyboard interactions.

### Day, Week and WorkWeek views

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Right arrow<br/><br/></td><td>Moves selection to the same time slot on the next day.<br/><br/></td></tr>
<tr>
<td>
Left arrow<br/><br/></td><td>
Moves selection to the same time slot on the previous day.<br/><br/></td></tr>
<tr>
<td>
Down arrow<br/><br/></td><td>
Moves selection to the next time slot directly below the currently selected time slot.<br/><br/></td></tr>
<tr>
<td>
Up arrow<br/><br/></td><td>
Moves selection to the previous time slot directly above the currently selected time slot.<br/><br/></td></tr>
</table>

### Timeline views

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Right arrow<br/><br/></td><td>Moves selection to the next time slot of the currently selected time slot.<br/><br/></td></tr>
<tr>
<td>
Left arrow<br/><br/></td><td>
Moves selection to the previous time slot of the currently selected time slot.<br/><br/></td></tr>
</table>

### Month view

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Right arrow<br/><br/></td><td>Moves selection to the next date of the currently selected date.<br/><br/></td></tr>
<tr>
<td>
Left arrow<br/><br/></td><td>
Moves selection to the previous date of the currently selected date.<br/><br/></td></tr>
<tr>
<td>
Down arrow<br/><br/></td><td>
Moves selection to the date directly below the currently selected date on the next row.<br/><br/></td></tr>
<tr>
<td>
Up arrow<br/><br/></td><td>
Moves selection to the date directly above the currently selected date on the previous row.<br/><br/></td></tr>
</table>

### Appointments

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Tab<br/><br/></td><td>Moves selection to the next appointment of the currently selected appointment.<br/><br/></td></tr>
<tr>
<td>
Shift + Tab<br/><br/></td><td>
Moves selection to the previous appointment of the currently selected appointment.<br/><br/></td></tr>
<tr>
<td>
Delete<br/><br/></td><td>Deletes the selected appointment from appointments collection.<br/><br/></td></tr>
</table>

### View navigations

<table>
<tr>
<td>
Ctrl + Alt + 1 => DayView<br/><br/></td><td>
Moves the view to day view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 2 => WeekView<br/><br/></td><td>
Moves the view to week view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 3 => WorkWeekView<br/><br/></td><td>
Moves the view to work week view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 4 => MonthView<br/><br/></td><td>
Moves the view to work week view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 5 => TimelineDayView<br/><br/></td><td>
Moves the view to Timeline day view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 6 => TimelineWeekView<br/><br/></td><td>
Moves the view to Timeline week view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 7 => TimelineWorkWeekView<br/><br/></td><td>
Moves the view to Timeline work week view.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Alt + 8 => TimelineMonthView<br/><br/></td><td>
Moves the view to Timeline month view.<br/><br/></td></tr>
</table>