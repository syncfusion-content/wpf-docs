---
layout: post
title: Recurrence in WPF Wizard Control control | Syncfusion
description: Learn here all about Recurrence support in Syncfusion WPF Schedule (Classic) control and more.
platform: wpf
control: SfSchedule
documentation: ug
---

## Recurrence Appointment
Recurring appointments can generate on a daily, weekly, monthly, or yearly interval. By setting [RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_RecurrenceRule) and activating the [IsRecursive](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_IsRecursive) property in Schedule appointment which will build recurring appointments.

## Recurrence Rule
The [RecurrenceRule](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_RecurrenceRule) is a string value that includes the details of the recurrence appointments such as repeat form - daily/weekly/monthly/yearly, how many times it needs to be repeated, the duration of the interval and also the time period to make the appointment, etc.
`RecurrenceRule` has the following properties and the Scheduler control makes the recurrence appointments with their respective time period.

<table>
<tr><th>PropertyName</th><th>Purpose</th></tr>
<tr><td>FREQ</td><td>Maintains the repeat type value of appointments. (Example: Daily, Weekly, Monthly, Yearly, Every week day) Example: FREQ=DAILY;INTERVAL=1</td></tr>
<tr><td>INTERVAL</td><td>Maintains the interval value of appointments. For example, when you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday. (creates the appointment on all days by leaving the interval of one day gap) Example: FREQ=DAILY;INTERVAL=1</td></tr>
<tr><td>COUNT</td><td>It holds the appointment’s count value. For example, when the recurrence appointment count value is 10, it means 10 appointments are created in the recurrence series. Example: FREQ=DAILY;INTERVAL=1;COUNT=10</td></tr>
<tr><td>UNTIL</td><td>This property is used to store the recurrence end date value. For example, when you set the end date of appointment as 6/30/2014, the UNTIL property holds the end date value when the recurrence actually ends. Example: FREQ=DAILY;INTERVAL=1;UNTIL=8/25/2014</td></tr>
<tr><td>BYDAY</td><td>It holds the “DAY” values of an appointment to render.For example, when you create the weekly appointment, select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday). When Monday is selected, the first two letters of the selected day “MO” is stored in the “BYDAY” property. When you select multiple days, the values are separated by commas. Example: FREQ=WEEKLY;INTERVAL=1;BYDAY=MO,WE;COUNT=10</td></tr>
<tr><td>BYMONTHDAY</td><td>This property is used to store the date value of the Month while creating the Month recurrence appointment. For example, when you create a Monthly recurrence appointment in the date 3, it means the BYMONTHDAY holds the value 3 and creates the appointment on 3rd day of every month. Example: FREQ=MONTHLY;BYMONTHDAY=3;INTERVAL=1;COUNT=10</td></tr>
<tr><td>BYMONTH</td><td>This property is used to store the index value of the selected Month while creating the yearly appointments. For example, when you create the yearly appointment in the Month June, it means the index value for June month is 6 and it is stored in the BYMONTH field. The appointment is created on every 6th month of a year. Example: FREQ=YEARLY;BYMONTHDAY=16;BYMONTH=6;INTERVAL=1;COUNT=10</td></tr>
<tr><td>BYSETPOS</td><td>This property is used to store the index value of the week. For example, when you create the monthly appointment in second week of the month, the index value of the second week (2) is stored in BYSETPOS. Example: FREQ=MONTHLY;BYDAY=MO;BYSETPOS=2;UNTIL=8/11/2014</td></tr>
</table>

## Recurrence Pattern

Scheduler supports four types of recurrence patterns. You can set this recurrence pattern using [RecurrenceType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceType.html) property of `RecurrenceRule`. 

<table>
<tr><th>RecurrenceType</th><th>RecurrenceProperties</th><th>Description</th></tr>
<tr><td>Daily</td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsDailyEveryNDays">IsDailyEveryNDays</a></td><td>Gets or sets a value indicating whether the recurrence should be set based on specified day interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_DailyNDays">DailyNDays</a></td><td>Gets or sets the day interval on which recurrence has to be set.</td></tr>
<tr><td>Weekly</td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_WeeklyEveryNWeeks">WeeklyEveryNWeeks</a></td><td>Gets or sets the week interval on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklySunday">IsWeeklySunday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Sundays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklyMonday">IsWeeklyMonday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Mondays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklyTuesday">IsWeeklyTuesday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Tuesdays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklyWednesday">IsWeeklyWednesday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Wednesdays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklyThursday">IsWeeklyThursday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Thursdays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklyFriday">IsWeeklyFriday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Fridays with specified week interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsWeeklySaturday">IsWeeklySaturday</a></td><td>Gets or sets a value indicating whether the recurrence should be applied on Saturdays with specified week interval.</td></tr>
<tr><td>Monthly</td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsMonthlySpecific">IsMonthlySpecific</a></td><td>Gets or sets a value indicating whether the recurrence has to be set for particular month day i.e. MonthlySpecificMonthDay</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_MonthlyEveryNMonths">MonthlyEveryNMonths</a></td><td>Gets or sets the month interval on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_MonthlyNthWeek">MonthlyNthWeek</a></td><td>Gets or sets the week of month on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_MonthlySpecificMonthDay">MonthlySpecificMonthDay</a></td><td>Gets or sets the day on which recurrence has to be set for every month.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_MonthlyWeekDay">MonthlyWeekDay</a></td><td>Gets or sets the day of week on which monthly recurrence has to be set.</td></tr>
<tr><td>Yearly</td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsYearlySpecific">IsYearlySpecific</a></td><td>Gets or sets a value indicating whether the recurrence should be set based on specific year interval.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlyEveryNYears">YearlyEveryNYears</a></td><td>Gets or sets the year interval on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlyGenericMonth">YearlyGenericMonth</a></td><td>Gets or sets the generic month of year on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlyNthWeek">YearlyNthWeek</a></td><td>Gets or sets the week of year on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlySpecificMonth">YearlySpecificMonth</a></td><td>Gets or sets the specific month of year on which recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlySpecificMonthDay">YearlySpecificMonthDay</a></td><td>Gets or sets the specific day of month on which yearly recurrence has to be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_YearlyWeekDay">YearlyWeekDay</a></td><td>Gets or sets the day of week on which yearly recurrence has to be set.</td></tr>
<tr><td>Common</td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsRangeEndDate">IsRangeEndDate</a></td><td>Gets or sets a value indicating whether the date should be specified for ending the recurrence.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsRangeNoEndDate">IsRangeNoEndDate</a></td><td>Gets or sets a value indicating whether the recurrence should be ended.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_IsRangeRecurrenceCount">IsRangeRecurrenceCount</a></td><td>Gets or sets a value indicating whether the count of recurrence should be set.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_RangeEndDate">RangeEndDate</a></td><td>Gets or sets the date to end the recurrence.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_RangeStartDate">RangeStartDate</a></td><td> Gets or sets the date to start the recurrence.</td></tr>
<tr><td></td><td><a href = "https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.RecurrenceProperties.html#Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_RangeRecurrenceCount">RangeRecurrenceCount</a></td><td>Gets or sets the count for recurring appointment.</td></tr>
</table>

## Recurrence Rule Generator

[RRuleGenerator](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleHelper.html#Syncfusion_UI_Xaml_Schedule_ScheduleHelper_RRuleGenerator_Syncfusion_UI_Xaml_Schedule_RecurrenceProperties_System_DateTime_System_DateTime_) method is used to construct the recurrence rule that can be found in the [ScheduleHelper](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleHelper.html) of the Scheduler control. Assign the generated recurrence rule to the appointment property called `RecurrenceRule` that assign the recurrence properties to the appointment. Or from any iCal directory, the client may apply recurrence rule directly.

### Applying Recurrence to Appointments

Use `RRuleGenerator` method to generate the recurrence rule.

{% tabs %}
{% highlight c# %}
// Daily Recursive Appointment       
ScheduleAppointment SchApp = new ScheduleAppointment();  
SchApp.Subject = "Team Meeting";
SchApp.Notes = "Daily Recurrence";    
SchApp.Location = "Meeting Hall 1";   
SchApp.StartTime = currentDate;    
SchApp.EndTime = currentDate.AddHours(4);    
SchApp.AppointmentBackground = new SolidColorBrush((Color.FromArgb(0xFF, 0xD8, 0x00, 0x73)));
SchApp.IsRecursive = true;
// Setting Recurrence Properties     
RecurrenceProperties RecProp = new RecurrenceProperties();      
RecProp.RecurrenceType = RecurrenceType.Daily;      
RecProp.IsDailyEveryNDays = true;           
RecProp.DailyNDays = 2;           
RecProp.IsRangeRecurrenceCount = true;        
RecProp.IsRangeNoEndDate = false;       
RecProp.IsRangeEndDate = false;       
RecProp.RangeRecurrenceCount = 100;            
// Generating RRULE using ScheduleHelper           
SchApp.RecurrenceRule = ScheduleHelper.RRuleGenerator(RecProp, SchApp.StartTime, SchApp.EndTime);     
AppCollection.Add(SchApp);   
Schedule.Appointments = AppCollection;
{% endhighlight %}
{% endtabs %}

![WPF scheduler recurrence appointment](Recurrence_images/Recurrence-appointment.jpeg)

## Creating Custom Recurrence Appointment using Recurrence Builder
you need to create a custom class `Meeting` with mandatory fields `From`, `To`, `EventName` and `RecurrenceRule` to create custom recurrence appointment.

{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents custom data properties.
/// </summary>
public class Meeting
{
    public string EventName { get; set; }
    public DateTime From { get; set; }
    public DateTime To { get; set; }
    public Brush Color { get; set; }
    public string RecurrenceRule { get; set; }
    public bool IsRecursive { get; set; }
}
{% endhighlight %}
{% endtabs %}

N>You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map those properties of Meeting class with our SfSchedule control by using [ScheduleAppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="schedule" ScheduleType="Month" DataSource="{Binding Meetings}">
    <syncfusion:SfSchedule.AppointmentMapping>
        <syncfusion:ScheduleAppointmentMapping
            SubjectMapping="EventName"
            AppointmentBackgroundMapping="Color"
            StartTimeMapping="From"
            EndTimeMapping="To"
            IsRecursiveMapping="IsRecursive"
            RecurrenceRuleMapping="RecurrenceRule">
        </syncfusion:ScheduleAppointmentMapping>
    </syncfusion:SfSchedule.AppointmentMapping>
</syncfusion:SfSchedule>
{% endhighlight %}
{% highlight c# %}
// Schedule data mapping for custom appointments
ScheduleAppointmentMapping dataMapping = new ScheduleAppointmentMapping();
dataMapping.SubjectMapping = "EventName";
dataMapping.StartTimeMapping = "From";
dataMapping.EndTimeMapping = "To";
dataMapping.AppointmentBackgroundMapping = "Color";
dataMapping.IsRecursiveMapping= "IsRecursive";
dataMapping.RecurrenceRuleMapping = "RecurrenceRule";
schedule.AppointmentMapping = dataMapping;
{% endhighlight %}
{% endtabs %}

You can schedule recurring meetings for daily, weekly, monthly, or yearly interval by setting `RecurrenceRule` of `Meeting` class. Create meetings of type `ObservableCollection<Meeting>` and assign those appointments collection `Meetings` to the `DataSource` property which is of `IEnumerable` type.

{% highlight c# %}
// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = new DateTime(2017, 06, 11, 10, 0, 0);
// Setting end time of an event
meeting.To = meeting.From.AddHours(2);
// Setting start time for an event
meeting.EventName = "Client Meeting";
// Setting color for an event
meeting.Color = new SolidColorBrush(Color.FromArgb(0xFf, 0xD8, 0x00, 0x73));
// Enable to generate the recurrence.
meeting.IsRecursive = true;

// Creating recurrence rule
RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
recurrenceProperties.RecurrenceType = RecurrenceType.Weekly;
recurrenceProperties.IsWeeklyTuesday = true;
recurrenceProperties.IsWeeklyWednesday = true;
recurrenceProperties.IsWeeklyThursday = true;
recurrenceProperties.RangeRecurrenceCount = 10;
recurrenceProperties.RecurrenceRule = ScheduleHelper.RRuleGenerator(recurrenceProperties, meeting.From, meeting.To);

// Setting recursive rule for an event
meeting.RecurrenceRule = recurrenceProperties.RecurrenceRule;

// Creating instance for collection of custom appointments
var Meetings = new ObservableCollection<Meeting>();
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);

// Adding custom appointments in ItemsSource of SfSchedule
schedule.ItemsSource = Meetings;
{% endhighlight %}

![WPF scheduler custom recurrence appointment](Recurrence_images/Custom-Recurrence-Appointment.jpg)

Download demo from [GitHub](https://github.com/SyncfusionExamples/wpf-scheduler-working-with-recurrence-appointment).


### How to get the Recurrence editor field values from recurrence rule?
You can get the recurrence properties from recurrence rule using the [RRuleParser](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleHelper.html#Syncfusion_UI_Xaml_Schedule_ScheduleHelper_RRuleParser_System_String_System_DateTime_) method of Scheduler.

{% tabs %}
{% highlight c# %}
DateTime dateTime = new DateTime(2018,5,7,9,0,0);
RecurrenceProperties recurrenceProperties = schedule.RRuleParser("FREQ=DAILY;INTERVAL=1;COUNT=3", dateTime);
{% endhighlight %}
{% endtabs %}

Recurrence properties retrieved from above method,

recurrenceProperties.RecurrenceType as RecurrenceType.Daily

recurrenceProperties.DailyNDays as 1

recurrenceProperties.IsDailyEveryNDays as true

recurrenceProperties.RangeRecurrenceCount as 3

### How to get the occurrences date time list of recurring appointment from recurrence rule?
Use the [GetRecurrenceDateTimeCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleHelper.html#Syncfusion_UI_Xaml_Schedule_ScheduleHelper_GetRecurrenceDateTimeCollection_System_String_System_DateTime_System_Nullable_System_DateTime__System_Nullable_System_DateTime__) feature of Scheduler to get the occurrence date time list of recurring appointment from the recurrence rule.

{% tabs %}
{% highlight c# %}
DateTime dateTime = new DateTime(2018,5,7,9,0,0);
IEnumerable<DateTime> dateCollection = schedule.GetRecurrenceDateTimeCollection("FREQ=DAILY;INTERVAL=1;COUNT=3", dateTime);
{% endhighlight %}
{% endtabs %}

Following occurrence dates can be retrieved from the given RRULE,

var date0 = 5/7/2018;

var date1 = 5/8/2018;

var date2 = 5/9/2018;

## RecursiveExceptionDates
[ScheduleAppointment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html) supports to delete any recurrence appointment which exception from the recurrence pattern appointment by adding exception dates in [RecursiveExceptionDates](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointment.html#Syncfusion_UI_Xaml_Schedule_ScheduleAppointment_RecursiveExceptionDates) collection to the schedule appointment.

{% tabs %}
{% highlight c# %}
// Create the new exception date.
var exceptionDate = new DateTime(2017, 09, 07);
var recurrenceAppointment = new ScheduleAppointment()
{
    StartTime = new DateTime(2017, 09, 01, 10, 0, 0),
    EndTime = new DateTime(2017, 09, 01, 12, 0, 0),
    Subject = "Occurs Daily",
    Color=Color.Blue
};

// Creating recurrence rule
recurrenceAppointment.RecurrenceRule = "FREQ=DAILY;COUNT=20";

// Add RecursiveExceptionDates to appointment.
recurrenceAppointment.RecursiveExceptionDates = new ObservableCollection<DateTime>()
{
    exceptionDate 
};
this.schedule.Appointments.Add(recurrenceAppointment);
{% endhighlight %}
{% endtabs %}

N> You can also update the `RecursiveExceptionDates` collection dynamically.

### Delete occurrence from recurrence pattern dynamically or add/remove exception dates to recurrence pattern dynamically
You can also delete or add deleted occurrence from the recurrence pattern appointment by adding/removing exception date from the `RecursiveExceptionDates` collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecursiveExceptionDates.RemoveAt(0);
recurrenceAppointment.RecursiveExceptionDates.Add(new DateTime(2017, 09, 05));
{% endhighlight %}
{% endtabs %}

### Create recurrence exceptions for custom appointment
You can add/remove the recurrence exception appointments and recurrence exception dates to the CustomAppointment, You can create a custom class Meeting(refer [DataBinding](https://help.syncfusion.com/wpf/sfschedule/adding-appointments#using-data-binding-technique)) with mandatory field RecurrenceExceptionDates.

{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents custom data properties.
/// </summary>
public class Meeting
{
    public string EventName { get; set; }
    public DateTime From { get; set; }
    public DateTime To { get; set; }
    public Brush Color { get; set; }
    public string RecurrenceRule { get; set; }
    public bool IsRecursive { get; set; }
    public ObservableCollection<DateTime> RecurrenceExceptionDates { get; set; }
}
{% endhighlight %}
{% endtabs %}

N>You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

Using [AppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_AppointmentMapping) and [ScheduleAppointmentMapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ScheduleAppointmentMapping.html) to map certain properties of the `Meeting` class with our Scheduler control.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="schedule" ScheduleType="Month" DataSource="{Binding Meetings}">
    <syncfusion:SfSchedule.AppointmentMapping>
        <syncfusion:ScheduleAppointmentMapping
            SubjectMapping="EventName"
            AppointmentBackgroundMapping="Color"
            StartTimeMapping="From"
            EndTimeMapping="To"
            IsRecursiveMapping="IsRecursive"
            RecurrenceRuleMapping = "RecurrenceRule"
            RecursiveExceptionDatesMapping="RecurrenceExceptionDates">
        </syncfusion:ScheduleAppointmentMapping>
    </syncfusion:SfSchedule.AppointmentMapping>
</syncfusion:SfSchedule>
{% endhighlight %}
{% highlight c# %}
// Schedule data mapping for custom appointments
ScheduleAppointmentMapping dataMapping = new ScheduleAppointmentMapping();
dataMapping.SubjectMapping = "EventName";
dataMapping.StartTimeMapping = "From";
dataMapping.EndTimeMapping = "To";
dataMapping.IsRecursiveMapping="IsRecursive";
dataMapping.RecurrenceRuleMapping = "RecurrenceRule";
dataMapping.RecursiveExceptionDatesMapping = "RecurrenceExceptionDates";
schedule.AppointmentMapping = dataMapping;

ObservableCollection<Meeting> Meetings = new ObservableCollection<Meeting>();

// Create the new exception date.
var exceptionDate = new DateTime(2017, 09, 07);
var recurrenceAppointment = new Meeting()
{
    From = new DateTime(2017, 09, 01, 10, 0, 0),
    To = new DateTime(2017, 09, 01, 12, 0, 0),
    EventName = "Occurs Daily",
    IsRecursive = true,
    Color = new SolidColorBrush(Color.FromArgb(0xFf, 0xD8, 0x00, 0x73)),
    RecurrenceExceptionDates = new ObservableCollection<DateTime>()
    {
        exceptionDate
    }
};

// Creating recurrence rule
recurrenceAppointment.RecurrenceRule = "FREQ=DAILY;COUNT=20";

Meetings.Add(recurrenceAppointment);
this.schedule.ItemsSource = Meetings;

{% endhighlight %}
{%endtabs%}

![WPF scheduler recurrence exceptiondate](Recurrence_images/Recurrence-with-RecursiveExceptionDate.jpg)

Download demo from [GitHub](https://github.com/SyncfusionExamples/wpf-scheduler-adding-recurrence-exception-dates).

