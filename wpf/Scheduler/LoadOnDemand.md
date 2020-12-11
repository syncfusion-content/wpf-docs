---
layout: post
title: Load appointments on-demand in SfScheduler| WPF| Syncfusion
description: This section explains how to load  appointments on demand from visible date ranges in WPF Scheduler.  
platform: wpf
control: SfScheduler
documentation: ug
---
# Load on demand in WPF Scheduler (SfScheduler)
The scheduler supports to loading appointment on-demand and its improves the loading performance when you have appointments range for multiple years.

## Load on demand event
`QueryAppointments` event is used to load appointment in on-demand for visible date range. `QueryAppointments` will be raised once any one of the following action will be taken.
 * `ViewChanged` event is raised
 * `ResourceCollection` is updated 
 * `ResourceGroupType` is changed. 
If an appointment has been added, edited or deleted within the visible date range, then the `QueryAppointments` event will not be triggered.

### QueryAppointments
Scheduler notifies by `QueryAppointments` event, when user change visible date range.
`QueryAppointmentsEventArgs` has following members which provides information for `QueryAppointments` event.
`VisibleDateRange` -  Gets the current visible date range of scheduler that is used to load the appointments.

The recurrence appointment should be added to the Scheduler `ItemsSource` until the date of recurrence ends.

If `RecurrenceRule` added with count or end date, you can use the `GetRecurrenceDateTimeCollection` method to get recurrence date collection and compare recursive dates in the current visible date range. Then add recurrence appointment in scheduler `ItemsSource`, if recursive dates in current visible date range. 

If `RecurrenceRule` added with no end date , then recurrence appointment should be added in the Scheduler `ItemsSource` when all visible date changed from the recurrence start date.

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
 var dateRange = e.VisibleDateRange;
}
{% endhighlight %}
{% endtabs %}

## Load on demand command
Scheduler notifies by `LoadOnDemandCommand` when user change visible date range. You can get visible date range from `QueryAppointmentsEventArgs`. The default value for this ICommand is null. The `QueryAppointmentsEventArgs` passed as a command parameter. It will be invoked once any one of the following action will be taken.
 * `ViewChanged` event is raised
 * `ResourceCollection` is updated 
 * `ResourceGroupType` is changed.

If an appointment has been added, deleted or updated within the visible date range, then the `LoadOnDemandCommand` will not be invoked.

 ### On-demand loading of appointments
You can load appointments for scheduler itemsource in `Execute` method of `LoadOnDemandCommand`. In execute method, you have can perform following operations,

* Show or hide busy indicator in execute method until get appointment collection.
* Once got appointment collection, You can load into scheduler itemsource.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Scheduler"
                        ViewType="Month" 
                        LoadOnDemandCommand="{Binding LoadOnDemandCommand}">
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
public ICommand LoadOnDemandCommand { get; set; }

this.LoadOnDemandCommand = new DelegateCommand(ExecuteOnDemandLoading, CanExecuteOnDemandLoading);

/// <summary>
/// Execute method is called when any item is requested for load-on-demand items.
/// </summary>
/// <param name="parameter">QueryAppointmentsEventArgs is passed as parameter </param>
private async void ExecuteOnDemandLoading(object parameter)
{
  var dateRange = (parameter as QueryAppointmentsEventArgs).VisibleDateRange;
}

private bool CanExecuteOnDemandLoading(object sender)
{
  return true;
}
{% endhighlight %}
{% endtabs %}

>N> [View sample in GitHub]