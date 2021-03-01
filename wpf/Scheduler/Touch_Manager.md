---
layout: post
title: Touch Support | WPF | Syncfusion
description: Learn how to perform touch support in SfScheduler in WPF
platform: wpf
control: Touch Support
documentation: ug
---

## Touch-Events in WPF Scheduler
Scheduler control have touch support and it provides Touch UI which is easy to access the elements.

The Scheduler control provides support for touch manipulation like DragandDrop the appointments, Scrolling or swiping the views, and selecting the cell or appointment of the controller.

DragandDrop :  The drag operation will be triggered during a TapAndHold an appointment.

Scrolling or swiping the views : By default, the date can be navigated to next and previous views using touch gesture, by swiping the control from right to left and left to right direction.

Selection: We can perform cell and appointment selection of the controller.

## To perform CellContextMenu using touch.

By default, Holding on any timeslot or monthcell, The Cell Contextmenu will appear only on empty cells and cell selection should be performed.

## To perform Appointment ContextMenu using touch.

To enable touch context menu for appointments in the scheduler,by disabling the appointment drag and drop to setting AppointmentEditFlag property except DragDrop. In this case, you will not be able to perform appointment drag & drop.

The Appointment Contextmenu will be displayed only on appointments and appointment selection should be performed. 

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

N>
By default, the drag operation will be performed during holding the appointment.

If we hold on any empty cells(Timeslot or month) or appointment by using touch and swipe to prev view or next view, the contextmenu will not be performed. The view should be switching.

If we Set AppointmentEditFlag="Resize", while resizing an appointment by holding through MouseLeftButton, the appointment Contextmenu will not be displayed(when the appointment is in resizing state). The Appointment resizing only performed.

If Enabled DragandDrop by setting AppointmentEditFlag="DragDrop", the Appointment ContextMenu will not be performed by holding(touch and mouseLeftButton), we can perform only Drag and Drop the appointments by using both touch and mouse.

If we set AppointmentEditFlag="None" and holding on any elements(timeslot or monthcell or appointment) by using touch or MouseLeftButton, the corresponding context menu will be displayed, and selection will be performed.

The ContextMenu on SpecialTimeRegion, DisabledDate and MinMax Date : The context menu will be restricted in any of the highlighted regions and  the ContextMenu and  selection (cell or appointment) will not be performed by holding(both Touch and MouseLeftButton).