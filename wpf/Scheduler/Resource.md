---
layout: post
title: Resource Grouping scheduler | WPF| Syncfusion
description: WPF scheduler resource grouping allows users to select resources and display with efficient use of the events associated with the selected resources.
platform: WPF
control: SfScheduler
documentation: ug
---

# Resource in WPF Scheduler (SfScheduler)

The Scheduler control allows you to define resources that can be assigned to appointments in day,week,work week and timeline views. Resources let you associate additional information with your appointments. The schedule can group appointments based on the resources associated with them.

## Adding resources in scheduler
Resources can be visible to the Scheduler by setting `ResourceGroupType` property as `Resource` in `SfScheduler`.You need to set the `Name`, `Id`, and `Color` properties of `SchedulerResource` to create a resource.You can add the resource to the Scheduler by using `ResourceCollection` property of `SFScheduler`.

{% tabs %}
{% highlight c# %}

// Adding schedule resource in scheduler resource collection.
var ResourceCollection = new ObservableCollection<SchedulerResource>()
{
new SchedulerResource() { Name = "Sophia", Background = new SolidColorBrush(Colors.Red), Id = "1000", Foreground = new SolidColorBrush(Colors.White) },
new SchedulerResource() { Name = "Zoey Addison", Background = new SolidColorBrush(Colors.Blue), Id = "1001" },
new SchedulerResource() { Name = "James William", Background = new SolidColorBrush(Colors.Yellow), Id = "1002" },
};

// Adding scheduler resource collection to schedule resources of SfSchedule.
schedule.ResourceCollection = ResourceCollection;
{% endhighlight %}
{% endtabs %}


## Resource Grouping type in day,week,work week views.

You can handle the visibility of resource using the `ResourceGroupType` property of `SfScheduler`. If the appointments are not grouped based on resources the default value is Resource.

* Resource

* Date

### Resource

It groups the number of dates under each resource.

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource"/>
{% endhighlight %}
{% highlight c# %}
schedule.ViewType = SchedulerViewType.Week;
schedule.ResourceGroupType = ResourceGroupType.Resource;
{% endhighlight %}
{% endtabs %}

![WPF scheduler Resource Grouping](Resource_Images/Resource.png)

### Date
It groups the number of resources under each date.

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Date"/>
{% endhighlight %}
{% highlight c# %}
schedule.ViewType = SchedulerViewType.Week;
schedule.ResourceGroupType = ResourceGroupType.Date;
{% endhighlight %}
{% endtabs %}

![WPF scheduler Grouping resource by date ](Resource_Images/Resource_Date.png)

## Create appointments based on resource

You can associate `Resources` to the appointments by adding `Id` of resource in the `ResourceIdCollection` property of `ScheduleAppointment`. Appointments associated with the selected resources will be displayed in the `SfScheduler` views. 

{% tabs %}
{% highlight c# %}
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
var appointments = new ScheduleAppointment()
{
StartTime = DateTime.Now.AddMinutes(20),
EndTime = DateTime.Now.AddHours(2),
Subject = "General Meeting",
ResourceIdCollection = new ObservableCollection<object>() { ResourceCollection[0].Id, ResourceCollection[1].Id }
};

scheduleAppointmentCollection.Add(appointments);
this.schedule.ItemsSource = scheduleAppointmentCollection;

{% endhighlight %}
{% endtabs %}

### Appointment sharing to multiple resources
Multiple resources can share the same events, If appointment details edited or updated then the changes will reflect on all other shared instances simultaneously.

{% tabs %}
{% highlight c# %}

ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
var appointments = new ScheduleAppointment()
{
StartTime = DateTime.Now.AddMinutes(20),
EndTime = DateTime.Now.AddHours(2),
Subject = "General Meeting",
ResourceIdCollection = new ObservableCollection<object>() { ResourceCollection[0].Id, ResourceCollection[1].Id,ResourceCollection[2].Id }
};

scheduleAppointmentCollection.Add(appointments);
this.schedule.ItemsSource = scheduleAppointmentCollection;

{% endhighlight %}
{% endtabs %}

![WPF scheduler resource sharing ](Resource_Images/Resource_Sharing.png)

## Scheduler Resource Mapping

Schedule supports full data binding to any type of `IEnumerable` source. Specify the `ResourceMapping` attribute to map the properties in the underlying data source to the schedule resource.

| Property Name | Description |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `Name` | Maps the property name of custom class, which is equivalent to Name in ScheduleResource. |
| `Id` | Maps the property name of custom class, which is equivalent to Id in ScheduleResource. |
| `Image` | Maps the property name of custom class, which is equivalent to Image in ScheduleResource. |
| `Color`| Maps the property name of custom class, which is equivalent to Color in ScheduleResource. |

>**NOTE**
Custom resource class should contain a mandatory field for resource `Id`.

## Create business object for Resource
You can create a custom class `Employee` with mandatory fields `Name`, `Subject`, `Id`,`ForegroundColor` and `BackgroundColor`.

{% tabs %}
{% highlight c# %}
public class Employee
{
public string Name { get; set; }

public string ImageSource { get; set; }

public string Id { get; set; }

public Brush BackgroundColor { get; set; }

public Brush ForegroundColor { get; set; }
}

>**NOTE**

* You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

* You can map the properties of `Employee` class with our `SfScheduler` control using Scheduler `ResourceMapping`.

{% tabs %}
{% highlight xaml %}

<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.ResourceMapping>
<Schedule:ResourceMapping Id="Id" Name="Name" Background="BackgroundColor" Foreground="ForegroundColor"/>
</Schedule:SfScheduler.ResourceMapping>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
 // Schedule data mapping for custom resource.
ResourceMapping resourceMapping = new ResourceMapping();
resourceMapping.Name = "Name";
resourceMapping.Id = "Id";
resourceMapping.Background = "BackgroundColor";
resourceMapping.Foreground = "ForegroundColor";
schedule.ResourceMapping = resourceMapping;
{% endhighlight %}
{% endtabs %}

### Create custom resource collection

You can add resources for `Employee` that can be assigned to appointments using the `ResourceIdCollection` property of `SfScheduler`. You need to set the `Name`, `Id`, and `Color` properties of `ResourceCollection` to create a resource.

{% tabs %}
{% highlight c# %}
// Creating and Adding custom resource in scheduler resource collection.
var ResourceCollection = new ObservableCollection<object>()
{
new Employee () { Name = "Sophia", BackgroundColor = new SolidColorBrush(Colors.Red), Id = "1000", ForegroundColor = new SolidColorBrush(Colors.White) },
new Employee () { Name = " Kinsley Elena", BackgroundColor = new SolidColorBrush(Colors.Blue), Id = "1001" },
new Employee () { Name = " Adeline Ruby", BackgroundColor = new SolidColorBrush(Colors.Yellow), Id = "1002" },
};

//Adding schedule resource collection to schedule resources of SfSchedule.
schedule.ResourceCollection = ResourceCollection;

{% endhighlight %}
{% endtabs %}

You can associate `ResourceMapping` to the appointment by mapping resource in the `ResourceIdCollection` property of `ScheduleAppointment`. Custom appointments associated with the selected resources will be displayed in the `SfScheduler` views. 

### create business object to appointment

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents the custom data properties.   
/// </summary> 
public class Meeting
{
	public string EventName { get; set; }
	public DateTime From { get; set; }
	public DateTime To { get; set; }
    public ObservableCollection<object> Resources { get; set;}
}
{% endhighlight %}
{% endtabs %}
N>You can inherit this class from the INotifyPropertyChanged for dynamic changes in custom data.
You can map those properties of `Meeting` class to schedule appointment by using `AppointmentMapping` properties.
{%tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ItemsSource="{Binding Appointments}" ViewType="Week">
         <syncfusion:SfScheduler.AppointmentMapping>
            <syncfusion:AppointmentMapping
            Subject="EventName"
            StartTime="From"
            EndTime="To"
            ResourceIdCollection ="Resources"/>
        </syncfusion:SfScheduler.AppointmentMapping>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
//Schedule data mapping for custom appointments
AppointmentMapping dataMapping = new AppointmentMapping();
dataMapping.Subject = "EventName";
dataMapping.StartTime = "From";
dataMapping.EndTime = "To";
dataMapping.AppointmentBackground = "Color";
dataMapping.ResourceIdCollection= "Resources";
Schedule.AppointmentMapping = dataMapping;
{% endhighlight %}
{% endtabs %}


## Visible resource count

You can customize the number of visible resources in the current view using the `VisibleResourceCount` property of `DaysViewSettings`  or `TimelineViewSettings` in `SfScheduler`.

### Day view visible resource count
`DaysViewSetting` applicable for Day, Week and WorkWeek views. By default, value of this property is set to 1.
{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.DaysViewSettings>
<Schedule:DaysViewSettings VisibleResourceCount="3"/>
</Schedule:SfScheduler.DaysViewSettings>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
schedule.DaysViewSettings.VisibleResourceCount = 3;
{% endhighlight %}
{% endtabs %}


### Timeline View visible resource count
`TimelineViewSetting` applicable for Timeline views. By default, value of this property is set to 1.
{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.TimelineViewSettings>
<Schedule:TimelineViewSettings VisibleResourceCount="3"/>
</Schedule:SfScheduler.TimelineViewSettings>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
schedule.TimelineViewSettings.VisibleResourceCount = 3;
{% endhighlight %}
{% endtabs %}

## Create special time region based on Resource

Special time region can be created based on the resources in day , week , work week and timeline views.

### Day View

{% tabs %}
{% highlight c# %}

this.Schedule.DaysViewSettings.SpecialTimeRegions.Add(new SpecialTimeRegion
{
StartTime = new System.DateTime(2020, 09, 15, 13, 0, 0),
EndTime = new System.DateTime(2020, 09, 08, 15, 0, 0),
Text = "Lunch",
CanEdit = false,
Background = Brushes.Black,
Foreground = Brushes.White,
ResourceIdCollection = new ObservableCollection<object>() {"1001", "1002", "1003"}
});

{% endhighlight %}
{% endtabs %}

![WPF scheduler resource Special Time Region ](Resource_Images/Resource_SepcialRegion.png)

### Timeline View

{% tabs %}
{% highlight c# %}

this.schedule.TimelineViewSettings.SpecialTimeRegions.Add(new SpecialTimeRegion
{
StartTime = new System.DateTime(2020, 09, 15, 13, 0, 0),
EndTime = new System.DateTime(2020, 09, 08, 15, 0, 0),
Text = "Lunch",
CanEdit = false,
Background = Brushes.Black,
Foreground = Brushes.White,
ResourceIdCollection = new ObservableCollection<object>() { "1001", "1002", "1003" }
});

{% endhighlight %}
{% endtabs %}

## Resource appearnce customization

Resource UI customization using a template and template selectors support.

{% tabs %}
{% highlight xaml %}

<Window.Resources>
<DataTemplate  x:Key="DayViewResourceTemplate">
<Grid Background="Transparent">
<Border BorderThickness="0.3,0.3,0,0.3" BorderBrush="Gray" >
<StackPanel VerticalAlignment="Center" Orientation="Vertical">
<Border CornerRadius="36" Height="72" Width="72" BorderThickness="4" BorderBrush="{Binding BackgroundBrush}">
<Border CornerRadius="36" Height="64" Width="64" BorderThickness="4" BorderBrush="White">
<Image HorizontalAlignment="Center" VerticalAlignment="Center" Width="55"
Height="55" Source="{Binding ImageSource}" />
</Border>
</Border>
<TextBlock HorizontalAlignment="Center" VerticalAlignment="Center" FontSize="15"
Foreground="Black"  Text="{Binding Name}" />
</StackPanel>
</Border>
</Grid>
</DataTemplate>
</Window.Resources>

//used to find Image Source and Name properties
<Window.DataContext>
<local:Employee />
</Window.DataContext>


<Grid Name="grid">
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Week" ResourceGroupType="Resource" ResourceCollection="{Binding ResourceCollection}"
ResourceHeaderTemplate="{StaticResource DayViewResourceTemplate}">
</syncfusion:SfScheduler>
</Grid>

{% endhighlight %}
{% endtabs %}
