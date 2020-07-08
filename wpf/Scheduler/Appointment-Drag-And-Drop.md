---
layout: post
title: Appointment Drag and Drop in WPF Syncfusion SfScheduler | scheduler
description: This section explains how to handle an appointment drag and drop in WPF SfScheduler. Also, expalin about events in which used in drag and drop.
platform: wpf
control: SfScheduler
documentation: ug
---
# Appointment drag and drop in WPF Scheduler (SfScheduler)
Scheduler supports to reschedule the appointment by performing the drag and drop operation. This support is available for all views except 'Month' view.

## AppointmentDragOver event
Scheduler notifies by `AppointmentDragOver` when drag the appointment. `AppointmentDraggingEventArgs` has following members which provides information for `AppointmentDragOver` event.

`Appointment` - Gets the Appointment that is dragging.

`DraggingPoint` - Gets the dragging point of schedule appointment UI.

`DraggingTime` - Gets the dragging time of the dragging appointment object.

{% tabs %}
{% highlight c# %}
this.Schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

 private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
        {
            //To notify when dragging the appointment.
        }
{% endhighlight %}
{% endtabs %}

## AppointmentDragStarting event
Scheduler notifies by `AppointmentDragStarting` when start to drag the appointment. 
`AppointmentDragStartingEventArgs` has following members which provides information for `AppointmentDragStarting` event.

`Appointment` - Get the selected appointment.
`Cancel`- To avoid appointment dragging by enabling this property.

{% tabs %}
{% highlight c# %}
this.Schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
        {
            //To notify when start to drag the appointment.
        }
{% endhighlight %}
{% endtabs %}

## AppointmentDropping event
Scheduler notifies by `AppointmentDropping` when you drop the appointment.
 `AppointmentDroppingEventArgs` has following members which provides information for `AppointmentDropping` event.

`Appointment` - Gets the selected appointment that is dragged and dropped.

`DropTime` - Gets the dropped time of the dragged appointment.

`Cancel` - To avoid appointment dropping by enabling this property.

{% tabs %}
{% highlight c# %}
this.Schedule.AppointmentDropping += Schedule_AppointmentDropping;

  private void Schedule_AppointmentDropping(object sender, AppointmentDroppingEventArgs e)
        {
            //To notify when the appointment is dropping.
        }
{% endhighlight %}
{% endtabs %}