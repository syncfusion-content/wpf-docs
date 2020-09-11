---
layout: post
title: Resource Grouping scheduler | WPF| Syncfusion
description: WPF scheduler resource grouping allows users to select resources and display with efficient use of the events associated with the selected resources.
platform: WPF
control: SfScheduler
documentation: ug
---

# Resource Grouping in WPF Scheduler (SfScheduler)

Resource Grouping displays the resources as discrete views integrated with the scheduler to display appointments in all types of schedule views. It provides an intuitive user interface, which allows users to select single or multiple resources and display the events associated with the selected resources with efficient and effective utilization. Each resource can be assigned to a unique color to more easily identify the resource associated with an appointment. 

You can add resources that can be assigned to appointments using the `ResourceIdCollection` property of `SfScheduler`. You need to set the `Name`, `Id`, and `Color` properties of `ResourceCollection` to create a resource.

{% tabs %}
{% highlight c# %}
// Creating an instance for scheduler resource collection.
ObservableCollection<object> resources = new ObservableCollection<object>();

// Adding schedule resource in scheduler resource collection.
ResourceCollection = new ObservableCollection<object>()
{
new SchedulerResource() { Name = "Sophia", Background = new SolidColorBrush(Colors.Red), Id = "0", Foreground = new SolidColorBrush(Colors.White) },
new SchedulerResource() { Name = "Zoey Addison", Background = new SolidColorBrush(Colors.Blue), Id = "1" },
new SchedulerResource() { Name = "James William", Background = new SolidColorBrush(Colors.Yellow), Id = "2" },
};

// Adding schedule resource collection to schedule resources of SfSchedule.
schedule.ResourceCollection = ResourceCollection;
{% endhighlight %}
{% endtabs %}


## Resource Grouping visibility

You can handle the visibility of resource using the `ResourceGroupType` property of `SfScheduler`. If the appointments are not grouped based on resources the default value is Resource.

* Resource

* Date

* None

### Resource

It groups the number of dates under each resource and is applicable only on the scheduler views such as day, week, work week views.

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Resource" Grid.Row="1"/>
{% endhighlight %}
{% highlight c# %}
schedule.ViewType = SchedulerViewType.Week;
schedule.ResourceGroupType = ResourceGroupType.Resource;
{% endhighlight %}
{% endtabs %}

![WPF scheduler Resource Grouping](Resource_Images/Resource.png)

### Date
It groups the number of resources under each date and is applicable only on the scheduler views such as day, week, work week views.

{% tabs %}
{% highlight xaml %}
<Schedule:SfScheduler Name="schedule" ViewType="Week" ResourceGroupType="Date" Grid.Row="1"/>
{% endhighlight %}
{% highlight c# %}
schedule.ViewType = SchedulerViewType.Week;
schedule.ResourceGroupType = ResourceGroupType.Date;
{% endhighlight %}
{% endtabs %}

![WPF scheduler Grouping resource by date ](Resource_Images/Resource_Date.png)


### None
The resource not displays.


### Resource sharing 
Multiple resources can share the same events, If appointment details edited or updated then the changes will reflect on all other shared instances simultaneously.

{% tabs %}
{% highlight c# %}

ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
var appointments = new ScheduleAppointment()
{
StartTime = DateTime.Now.AddMinutes(20),
EndTime = DateTime.Now.AddHours(2),
Subject = "General Meeting",
ResourceIdCollection = new ObservableCollection<object>() { (ResourceCollection[0] as SchedulerResource).Id , (ResourceCollection[1] as SchedulerResource).Id}
};

scheduleAppointmentCollection.Add(appointments);
this.schedule.ItemsSource = scheduleAppointmentCollection;

{% endhighlight %}
{% endtabs %}

![WPF scheduler resource sharing ](Resource_Images/Resource_Sharing.png)

## Creating appointments by specifying the resource

You can associate `Resources` to the appointments by adding `Id` of resource in the `ResourceIdCollection` property of `ScheduleAppointment`. Appointments associated with the selected resources will be displayed in the `SfScheduler` views. 

{% tabs %}
{% highlight c# %}
// Creating an instance for scheduler appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
//Adding schedule appointment in scheduler appointment collection 
var appointments = new ScheduleAppointment()
{
StartTime = DateTime.Now.AddMinutes(20),
EndTime = DateTime.Now.AddHours(2),
Subject = "General Meeting",
ResourceIdCollection = new ObservableCollection<object>() { (ResourceCollection[0] as SchedulerResource).Id}
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


### Creating the custom resource collection

You can add resources for `CustomResourceClass` that can be assigned to appointments using the `ResourceIdCollection` property of `SfScheduler`. You need to set the `Name`, `Id`, and `Color` properties of `ResourceCollection` to create a resource.

{% tabs %}
{% highlight c# %}
// Creating an instance for scheduler resource collection.
ObservableCollection<object> resources = new ObservableCollection<object>();

// Adding custom resource in scheduler resource collection.
ResourceCollection = new ObservableCollection<object>()
{
new CustomResourceClass() { Name = "Peter", BackgroundColor = new SolidColorBrush(Colors.Red), Id = "0", ForegroundColor = new SolidColorBrush(Colors.White) },
new CustomResourceClass() { Name = "Natasha", BackgroundColor = new SolidColorBrush(Colors.Blue), Id = "1" },
new CustomResourceClass() { Name = "James William", BackgroundColor = new SolidColorBrush(Colors.Yellow), Id = "2" },
};

// Adding schedule resource collection to schedule resources of SfSchedule.
schedule.ResourceCollection = ResourceCollection;
{% endhighlight %}
{% endtabs %}


### Resource Mapping

Schedule supports full data binding to any type of `IEnumerable` source. Specify the `ResourceMapping` attribute to map the properties in the underlying data source to the schedule resource.

| Property Name | Description |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `Name` | Maps the property name of custom class, which is equivalent to Name in ScheduleResource. |
| `Id` | Maps the property name of custom class, which is equivalent to Id in ScheduleResource. |
| `Image` | Maps the property name of custom class, which is equivalent to Image in ScheduleResource. |
| `Color`| Maps the property name of custom class, which is equivalent to Color in ScheduleResource. |

>**NOTE**
Custom resource class should contain a mandatory field for resource `Id`.

You can map the properties of `CustomResourceClass` class with our `SfScheduler` control using Scheduler `ResourceMapping`.

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

You can associate `ResourceMapping` to the appointments by adding `Id` of resource in the `ResourceIdCollection` property of `ScheduleAppointment`. Appointments associated with the selected resources will be displayed in the `SfScheduler` views. 

{% tabs %}
{% highlight C# %}


{% endhighlight %}
{% endtabs %}

## Visible resource count

You can customize the number of visible resources in the current view using the `VisibleResourceCount` property of `DaysViewSettings`  or `TimelineViewSettings` in `SfScheduler`.

### DaysViewSetting visible resource count
`DaysViewSetting` applicable for Day, Week and WorkWeek views. By default, value of this property is set to 1.
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

## Special Time Region

Special time region can be created based on the resources in day , week , work week and timeline views.

{% tabs %}
{% highlight c# %}

ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
var appointments = new ScheduleAppointment()
{
StartTime = DateTime.Now.AddMinutes(20),
EndTime = DateTime.Now.AddHours(2),
Subject = "SUBJECT",
ResourceIdCollection = new ObservableCollection<object>() { (ResourceCollection[0] as SchedulerResource).Id , (ResourceCollection[1] as SchedulerResource).Id}
};

scheduleAppointmentCollection.Add(appointments);
this.schedule.ItemsSource = scheduleAppointmentCollection;

{% endhighlight %}
{% endtabs %}

![WPF scheduler resource Special Time Region ](Resource_Images/Resource_SepcialRegion.png)

## Customization of Resource Grouping

Resource UI customization using a template and template selectors support.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler.ResourceHeaderTemplate>
<DataTemplate>
<Grid Background="Transparent">
<Border BorderThickness="0.3" BorderBrush="Gray" >
<StackPanel VerticalAlignment="Center" Orientation="Vertical">
<Border CornerRadius="36" Height="72" Width="72" BorderThickness="4" BorderBrush="{Binding BackgroundBrush}">
<Border CornerRadius="36" Height="64" Width="64" BorderThickness="4" BorderBrush="White">
<Image HorizontalAlignment="Center" VerticalAlignment="Center"
Width="55"
Height="55"
Source="{Binding ImageSource}" />
</Border>
</Border>
<TextBlock
HorizontalAlignment="Center"
VerticalAlignment="Center"
FontSize="15"
Foreground="Black"
Text="{Binding Name}" />
</StackPanel>
</Border>
</Grid>
</DataTemplate>
</syncfusion:SfScheduler.ResourceHeaderTemplate>
{% endhighlight %}
{% endtabs %}
