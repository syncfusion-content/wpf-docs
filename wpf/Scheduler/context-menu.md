---
layout: post
title: Context Menu Commands in WPF  Scheduler Control | Syncfusion
description: Learn about context menu support and its customization in Syncfusion WPF Scheduler (SfScheduler) control and more details. 
platform: wpf
control: SfScheduler
documentation: ug
---

# Context Menu Commands in WPF Scheduler (SfScheduler)

Scheduler provides the built-in `RoutedUICommands` support for handling context menu to add , edit and deleting the appointments in scheduler. There are two types of ContextMeu.

* Cell ContextMenu
* Appointment ContextMenu

## Context menu for cell

You can set the context menu for the cell by using `SfScheduler.CellContextMenu` property. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler.CellContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Add}}" CommandParameter ="{Binding}" Header="Add">
<MenuItem.Icon>
     <Path Width="20"
             Height="20"
             HorizontalAlignment="Center"
             VerticalAlignment="Center"
             Fill="#FF5A5A5B"
             Stretch="Uniform" />
</MenuItem.Icon>
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.CellContextMenu>

{% endhighlight %}
{% endtabs %}

![Cell ContextMenu in WPF Scheduler](images/scheduler/Resource/CellContextMenu.png)

## Context menu for appointment

You can set the context menu for the appointment by using `SfScheduler.AppointmentContextMenu` property. You can create context menu for Appointment, Timeslot and Monthcell in an efficient manner.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler.AppointmentContextMenu>
<ContextMenu>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Edit}}"
                    CommandParameter ="{Binding}"
                    Header="Edit">
<MenuItem.Icon>
                    <Path Width="20" 
                    Height="20"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Fill="#FF5A5A5B"
                    Stretch="Fill" />
</MenuItem.Icon>
</MenuItem>
<MenuItem Command="{Binding Source={x:Static Member=syncfusion:SchedulerCommands.Delete}}"
CommandParameter ="{Binding}"
Header="Delete">
<MenuItem.Icon>
            <Path Width="20"
            Height="20"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            Data="M21.546655,7.0632796E-06 C21.883706,-0.00066572799 22.051846,0.046859182 21.985844,0.085105601 21.985844,0.085105706 18.149817,2.3661337 15.459795,4.1891491 14.654603,4.735152 13.507447,5.8064868 12.312733,7.0429675 L12.265645,7.0920484 12.341799,7.1837728 C14.125798,9.3470118 15.905157,11.851134 17.039897,13.84393 18.552884,16.501994 18.99088,18.823049 18.821881,18.823049 L18.654883,18.823049 C18.654883,18.823049 16.500902,14.852954 13.944925,12.296894 12.986434,11.337997 11.848084,10.275033 10.716134,9.2747557 L10.458408,9.048093 10.387407,9.1277754 C9.3161123,10.336912 8.3393701,11.52151 7.6887401,12.398274 5.7887242,14.957258 5.5417207,15.095261 5.198716,15.794303 4.6507152,16.9173 6.1067274,20.571326 2.9787056,20.269321 0.8946903,20.067292 0.90368542,16.771302 1.0396879,16.165279 1.039688,16.165279 1.4646943,14.146277 3.5857051,12.027238 4.9094673,10.702228 6.5359638,9.1150982 8.3255475,7.5771367 L8.5209888,7.4112942 8.515951,7.4071881 C7.4753121,6.5646021 6.5652421,5.8958676 5.9719976,5.5677344 4.3920117,4.6937139 1.7210358,3.0476751 0.98804266,2.7766685 0.25504911,2.5076623 -0.4199447,1.9546491 0.32204843,1.2046314 1.0600419,0.45461359 2.7760263,-0.35240552 4.1220141,0.25360882 5.4670017,0.85862317 8.2939766,2.708667 10.579956,5.165725 10.651456,5.2424457 10.723317,5.3202512 10.795494,5.39908 L10.89612,5.5099146 11.114782,5.3459823 C11.306557,5.2048852 11.499266,5.0658362 11.692768,4.9291465 14.785793,2.7421748 16.837804,1.525122 18.755824,0.67110976 19.953959,0.13613158 20.984904,0.0011281502 21.546655,7.0632796E-06 z"
            Fill="#FFC1272D"
            Stretch="Fill" />
</MenuItem.Icon>
</MenuItem>
</ContextMenu>
</syncfusion:SfScheduler.AppointmentContextMenu>

{% endhighlight %}
{% endtabs %}
>**NOTE**
You need to check "IsAllDay" check box manually in AppointmentEditor window, when right click the context menu on AllDay panel.

![Appointment ContextMenu in WPF Scheduler](images/scheduler/Resource/AppointmentContextMenu.png)

## Events

### SchedulerContextMenuOpening

`SchedulerContextMenuOpening` event occurs while opening the context menu in SfScheduler. 

`SchedulerContextMenuOpeningEventArgs` has the following members which provides the information about `SchedulerContextMenuOpening` event.

* `MenuInfo` – Gets the instance of `SchedulerContextMenuInfo`. Its contains the information about datetime, appointment of the element opens the context menu. 

* `MenuType` – Gets the element type for which the context menu opens.

* `ContextMenu` – It represents shortcut context menu which is being opened.

## Adding custom commands

The below code example shows the context menu with command bindings.

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

![CustomContextMenu in WPF Scheduler](images/scheduler/Resource/CustomContextMenu.png)

You can download Adding custom  commnnds of ContextMenu Demo for WPF from here [SchedulerCustomContextMeu](https://github.com/SyncfusionExamples/how-to-use-custom-commands-in-context-menu)



