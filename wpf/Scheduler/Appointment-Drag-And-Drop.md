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

## Disable drag and drop
You can disable appointment drag and drop by setting [AppointmentEditFlag](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~AppointmentEditFlag.html) property to `None`. In this case, you will not be able to perform add, edit, resize and drag & drop the appointments.

{% tabs %}
{% highlight XAML %}
 <syncfusion:SfScheduler
            x:Name="Schedule"
           AppointmentEditFlag="None">
        </syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

## AppointmentDragOver event
Scheduler notifies by [AppointmentDragOver](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~AppointmentDragOver_EV.html) when drag the appointment. [AppointmentDragEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragEventArgs.html) has following members which provides information for `AppointmentDragOver` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragEventArgs~Appointment.html) - Gets the Appointment that is dragging.

[DraggingPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragEventArgs~DraggingPoint.html) - Gets the dragging point of schedule appointment UI.

[DraggingTime](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragEventArgs~DraggingTime.html) - Gets the dragging time of the dragging appointment object.

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
Scheduler notifies by [AppointmentDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~AppointmentDragStarting_EV.html) when start to drag the appointment. 
[AppointmentDragStartingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragStartingEventArgs.html) has following members which provides information for `AppointmentDragStarting` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDragStartingEventArgs~Appointment.html) - Get the selected appointment.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=netcore-3.1) - To avoid appointment dragging by enabling this property.

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
Scheduler notifies by [AppointmentDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~AppointmentDropping_EV.html) when you drop the appointment.
 [AppointmentDroppingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html) has following members which provides information for `AppointmentDropping` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs~Appointment.html) - Gets the selected appointment that is dragged and dropped.

[DropTime](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs~DropTime.html) - Gets the dropped time of the dragged appointment.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=netcore-3.1) - To avoid appointment dropping by enabling this property.

{% tabs %}
{% highlight c# %}
this.Schedule.AppointmentDropping += Schedule_AppointmentDropping;

  private void Schedule_AppointmentDropping(object sender, AppointmentDroppingEventArgs e)
        {
            //To notify when the appointment is dropping.
        }
{% endhighlight %}
{% endtabs %}