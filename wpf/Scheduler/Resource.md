---
layout: post
title: Resource scheduler | WPF| Syncfusion
description: WPF scheduler resource view allows users to select resources and display with efficient use of the events associated with the selected resources.
platform: WPF
control: SfScheduler
documentation: ug
---

# Resource in WPF Scheduler (SfScheduler)

Resource displays the resources as discrete views integrated with the scheduler to display appointments in all types of schedule views. It provides an intuitive user interface, which allows users to select single or multiple resources and display the events associated with the selected resources with efficient and effective utilization. Each resource can be assigned to a unique color to more easily identify the resource associated with an appointment. 

You can add resources that can be assigned to appointments using the `ResourceIdCollection` property of `SfScheduler`. You need to set the `Name`, `Id`, and `Color` properties of `ResourceCollection` to create a resource.

{% tabs %}
{% highlight c# %}
// Creating an instance for scheduler resource collection.
ObservableCollection<object> resources = new ObservableCollection<object>();

// Adding schedule resource in scheduler resource collection.
ResourceCollection = new ObservableCollection<object>()
{
   new SchedulerResource() { Name = "Peter", Background = new SolidColorBrush(Colors.Red), Id = "5001", Foreground = new SolidColorBrush(Colors.White) },
   new SchedulerResource() { Name = "Natasha", Background = new SolidColorBrush(Colors.Blue), Id = "5002" },
   new SchedulerResource() { Name = "Steev Roger", Background = new SolidColorBrush(Colors.Green), Id = "5003" },
   new SchedulerResource() { Name = "Star Loard", Background = new SolidColorBrush(Colors.Yellow), Id = "5004"  },
};

// Adding schedule resource collection to schedule resources of SfSchedule.
schedule.ResourceCollection = ResourceCollection;
{% endhighlight %}
{% endtabs %}


## Resource view visibility

You can handle the visibility of resource using the `ResourceGroupType` property of `SfScheduler`. If the appointments are not grouped based on resources the default value is Resource.

`Resource`: Displays the dates grouped under resource.

`Date`: Displays the resources grouped within a date.

`None`: The resource not display

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource" Grid.Row="1"/>
{% endhighlight %}
{% highlight c# %}
schedule.ViewType = SchedulerViewType.Week;
schedule.ResourceGroupType = ResourceGroupType.Resource;
{% endhighlight %}
{% endtabs %}

## Creating appointments by specifying the resource

You can associate `Resources` to the appointments by adding `Id` of resource in the `ResourceIdCollection` property of `ScheduleAppointment`. Appointments associated with the selected resources will be displayed in the `SfScheduler` views. 

{% tabs %}
{% highlight c# %}
// Creating an instance for scheduler appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
//Adding schedule appointment in scheduler appointment collection 
var scheduleAppointment = new ScheduleAppointment()
{
   StartTime = currentDate.AddMinutes(20),
   EndTime = currentDate.AddMinutes(40),
   Subject = "Business meeting",
   AppointmentBackground = new SolidColorBrush(Colors.RoyalBlue),
   IsAllDay = true,
   ResourceIdCollection=new ObservableCollection<object>() { "5001","5002"}
};

scheduleAppointmentCollection.Add(scheduleAppointment1);
//Adding schedule appointment collection to ItemsSource of SfScheduler
scheduler.ItemsSource = scheduleAppointmentCollection;
{% endhighlight %}
{% endtabs %}

## Creating appointments by specifying the custom resource
You can create a custom class `CustomResourceClass` with mandatory fields `Name`, `Subject`, `Id`,`ForegroundColor` and `BackgroundColor`. 

{% tabs %}
{% highlight c# %}
public class CustomResourceClass : INotifyPropertyChanged
    {
        private string subject;
        private int id;
        private Brush background;
        private Brush foreground;

        private string name;

        public string Name
        {
            get { return name; }
            set
            {
                name = value;
                this.RaisePropertyChanged("Name");
            }
        }


        public string Subject
        {
            get { return subject; }
            set
            {
                subject = value;
                this.RaisePropertyChanged("Subject");
            }
        }

        public int Id
        {
            get { return id; }
            set
            {
                id = value;
                this.RaisePropertyChanged("Code");
            }
        }

        public Brush BackgroundColor
        {
            get { return background; }
            set
            {
                background = value;
                this.RaisePropertyChanged("BackgroundColor");
            }
        }

        public Brush ForegroundColor
        {
            get { return foreground; }
            set
            {
                foreground = value;
                this.RaisePropertyChanged("ForegroundColor");
            }
        }

        public event PropertyChangedEventHandler PropertyChanged;

        private void RaisePropertyChanged(string propertyName)
        {
            this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
    }

{% endhighlight %}
{% endtabs %}

>**NOTE**
You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map the properties of `Event` class with our `SfScheduler` control using Scheduler `AppointmentMapping`.


## Assigning custom appointment by specifying the resource

You can associate resources to the custom appointments using the equivalent field of `ResourceIdCollection` in custom appointment class.

### Creating custom appointment

You can create a custom class `Event` with mandatory fields `From`, `To`, `EventName`, and `ResourceIdCollection`. 

{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents custom data properties.
/// </summary>
public class Event
    {
        public string EventName { get; set; }
        public DateTime From { get; set; }
        public DateTime To { get; set; }
        public bool IsAllDay { get; set; }
        public ObservableCollection<object> ResourceIdCollection { get; set; }
    }
{% endhighlight %}
{% endtabs %}

>**NOTE**
You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map the properties of `CustomResourceClass` class with our `SfScheduler` control using Scheduler `ResourceMapping`.

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.ResourceMapping>
<Schedule:ResourceMapping Id="Code" Name="Subject" Background="BackgroundColor" Foreground="ForegroundColor"/>
</Schedule:SfScheduler.ResourceMapping>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
 // Schedule data mapping for custom appointments.
  AppointmentMapping appointmentMapping = new AppointmentMapping();
  appointmentMapping.IsAllDay = "AllDay";
  appointmentMapping.StartTime = "From";
  appointmentMapping.EndTime = "To";
  appointmentMapping.Subject = "Event name";
  appointmentMapping.ResourceIdCollection = "ResourceIdCollection";
  Schedule.AppointmentMapping = appointmentMapping;
{% endhighlight %}
{% endtabs %}


## Mapping

Schedule supports full data binding to any type of `IEnumerable` source. Specify the `ResourceMapping` attribute to map the properties in the underlying data source to the schedule resource.

| Property Name | Description |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `Name` | Maps the property name of custom class, which is equivalent to Name in ScheduleResource. |
| `Id` | Maps the property name of custom class, which is equivalent to Id in ScheduleResource. |
| `Image` | Maps the property name of custom class, which is equivalent to Image in ScheduleResource. |
| `Color`| Maps the property name of custom class, which is equivalent to Color in ScheduleResource. |

>**NOTE**
Custom resource class should contain a mandatory field for resource `Id`.

### Creating a custom resource

You can create a custom class `Event` with mandatory fields `From`, `To`, `EventName`, and `ResourceIdCollection`. 

>**NOTE**
You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map the properties of `Event` class with our `SfScheduler` control using `ResourceMapping`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule ScheduleView="WeekView" ShowResourceView="True">
<Schedule:SfScheduler.ResourceMapping>
<Schedule:ResourceMapping Id="Code" Name="Subject" Background="BackgroundColor" Foreground="ForegroundColor"/>
</Schedule:SfScheduler.ResourceMapping>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
// Creating an instance for resource mapping.
ResourceMapping resourceMapping = new ResourceMapping();

// Mapping the custom data fields. 
resourceMapping.Name = "Subject";
resourceMapping.Background = "BackgroundColor";
resourceMapping.Foreground = "ForegroundColor";
{% endhighlight %}
{% endtabs %}

## Visible resource count

You can customize the number of visible resources in the current view using the `VisibleResourceCount` property of `DaysViewSettings`  or `TimelineViewSettings` in `SfScheduler`.

### DaysViewSetting visible resource count
`DaysViewSetting` applicable for Day, Week and WorkWeek views. By default, value of this property is set to 1.F
{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.DaysViewSettings>
<Schedule:DaysViewSettings VisibleResourceCount="2"/>
</Schedule:SfScheduler.DaysViewSettings>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
schedule.DaysViewSettings.VisibleResourceCount = 3;
{% endhighlight %}
{% endtabs %}


### TimelineViewSetting visible resource count
`TimelineViewSetting` applicable for Timeline views. By default, value of this property is set to 1.
{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource">
<Schedule:SfScheduler.TimelineViewSettings>
<Schedule:TimelineViewSettings VisibleResourceCount="2"/>
</Schedule:SfScheduler.TimelineViewSettings>
</Schedule:SfScheduler>
{% endhighlight %}
{% highlight c# %}
schedule.TimelineViewSettings.VisibleResourceCount = 3;
{% endhighlight %}
{% endtabs %}

