---
layout: post
title: Context Menu and Commands in WPF Scheduler Control | Syncfusion
description: Learn about the context menu support and built-in `RoutedUICommands` support for handling the context menu to add, edit, and delete appointments. 
platform: wpf
control: SfScheduler
documentation: ug
---

# Context Menu Commands in WPF Scheduler (SfScheduler)

The WPF scheduler has support to define a context menu commands for appointments, time slots, and month cells are right-clicked. It will also have the built-in `RoutedUICommands` support for handling the context menu to add, edit, and delete appointments. There are two types of `ContextMenu`.

* CellContextMenu
* AppointmentContextMenu

## Cell context menu

You can set the context menu for time slot and month cells by using the `SfScheduler.CellContextMenu` property. The `CellContextMenu` will appear only when the time slot or month cells are right-clicked.

>**NOTE**
The menu items which bind the `SchedulerCommands.Edit` and `SchedulerCommands.Delete` built-in commands will be disabled in the `CellContextMenu`.
The `DataContext` for the context menu is `SchedulerContextMenuInfo` `CommandParameter` of menu item should bound to context menu's data context when using the commands in `SchedulerCommands`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
<syncfusion:SfScheduler.CellContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Add}}" CommandParameter ="{Binding}" CommandTarget="{Binding ElementName=Schedule}" Header="Add">
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.CellContextMenu>
</syncfusion:SfScheduler>

{% endhighlight %}
{% endtabs %}

![Cell ContextMenu in WPF Scheduler](ContextMenu/CellContextMenu.png)

## Appointment context menu

You can set the context menu for schedule appointments by using the `SfScheduler.AppointmentContextMenu` property. The `AppointmentContextMenu` will be displayed only on appointments that are right-clicked.

>**NOTE**
The menu item which binds the `SchedulerCommands.Add` command will be disabled in the `AppointmentContextMenu`.
The `DataContext` for the context menu is `SchedulerContextMenuInfo` Command parameter of menu item should bound to context menu's data context when using the commands in `SchedulerCommands`.
In month view, the `AppointmentContextMenu` opens when the `MonthViewSettings.AppointmentDisplayMode` is set to `AppointmentDisplayMode.Appointment`.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week">
<syncfusion:SfScheduler.AppointmentContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Edit}}"
                    CommandParameter ="{Binding}" CommandTarget="{Binding ElementName=Schedule}"
                    Header="Edit">
</MenuItem>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Delete}}"
CommandParameter ="{Binding}"
Header="Delete">
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.AppointmentContextMenu>
</syncfusion:SfScheduler>

{% endhighlight %}
{% endtabs %}

![Appointment ContextMenu in WPF Scheduler](ContextMenu/AppointmentContextMenu.png)

## SchedulerContextMenuOpening event

The `SchedulerContextMenuOpening` event occurs while opening the `AppointmentContextMenu` or `CellContextMenu` in the SfScheduler. 

`SchedulerContextMenuOpeningEventArgs` has the following members which provides the information about `SchedulerContextMenuOpening` event.

* `MenuInfo` – Returns the `SchedulerContextMenuInfo` which contains the information about date time, appointment of the element opens the context menu. The `AppointmentContextMenu` and `CellContextMenu` received this information as a DataContext.

* `MenuType` – Gets the element type for which the context menu opens.

* `ContextMenu` – It represents a shortcut context menu that is being opened.

