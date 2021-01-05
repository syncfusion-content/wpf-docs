---
layout: post
title: Appointment Drag and Drop in WPF Syncfusion SfScheduler | scheduler
description: This section explains how to handle an appointment drag and drop in WPF SfScheduler. Also, expalin about events in which used in drag and drop.
platform: wpf
control: SfScheduler
documentation: ug
---
# Appointment drag and drop in WPF Scheduler (SfScheduler)
Scheduler supports to reschedule the appointment by performing the drag and drop operation. This support is available for all views.

## Disable drag and drop
Scheduler supports to disable the appointment drag and drop by setting [AppointmentEditFlag](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_AppointmentEditFlag) property except `DragDrop`. In this case, you will not be able to perform appointment drag & drop.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        AppointmentEditFlag="Add,Edit,Resize">
 </syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
this.Schedule.AppointmentEditFlag = AppointmentEditFlag.Add | AppointmentEditFlag.Edit | AppointmentEditFlag.Resize;
{% endhighlight %}
{% endtabs %}

## AppointmentDragOver event
Scheduler notifies by [AppointmentDragOver](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) when drag the appointment. [AppointmentDragOverEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html) has following members which provides information for `AppointmentDragOver` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragOverEventArgs_Appointment) - Gets the Appointment that is dragging.

[DraggingPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragOverEventArgs_DraggingPoint) - Gets the dragging point of schedule appointment UI.

[DraggingTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragOverEventArgs_DraggingTime) - Gets the dragging time of the dragging appointment object.

[SourceResource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragOverEventArgs_SourceResource) - Gets the [SchedulerResource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SchedulerResource.html) where the appointment was located before starting the dragging. 

[TargetResource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragOverEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragOverEventArgs_TargetResource) - Gets the `SchedulerResource` where the appointment is currently being dragged over.

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
Scheduler notifies by [AppointmentDragStarting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) when start to drag the appointment. 
[AppointmentDragStartingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragStartingEventArgs.html) has following members which provides information for `AppointmentDragStarting` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragStartingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragStartingEventArgs_Appointment) - Get the selected appointment.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=netcore-3.1) - To avoid appointment dragging by enabling this property.

[Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDragStartingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDragStartingEventArgs_Resource) - gets the resource of an appointment under which the appointment is located.

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
Scheduler notifies by [AppointmentDropping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html) when you drop the appointment.
 [AppointmentDroppingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html) has following members which provides information for `AppointmentDropping` event.

[Appointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDroppingEventArgs_Appointment) - Gets the selected appointment that is dragged and dropped.

[DropTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDroppingEventArgs_DropTime) - Gets the dropped time of the dragged appointment.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=netcore-3.1) - To avoid appointment dropping by enabling this property.

[SourceResource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDroppingEventArgs_SourceResource) - Gets the `SchedulerResource` where the appointment was located before starting the dragging.

[TargetResource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.AppointmentDroppingEventArgs.html#Syncfusion_UI_Xaml_Scheduler_AppointmentDroppingEventArgs_TargetResource) - Gets the `SchedulerResource` where the appointment is currently being dragged over.

{% tabs %}
{% highlight c# %}
this.Schedule.AppointmentDropping += Schedule_AppointmentDropping;

private void Schedule_AppointmentDropping(object sender, AppointmentDroppingEventArgs e)
{
  //To notify when the appointment is dropping.
}
{% endhighlight %}
{% endtabs %} 