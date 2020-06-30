---   
layout: post   
title: Getting Started | SfScheduler | WPF | Syncfusion   
description: This section explain about how to integrate WPF Scheduler into an applicationl and enable its basic features with example.. 
platform: WPF   
control: SfScheduler   
documentation: ug   
---   
    
# Getting Started with WPF Scheduler (SfScheduler)   
    
This section provides you an overview for working with Scheduler for WPF and also provides a walk through to configure Scheduler control in real time scenario.   

## Assembly deployment
Refer to the section on [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#SfScheduler) for a list of assemblies or NuGet Packages to be used as a guide for using control in any application. Further information on installing the NuGet package can be found in the following link in a WPF application: [How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages). You can also use [Syncfusion Reference Manager](https://help.syncfusion.com/wpf/visual-studio-integration/visual-studio-extensions/add-references) to refer the scheduler's dependent assemblies.

## Create simple application with SfSchedule

* [Creating project](#Creating-project)
* [Adding control via Designer](#Adding-control-via-Designer)
* [Adding control manually in XAML](#Adding-control-manually-in-XAML)
* [Adding control manually in C#](#Adding-control-manually-in-C#)  

### Creating project
In Visual Studio, create a new WPF project to show the features of the scheduler control and add the following namespace to the added assemblies.

Assembly: `Syncfusion.SfScheduler.WPF`

Namespace: `Syncfusion.UI.Xaml.Scheduler`

### Adding control via Designer

Scheduler control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

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
    xmlns:skinmanager ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    skinmanager:SfSkinManager.VisualStyle="MaterialLight"
    Title="Getting Started"
    Icon="App.ico"
    WindowStartupLocation="CenterScreen">

<Window.Resources>
    <ObjectDataProvider x:Key="schedulerviewtypes" MethodName="GetValues"
                            ObjectType="{x:Type system:Enum}">
    <ObjectDataProvider.MethodParameters>
    <x:Type  Type="{x:Type syncfusion:SchedulerViewType}"/>
    </ObjectDataProvider.MethodParameters>
    </ObjectDataProvider>
</Window.Resources>
    
<Window.DataContext>
    <local:MeetingDetails/>
</Window.DataContext>
<Grid>
    <syncfusion:SfScheduler x:Name="Schedule"
                ItemsSource="{Binding Events}"
                ViewType="{Binding ElementName=viewtypecombobox, Path=SelectedValue}">
            <syncfusion:SfScheduler.MonthViewSettings>
                <syncfusion:MonthViewSettings AppointmentDisplayMode="Appointment"
                                        AppointmentDisplayCount="2"/>
            </syncfusion:SfScheduler.MonthViewSettings>
   </syncfusion:SfScheduler>

   <StackPanel
            HorizontalAlignment="Right"
            VerticalAlignment="Top"
            Margin="0,20,25,0">
            <ComboBox x:Name="viewtypecombobox" ItemsSource="{Binding Source={StaticResource schedulerviewtypes}}"
                                    SelectedIndex="2"  Width="100"/>
  </StackPanel>
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
   

## Change different Scheduler Views  
    
Scheduler control provides five different types of views to display dates and it can be assigned to the control by using `SchedulerViewType` property. By default the control is assigned with `MonthView`. Current date will be displayed initially for all the Schedule views.  

### Month View   
    
`Month` in Scheduler control is to view entire dates of a particular month.
    
{% tabs %}   
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" ViewType="Month">
{% endhighlight %}  
{% highlight c# %}
Schedule.ViewType =SchedulerViewType.Month;
{% endhighlight %}   
{% endtabs %}   
    
![Month View](GettingStarted_images/Month.png)

## Events/Appointments data mapping

* [Create an event Data Model](#creating-custom-class-for-appointments) 
* [Create view model](#create-view-model)
* [Bind to Scheduler appointment](#Bind-to-Scheduler-appointment)  
* [Add Scheduler items source.](#Add-Scheduler-items-source.) 
  
### Create an event Data Model 
  
`ScheduleAppointment` is used to create the scheduler events or appointments, which holds the details about the appointment to be rendered in schedule.   
  
{% tabs %}     
{% highlight c# %}
ScheduleAppointmentCollection appointmentCollection = new ScheduleAppointmentCollection();   
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

### Create view model 

You can schedule meetings for a particular day by setting `From` and `To` of `Meeting` class.Also you can change subject and color of appointment using `EventName` and `color` of Meeting class. In a separate ViewModel class you can describe the collection of custom appointments.  

{% tabs %}   
{% highlight c# %} 
public class ScheduleViewModel : NotificationObject
    {  
        private List<DateTime> startTimeCollection;     
        public ObservableCollection<Meeting> Appointments{ get; set; }

        public ScheduleViewModel()
        {
            this.Appointments = new ObservableCollection<Meeting>();
            this.IntializeAppoitments();
        }

        private void IntializeAppoitments()
        {
            Meeting meeting = new Meeting();
            meeting.From = new DateTime(date.Year, date.Month, date.Day, randomTime.Next(9, 11), 0, 0);
            meeting.To = meeting.From.AddDays(2).AddHours(1);
            meeting.EventName = this.currentDayMeetings[randomTime.Next(9)];
            meeting.Color = this.colorCollection[randomTime.Next(9)];
            meeting.IsAllDay = true;
            meeting.StartTimeZone = string.Empty;
            meeting.EndTimeZone = string.Empty;
            this.Appointments.Add(meeting);
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
    }
{% endhighlight %}
{% endtabs %}   


>**NOTE**
You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

### Bind to Scheduler appointment

You can map those properties of `Meeting` class with our schedule control by using `SfScheduler.AppointmentMapping`.   

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
    ItemsSource="{Binding Appointments}"
    ViewType="{Binding ElementName=viewtypecombobox, Path=SelectedValue}">
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
<syncfusion:SfScheduler.MonthViewSettings>
<syncfusion:MonthViewSettings AppointmentDisplayMode="Appointment"
    AppointmentDisplayCount="2"/>
</syncfusion:SfScheduler.MonthViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}  
Schedule.AppointmentMapping.IsAllDay = "AllDay";
Schedule.AppointmentMapping.StartTime = "From";
Schedule.AppointmentMapping.EndTime = "To";
Schedule.AppointmentMapping.Subject = "Event name";
Schedule.AppointmentMapping.AppointmentBackground = "color";
Schedule.AppointmentMapping.StartTimeZone = "StartTimeZone";
Schedule.AppointmentMapping.EndTimeZone = "EndTimeZone";  
{% endhighlight %}
{% endtabs %}

You can download the entire source code of creating CustomAppointment for WPF from
here [SchedulerDataBindingDemo](https://github.com/SyncfusionExamples/scheduler-data-binding-demo)

### Add Scheduler items source.

Create meetings of type `ObservableCollection <Meeting>`  and assign those appointments collection `Meetings` to the `ItemsSource` property of `SfScheduler`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"    ItemsSource="{Binding Events}"
              ViewType="Month">
<syncfusion:SfScheduler.MonthViewSettings>
<syncfusion:MonthViewSettings AppointmentDisplayMode="Appointment"
                                        AppointmentDisplayCount="2"/>
</syncfusion:SfScheduler.MonthViewSettings>
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
MeetingDetails meetingDetails = new MeetingDetails();
Schedule.ItemsSource = meetingDetails.Events;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for WPF from
here [SchedulerGettingStarted](https://github.com/SyncfusionExamples/scheduler_getting_started_demo)

## Change first day of week

Scheduler control will be rendered with `Sunday` as the first day of the week, but you can customize to any day by using `FirstDayOfWeek` property of `SfSchedule`.
    
{% tabs %}  
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule" FirstDayOfWeek="Tuesday"/> 
{% endhighlight %}   
{% highlight c# %}
//setting first day of the week    
Schedule.FirstDayOfWeek = DayOfWeek.Thursday;   
{% endhighlight %}  
{% endtabs %}   
    
![First Day of week](GettingStarted_images/DayOfWeek.png) 