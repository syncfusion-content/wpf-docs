---
layout: post
title: Context Menu Commands in WPF  Scheduler Control | Syncfusion
description: Learn about context menu support and its customization in Syncfusion WPF Scheduler (SfScheduler) control and more details. 
platform: wpf
control: SfScheduler
documentation: ug
---

# Context Menu Commands in WPF Scheduler (SfScheduler)

Scheduler provides the built-in `RoutedUICommands` support for handling context menu to add , edit and deleting the appointments in scheduler. There are two types of ContextMenu.

* CellContextMenu
* AppointmentContextMenu

## Cell context menu

You can set the context menu for time slot and month cells by using `SfScheduler.CellContextMenu` property. CellContextMenu will be appeared only on time slot or month cells.

>**NOTE**
CellContextMenu will enables the menu item which binds the `SchedulerCommands.Add`built-in command only when it has the menu items with also `SchedulerCommands.Edit` and `SchedulerCommands.Delete` built-in commands.
The DataContext for the context menu is `SchedulerContextMenuInfo` Command parameter of menu item should bound to context menu's data context when using the commands in `SchedulerCommands`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler.CellContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Add}}" CommandParameter ="{Binding}" Header="Add">
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.CellContextMenu>

{% endhighlight %}
{% endtabs %}

![Cell ContextMenu in WPF Scheduler](images/scheduler/ContextMenu/CellContextMenu.png)

## Appointment context menu

You can set the context menu for time slot and month cells by using `SfScheduler.AppointmentContextMenu` property. AppointmentContextMenu will be appeared only on time slot or month cells.

>**NOTE**
AppointmentContextMenu will enables the menu item which binds the `SchedulerCommands.Add`built-in command only when it has the menu items with also `SchedulerCommands.Edit` and `SchedulerCommands.Delete` built-in commands.
The DataContext for the context menu is `SchedulerContextMenuInfo` Command parameter of menu item should bound to context menu's data context when using the commands in `SchedulerCommands`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler.AppointmentContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Edit}}"
                    CommandParameter ="{Binding}"
                    Header="Edit">
</MenuItem>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Delete}}"
CommandParameter ="{Binding}"
Header="Delete">
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.AppointmentContextMenu>

{% endhighlight %}
{% endtabs %}

![Appointment ContextMenu in WPF Scheduler](images/scheduler/ContextMenu/AppointmentContextMenu.png)

## Events

### SchedulerContextMenuOpening

`SchedulerContextMenuOpening` event occurs while opening the context menu in SfScheduler. 

`SchedulerContextMenuOpeningEventArgs` has the following members which provides the information about `SchedulerContextMenuOpening` event.

* `MenuInfo` – Returns the `SchedulerContextMenuInfo` which contains the information about date time, appointment of the element opens the context menu.`AppointmentContextMenu` and `CellContextMenu` received this information as DataContext.. 

* `MenuType` – Gets the element type for which the context menu opens.

* `ContextMenu` – It represents shortcut context menu which is being opened.

## Adding custom commands

You can add the menu items with custom commands for `CellContextMenu` and `AppointmentContextMenu`. The below code example shows the context menu with custom commands.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
        <local:ScheduleViewModel/>
</Window.DataContext>
<ContextMenu>
<MenuItem Command="{Binding CopyCommand}" CommandTarget="{Binding}" Header="Copy"></MenuItem>
<MenuItem Command="{Binding PasteCommand}" CommandTarget="{Binding}" Header="Paste"></MenuItem>
</ContextMenu>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
   public class CustomCommand : ICommand
    {
        Action _action;
        public CustomCommand(Action action)
        {
            _action = action;
        }



        public event EventHandler CanExecuteChanged;



        public bool CanExecute(object parameter)
        {
            return true;
        }



        public void Execute(object parameter)
        {
            _action();
        }
    }

   /// <summary>
    /// Schedule View Model
    /// </summary>
    public class ScheduleViewModel : INotifyPropertyChanged
    {

        /// <summary>
        /// Gets the values that represents the Copy command
        /// </summary>
        ICommand copyCommand;

        /// <summary>
        ///  Gets the values that represents the Paste command
        /// </summary>
        ICommand pasteCommand;

        public ICommand CopyCommand
        {
            get
            {
                return copyCommand;
            }
        }

    
        public ICommand PasteCommand
        {
            get
            {
                return pasteCommand;
            }
        }


        /// <summary>
        /// Initializes a new instance of the <see cref="ScheduleViewModel" /> class.
        /// </summary>
        public ScheduleViewModel()
        {
            copyCommand = new CustomCommand(Copy);
            pasteCommand = new CustomCommand(Paste);
        }

    }

{% endhighlight %}
{% endtabs %}

![CustomContextMenu in WPF Scheduler](images/scheduler/ContextMenu/CustomContextMenu.png)

You can get the sample from [here] (https://github.com/SyncfusionExamples/how-to-use-custom-commands-in-context-menu)

## Limitations

You need to check "IsAllDay" check box manually in AppointmentEditor window, when right click the context menu on AllDay panel.
