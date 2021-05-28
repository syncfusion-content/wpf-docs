---
layout: post
title: Event in WPF SfSchedule Control | Syncfusion
description: Learn here all about Event support in Syncfusion WPF Schedule (Classic) control, its elements and more details.
platform: wpf
control: SfSchedule
 documentation: ug
---

# Event in WPF Schedule (Classic)

Event can be used for various operation such as Appointment Editor Opening and Closed or while opening or closing the Context Menu and events ItemsSourceChanged, ScheduleTapped, ScheduleDoubleTapped are used for customization purposes.



* AppointmentEditorOpening - occurs when the appointment editor is opening. The AppointmentEditorOpening event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* An AppointmentEditorOpeningEventArgs is a class. Via the AppointmentEditorOpeningEventArgs you can access the following properties:



Appointment - gets the appointment, this argument is of type object.

StartTime - gets the appointment start time.

Action – gets the Editor action such as Add or Edit or Delete.

SelectedResource – gets the list of Resources.

Cancel- set this Boolean property to True to canceling the event.

* AppointmentEditorClosed- occurs when the appointment editor is closed. The AppointmentEditorClosed event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* An AppointmentEditorClosedEventArgs a class. Via the AppointmentEditorClosedEventArgs you can access the following properties:

OriginalAppointment - gets the Original appointment, this argument is of type object.

EditedAppointment - gets the edited appointment, this argument is of type object.

IsNew – set this Boolean property to True, when you Updating or Setting new appointment property.

Action – gets the Editor action such as Add or Edit or Delete.

* AppointmentCollectionChanged - occurs when the appointment collection changed. The AppointmentCollectionChanged event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* Via the NotifyCollectionChangedEventArgs gets the collection are affected by the change.



* ContextMenuOpening- occurs when opening Context Menu. The ContextMenuOpening event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* A ContextMenuOpeningEventArgs is a class. Via the ContextMenuOpeningEventArgs you can access the following properties:

Appointment - gets the appointment, this argument is of type object.

CurrentSelectedDate - gets the appointment current selected Date.

CurrentEventArgs – gets the Editor action such as Add or Edit or Delete.

SelectedResource – gets the list of Resources.

Cancel- set this Boolean property to True to disable the context menu.

* ContextMenuClosed- occurs when the Context Menu closed. The ContextMenuClosedEvent handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* A ContextMenuClosedEventArgs is a class. 



* ItemsSourceChanged- occurs when item source changed. The ItemsSourceChanged event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* Via the PropertyChangedEventArgs gets the name of the property that changed.



* ScheduleClick- occurs when tapping the schedule. The ScheduleClickEvent handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* ScheduleClickEventArgs is a class. Via the ScheduleClickEventArgs you can access the following properties:

Appointment - gets the appointment, this argument is of type object.

SelectedDate - gets the appointment current selected Date.

SelectedResource – gets the list of Resources.

* ScheduleDoubleClick- occurs when double tapping the schedule. The ScheduleDoubleClick event handler receives two arguments:
* The sender argument contains the SfSchedule. This argument is of type object, but can be cast to the SfSchedule type.
* ScheduleClickEventArgs is a class. Via the ScheduleClickEventArgs you can access the following properties:

Appointment - gets the appointment, this argument is of type object.

SelectedDate - gets the appointment current selected Date.

SelectedResource – gets the list of Resources.



