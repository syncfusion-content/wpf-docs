---
layout: post   
title: Getting Started | SfScheduler | WPF | Syncfusion   
description: This section explain about how to integrate WPF Scheduler(SfScheduler) into an applicationl and enable its basic features with example.. 
platform: WPF   
control: SfScheduler   
documentation: ug   
---   
    
# Getting Started with WPF Scheduler (SfScheduler)   
    
This section provides you an overview for working with SfScheduler for WPF and also provides a walk through to configure SfScheduler control in real time scenario.   

## Assembly deployment
Refer to the section on [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#SfScheduler) for a list of assemblies or NuGet Packages to be used as a guide for using control in any application. Further information on installing the NuGet package can be found in the following link in a WPF application: [How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages). You can also use [Syncfusion Reference Manager](https://help.syncfusion.com/wpf/visual-studio-integration/visual-studio-extensions/add-references) to refer the scheduler's dependent assemblies.

## Create simple application with SfScheduler

In this section, you will create WPF application with SfScheduler control.

* [Creating project](#Creating-project)
* [Adding control via Designer](#Adding-control-via-Designer)
* [Adding control manually in XAML](#Adding-control-manually-in-XAML)
* [Adding control manually in C#](#Adding-control-manually-in-C#)  

### Creating project
In Visual Studio, create a new WPF project to show the features of the SfScheduler control and add the following namespace to the added assemblies.

Assembly: `Syncfusion.SfScheduler.WPF`

Namespace: `Syncfusion.UI.Xaml.Scheduler`

### Adding control via Designer

`SfScheduler` control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

### Adding control manually in XAML

To add the control manually in XAML page, follow the given steps:

1. Add the `Syncfusion.SfScheduler.WPF` assembly reference to the project.
2. Import WPF schema `http://schemas.syncfusion.com/wpf` in the XAML page.
3. Declare the `SfScheduler` control in XAML page.

{% tabs %}
{% highlight xaml %}
<Window
    x:Class="GettingStarted.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:GettingStarted"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:system="clr-namespace:System;assembly=mscorlib"  
    WindowStartupLocation="CenterScreen">
<Grid>
    <syncfusion:SfScheduler x:Name="Schedule" ViewType="Month"/>
</Grid>
</Window>
{% endhighlight %}
{% endtabs %}

### Adding control manually in C#

To add the control manually in C# page,Add the `Syncfusion.SfScheduler.WPF` assembly reference to the project.

{% tabs %}
{% highlight c#%}
using Syncfusion.UI.Xaml.Scheduler;
namespace GettingStarted
{
    public partial class MainWindow : Window
    {
       SfScheduler schedule = new SfScheduler();
       this.Content = schedule;
    }
}
{% endhighlight %}
{% endtabs %}
   

## Change different SfScheduler Views  
    
`SfScheduler` control provides five different types of views to display dates and it can be assigned to the control by using `ViewType` property. By default the control is assigned with `MonthView`. Current date will be displayed initially for all the Schedule views.  

### Month View     

{% tabs %}   
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Month">
{% endhighlight %}  
{% highlight c# %}
Schedule.ViewType =SchedulerViewType.Month;
{% endhighlight %}   
{% endtabs %}   

## Appointments
`SfScheduler` has a built-in capability to handle the appointment arrangement internally based on the `ScheduleAppointment` collections. You need to allocate the collection generated to `Appointments` property.

### Adding Appointments
`ScheduleAppointment` is a class that includes the specific of scheduled appointment. It has some basic properties such as `StartTime`, `EndTime`, `Subject` and some additional information about the appointment can be added with `Notes`, `Location`, `IsAllDay` properties.

{% tabs %}   
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ViewType="Month"/>
{% endhighlight %}  
{% highlight c# %} 
//Creating new event   
ScheduleAppointmentCollection appointmentCollection = new ScheduleAppointmentCollection();

//Creating new event   
ScheduleAppointment clientMeeting = new ScheduleAppointment();
DateTime currentDate = DateTime.Now;
DateTime startTime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, 10, 0, 0);
DateTime endTime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, 12, 0, 0);
clientMeeting.StartTime = startTime;
clientMeeting.EndTime = endTime;
clientMeeting.Subject = "ClientMeeting";
appointmentCollection.Add(clientMeeting);
Schedule.ItemsSource = appointmentCollection;
{% endhighlight %}   
{% endtabs %} 

You can download the entire source code of this demo for WPF from
here [SchedulerGettingStarted](https://github.com/SyncfusionExamples/scheduler_getting_started_demo)

### Events/Appointments data mapping

You can also map custom appointments data to our scheduler.

Here steps to render meetings using `SfScheduler` control with respective custom data properties created in a class `Meeting`.

* [Create an event Data Model](#creating-custom-class-for-appointments) 
* [Create view model](#create-view-model)
* [Bind to Scheduler appointment](#Bind-to-Scheduler-appointment)  
* [Add Scheduler items source.](#Add-Scheduler-items-source.) 
* [Bind item source for Scheduler](#Bind-item-source-for-Scheduler)
  
#### Create an event Data Model 
  
You can create a custom class `Meeting` with mandatory fields `From`, `To` and `EventName`that is used to map the information of the appointment.

{% highlight c# %}  
    public class Meeting : INotifyPropertyChanged
    {
        DateTime from, to;
        string eventName;
        bool isAllDay;
        string startTimeZone, endTimeZone;
        Brush color;
        public Meeting()
        {
        }

        public DateTime From
        {
            get { return from; }
            set
            {
                from = value;
                RaisePropertyChanged("From");
            }
        }

        public DateTime To
        {
            get { return to; }
            set
            {
                to = value;
                RaisePropertyChanged("To");
            }
        }

        public bool IsAllDay
        {
            get { return isAllDay; }
            set
            {
                isAllDay = value;
                RaisePropertyChanged("IsAllDay");
            }
        }
        public string EventName
        {
            get { return eventName; }
            set
            {
                eventName = value;
                RaisePropertyChanged("EventName");
            }
        }
        public string StartTimeZone
        {
            get { return startTimeZone; }
            set
            {
                startTimeZone = value;
                RaisePropertyChanged("StartTimeZone");
            }
        }
        public string EndTimeZone
        {
            get { return endTimeZone; }
            set
            {
                endTimeZone = value;
                RaisePropertyChanged("EndTimeZone");
            }
        }

        public Brush Color
        {
            get { return color; }
            set
            {
                color = value;
                RaisePropertyChanged("Color");
            }
        }

        public event PropertyChangedEventHandler PropertyChanged;
        protected virtual void RaisePropertyChanged(string propertyName, object oldValue = null)
        {
            this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }

    }
{% endhighlight %}
  

#### Create view model 

By setting `From` and `To` of `Meeting` class, you can schedule meetings for a specific day. You can also change the subject and color of appointment using `EventName` and `Color` property. You may define the list of custom appointments in a separate class of `ViewModel`.

{% tabs %}   
{% highlight c# %} 
public class ScheduleViewModel
    {
        private List<string> teamManagement;
        private List<string> currentDayMeetings;
        private List<string> minTimeMeetings;
        private List<Brush> colorCollection;
        private List<DateTime> startTimeCollection;
        private List<DateTime> endTimeCollection;
        private List<int> randomNums = new List<int>();
        public ScheduleViewModel()
        {
            this.Events = new ObservableCollection<Meeting>();
            this.CreateRandomNumbersCollection();
            this.CreateStartTimeCollection();
            this.CreateEndTimeCollection();
            this.CreateSubjectCollection();
            this.CreateColorCollection();
            this.InitializeDataForBookings();
            this.IntializeAppoitments();
        }
        public ObservableCollection<Meeting> Events
        {
            get;
            set;
        }
        private List<Point> GettingTimeRanges()
        {
            List<Point> randomTimeCollection = new List<Point>();
            randomTimeCollection.Add(new Point(9, 11));
            randomTimeCollection.Add(new Point(12, 14));
            randomTimeCollection.Add(new Point(15, 17));

            return randomTimeCollection;
        }
        private void InitializeDataForBookings()
        {
            this.currentDayMeetings = new List<string>();
            this.currentDayMeetings.Add("General Meeting");
            this.currentDayMeetings.Add("Plan Execution");

            this.minTimeMeetings = new List<string>();
            this.minTimeMeetings.Add("Work log alert");
            this.minTimeMeetings.Add("Birthday wish alert");

            this.colorCollection = new List<Brush>();
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FF339933")));
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FF00ABA9")));
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FFE671B8")));
        }
        private void IntializeAppoitments()
        {
            Random randomTime = new Random();
            List<Point> randomTimeCollection = this.GettingTimeRanges();

            DateTime date;
            DateTime dateFrom = DateTime.Now.AddDays(-100);
            DateTime dateTo = DateTime.Now.AddDays(100);
            var random = new Random();
            var dateCount = random.Next(4);
            DateTime dateRangeStart = DateTime.Now.AddDays(0);
            DateTime dateRangeEnd = DateTime.Now.AddDays(1);

            for (date = dateFrom; date < dateTo; date = date.AddDays(1))
            {
                if (date.Day % 7 != 0)
                {
                    for (int additionalAppointmentIndex = 0; additionalAppointmentIndex < 1; additionalAppointmentIndex++)
                    {
                        Meeting meeting = new Meeting();
                        int hour = randomTime.Next((int)randomTimeCollection[additionalAppointmentIndex].X, (int)randomTimeCollection[additionalAppointmentIndex].Y);
                        meeting.From = new DateTime(date.Year, date.Month, date.Day, hour, 0, 0);
                        meeting.To = meeting.From.AddHours(1);
                        meeting.EventName = this.currentDayMeetings[randomTime.Next(1)];
                        meeting.Color = this.colorCollection[randomTime.Next(2)];
                        meeting.IsAllDay = false;
                        meeting.StartTimeZone = string.Empty;
                        meeting.EndTimeZone = string.Empty;
                        this.Events.Add(meeting);
                    }
                }
                else
                {
                    Meeting meeting = new Meeting();
                    meeting.From = new DateTime(date.Year, date.Month, date.Day, randomTime.Next(9, 11), 0, 0);
                    meeting.To = meeting.From.AddDays(2).AddHours(1);
                    meeting.EventName = this.currentDayMeetings[randomTime.Next(1)];
                    meeting.Color = this.colorCollection[randomTime.Next(2)];
                    meeting.IsAllDay = true;
                    meeting.StartTimeZone = string.Empty;
                    meeting.EndTimeZone = string.Empty;
                    this.Events.Add(meeting);
                }
            }
            DateTime minDate;
            DateTime minDateFrom = DateTime.Now.AddDays(-2);
            DateTime minDateTo = DateTime.Now.AddDays(2);

            for (minDate = minDateFrom; minDate < minDateTo; minDate = minDate.AddDays(1))
            {
                Meeting meeting = new Meeting();
                meeting.From = new DateTime(minDate.Year, minDate.Month, minDate.Day, randomTime.Next(9, 18), 30, 0);
                meeting.To = meeting.From;
                meeting.EventName = this.minTimeMeetings[randomTime.Next(0, 1)];
                meeting.Color = this.colorCollection[randomTime.Next(0, 2)];
                meeting.StartTimeZone = string.Empty;
                meeting.EndTimeZone = string.Empty;
                
                this.Events.Add(meeting);
            }
        }
        private void CreateSubjectCollection()
        {
            this.teamManagement = new List<string>();
            this.teamManagement.Add("General Meeting");
            this.teamManagement.Add("Plan Execution");
            this.teamManagement.Add("Project Plan");
            this.teamManagement.Add("Consulting");
        }
        private void CreateColorCollection()
        {
            this.colorCollection = new List<Brush>();
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FFA2C139")));
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FFD80073")));
            this.colorCollection.Add(new SolidColorBrush((Color)ColorConverter.ConvertFromString("#FF1BA1E2")));
        }
        private void CreateRandomNumbersCollection()
        {
            this.randomNums = new List<int>();

            Random rand = new Random();

            for (int i = 0; i < 10; i++)
            {
                int random = rand.Next(9, 15);
                this.randomNums.Add(random);
            }
        }
        private void CreateStartTimeCollection()
        {
            this.startTimeCollection = new List<DateTime>();
            DateTime currentDate = DateTime.Now;

            int count = 0;
            for (int i = -5; i < 5; i++)
            {
                DateTime startTime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, this.randomNums[count], 0, 0);
                DateTime startDateTime = startTime.AddDays(i);
                this.startTimeCollection.Add(startDateTime);
                count++;
            }
        }
        private void CreateEndTimeCollection()
        {
            this.endTimeCollection = new List<DateTime>();
            DateTime currentDate = DateTime.Now;
            int count = 0;
            for (int i = -5; i < 5; i++)
            {
                DateTime endTime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, this.randomNums[count] + 1, 0, 0);
                DateTime endDateTime = endTime.AddDays(i);
                if (i == -3 || i == 3)
                {
                    endDateTime = endTime.AddDays(i).AddHours(22);
                }

                this.endTimeCollection.Add(endDateTime);
                count++;
            }
        }
    }
{% endhighlight %}
{% endtabs %}   

#### Bind to SfScheduler appointment

You can map those properties of `Meeting` class with our `SfScheduler` control by using `SfScheduler.AppointmentMapping` property.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule">
<syncfusion:SfScheduler.AppointmentMapping>
<syncfusion:AppointmentMapping
    Subject="EventName"
    StartTime="From"
    EndTime="To"
    AppointmentBackground="Color"
    IsAllDay="IsAllDay"
    StartTimeZone="StartTimeZone"
    EndTimeZone="EndTimeZone"/>
</syncfusion:SfScheduler.AppointmentMapping>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}  
  AppointmentMapping appointmentMapping = new AppointmentMapping();
  appointmentMapping.IsAllDay = "AllDay";
  appointmentMapping.StartTime = "From";
  appointmentMapping.EndTime = "To";
  appointmentMapping.Subject = "Event name";
  appointmentMapping.AppointmentBackground = "color";
  appointmentMapping.StartTimeZone = "StartTimeZone";
  appointmentMapping.EndTimeZone = "EndTimeZone";
{% endhighlight %}
{% endtabs %}

#### Bind item source for SfScheduler
Create meetings of type `ObservableCollection<Events>` and assign those appointments collection `Events` to the `ItemsSource` property of SfScheduler.

{% tabs %}
{% highlight xaml %}
    <Window.DataContext>
        <local:ScheduleViewModel/>
    </Window.DataContext>
      <syncfusion:SfScheduler x:Name="Schedule"
                ItemsSource="{Binding Events}"
                ViewType="Month">
      </syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
 ScheduleViewModel viewModel = new ScheduleViewModel();
 Schedule.ItemsSource = viewModel.Events;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of creating CustomAppointment for WPF from
here [SchedulerDataBindingDemo](https://github.com/SyncfusionExamples/scheduler-data-binding-demo)

## Change first day of week

SfScheduler control will be rendered with `Sunday` as the first day of the week, but you can customize to any day by using `FirstDayOfWeek` property of `SfScheduler`.
    
{% tabs %}  
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" FirstDayOfWeek="Tuesday"/> 
{% endhighlight %}   
{% highlight c# %}
//setting first day of the week    
Schedule.FirstDayOfWeek = DayOfWeek.Thursday;   
{% endhighlight %}  
{% endtabs %}   
