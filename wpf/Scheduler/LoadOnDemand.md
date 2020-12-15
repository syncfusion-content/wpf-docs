---
layout: post
title: Load appointments on-demand in SfScheduler| WPF| Syncfusion
description: This section explains how to load  appointments on demand from visible date ranges in WPF Scheduler.  
platform: wpf
control: SfScheduler
documentation: ug
---
# Load on demand in WPF Scheduler (SfScheduler)
The scheduler supports to loading appointment on-demand with loading indicator and its improves the loading performance when you have appointments range for multiple years.

## Load on-demand on recurring appointment
  Scheduler control calculates the recurring series and displays appointments from the series in the active view. You can get pattern appointment from `RecurrenceHelper.GetPatternAppointment` method, If recurrence appointment in visible date range. 

* The recurrence appointment should be added to the Scheduler [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ItemsSource) until the date of recurrence ends.

* If [RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.ScheduleAppointment.html#Syncfusion_UI_Xaml_Scheduler_ScheduleAppointment_RecurrenceRule) added with count or end date, you can use the [RecurrenceHelper.GetRecurrenceDateTimeCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.RecurrenceHelper.html#Syncfusion_UI_Xaml_Scheduler_RecurrenceHelper_GetRecurrenceDateTimeCollection_System_String_System_DateTime_System_Nullable_System_DateTime__System_Nullable_System_DateTime__) method to get recurrence date collection and compare recursive dates in the current visible date range. Then add recurrence appointment in scheduler [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ItemsSource), If recursive dates in current visible date range. 

* If `RecurrenceRule` added with no end date , then recurrence appointment should be added in the scheduler `ItemsSource` when all visible date changed from the recurrence start date.

## Load on demand event
`QueryAppointments` event is used to load appointment in on-demand for visible date range. `QueryAppointments` will be raised once any one of the following action will be taken. 

 * Once the [ViewChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ViewChanged) event is raised, QueryAppointments will be raised.

* If the appointment has been added or removed or changed (Resize, drag and drop)  in the current time visible date range, then the `QueryAppointments` event will not be triggered. Since appointments for that visible date range have already been loaded.

* The QueryAppointments event is triggered when the Schedule [ResourceCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ResourceCollection) is updated to load appointments based on the changed resource collection.

* QueryAppointments event will be triggered on [ResourceGroupType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ResourceGroupType) changed.

### QueryAppointments
Scheduler notifies by `QueryAppointments` event, when user change visible date range. You might start and stop the loading indicator animation before and after the appointments loaded using ShowBusyIndicator.
`QueryAppointmentsEventArgs` has following members which provides information for `QueryAppointments` event.

[VisibleDateRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.DateRange.html) -  Gets the current visible date range of scheduler that is used to load the appointments.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler"
                        ViewType="Month" QueryAppointments="Scheduler_QueryAppointments">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
Scheduler.QueryAppointments += Scheduler_QueryAppointments;
private void Scheduler_QueryAppointments(object sender, QueryAppointmentsEventArgs e)
{
 Scheduler.ShowBusyIndicator = true;
 Scheduler.ItemsSource = this.GetAppointments(e.VisibleDateRange);
 Scheduler.ShowBusyIndicator = false;
}

private IEnumerable GetAppointments(DateRange dateRange)
 {
  // Add codes to generate appointments from the date renage
}
{% endhighlight %}
{% endtabs %}

## Load on demand command
Scheduler notifies by `LoadOnDemandCommand` when user change visible date range. You can get visible date range from `QueryAppointmentsEventArgs`. The default value for this ICommand is null. The `QueryAppointmentsEventArgs` passed as a command parameter. It will be invoked once any one of the following action will be taken.

* Once the [ViewChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ViewChanged) event is raised, `LoadOnDemandCommand` will be raised.

* If the appointment has been added or removed or changed (Resize, drag and drop)  in the current time visible date range, then the `LoadOnDemandCommand` will not be triggered. Since appointments for that visible date range have already been loaded.

* The `LoadOnDemandCommand` is triggered when the Schedule [ResourceCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ResourceCollection) is updated to load appointments based on the changed resource collection.

* `LoadOnDemandCommand` will be triggered on [ResourceGroupType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Scheduler.SfScheduler.html#Syncfusion_UI_Xaml_Scheduler_SfScheduler_ResourceGroupType) changed.

 ### On-demand loading of appointments
You can load appointments for scheduler itemsource in `Execute` method of `LoadOnDemandCommand`. In execute method, you have can perform following operations,

* You might start and stop the loading indicator animation before and after the appointments loaded  using ShowBusyIndicator.
* Once got appointment collection, You can load into scheduler itemsource.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler"
                        ViewType="Month" 
                        ShowBusyIndicator="{Binding ShowBusyIndicator}"
                        LoadOnDemandCommand="{Binding LoadOnDemandCommand}"
                        ItemsSource="{Binding Events}">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}

public class LoadOnDemandViewModel : INotifyPropertyChanged
  {
    public ICommand LoadOnDemandCommand { get; set; }
    private IEnumerable events;
    public IEnumerable Events
      {
        get { return events; }
        set
          {
            events = value;
            this.RaisePropertyChanged("Events");
          }
      }
    private bool showBusyIndicator;
    public bool ShowBusyIndicator
    {
      get { return showBusyIndicator; }
      set
          {
            showBusyIndicator = value;
            this.RaisePropertyChanged("ShowBusyIndicator");
          }
    }
    
    public ObservableCollection<SchedulerResource> ResourceCollection
    {
      get { return resourceCollection; }
      set
        {
         resourceCollection = value;
         this.RaisePropertyChanged("ResourceCollection");
        }
    }
    public SchedulerViewModel()
    {
       this.LoadOnDemandCommand = new DelegateCommand(ExecuteOnDemandLoading, CanExecuteOnDemandLoading);
    }
       
    public event PropertyChangedEventHandler PropertyChanged;
    public async void ExecuteOnDemandLoading(object parameter)
    {
      this.ShowBusyIndicator = true;
      await Task.Delay(1000);
      await Application.Current.MainWindow.Dispatcher.BeginInvoke(DispatcherPriority.ApplicationIdle, new Action(() =>
            {
                this.Events = this.GetAppointments((parameter as QueryAppointmentsEventArgs).VisibleDateRange);
            }));
      this.ShowBusyIndicator = false;
    }

    private bool CanExecuteOnDemandLoading(object sender)
    {
      return true;
    }

    private IEnumerable GetAppointments(DateRange dateRange)
    {
      // Add Codes to generate appointments
    }

    private void RaisePropertyChanged(string propertyName)
    {
        this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    } 
  }
{% endhighlight %}
{% endtabs %}

![Load on-demand in WPF Scheduler](LoadOnDemand_Images/LoadOnDemand.mp4)

N> [View sample in GitHub]