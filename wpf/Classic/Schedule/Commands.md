---
layout: post
title: Commands in WPF SfSchedule Control | Syncfusion
description: Learn here all about Commands support in Syncfusion WPF Schedule (Classic) control, its elements and more details.
platform: wpf
control: SfSchedule
 documentation: ug
---

# Commands in WPF Schedule (Classic)

Operations that are done by context menu can be performed using Schedule commands. The following actions of context menu can be handled by executing schedule commands in the application.

* Adding new appointment
* Editing appointment
* Deleting appointment
* Copying appointment
* Pasting appointment
* Drag and drop appointment



## AddNewCommand

Using AddNewCommand of ScheduleCommands, a new appointment can be added in SfSchedule.
{% highlight c# %}

ScheduleCommands.AddNewCommand.Execute(this.Schedule);


{% endhighlight  %}


## EditCommand

Using EditCommand of ScheduleCommands, an existing appointment of SfSchedule can be modified.
{% highlight c# %}

ScheduleCommands.EditCommand.Execute(this.Schedule);



{% endhighlight  %}

## DeleteCommand

DeleteCommand can be used to delete an appointment in SfSchedule.
{% highlight c# %}

ScheduleCommands.DeleteCommand.Execute(this.Schedule);


{% endhighlight  %}


## CopyCommand

Using CopyCommand of ScheduleCommands, a schedule appointment can be copied.
{% highlight c# %}

ScheduleCommands.CopyCommand.Execute(this.Schedule);


{% endhighlight  %}


## PasteCommand

Using PasteCommand of ScheduleCommands, a copied schedule appointment can be pasted in SfSchedule.
{% highlight c# %}

ScheduleCommands.PasteCommand.Execute(this.Schedule);



{% endhighlight %}

## DragAndDropCommand

Using DragAndDropCommand of ScheduleCommands, an appointment can be dragged and dropped from one timeslot to another timeslot. Resizing operation can also be performed using this command.
{% highlight c# %}

ScheduleCommands.DragAndDropCommand.Execute(this.Schedule);


{% endhighlight  %}


