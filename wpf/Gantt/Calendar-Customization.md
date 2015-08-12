---
layout: post
title: Calendar-Customization
description: calendar customization
platform: wpf
control: Gantt
documentation: ug
---

# Calendar Customization

This feature allows you to set your own schedule for the entire project. Using this feature you can customize the calendar as per the organization’s requirement. Currently Essential Gantt provides  the following properties of the schedule to customize the calendar:

* Week Begins On—Gets or sets the starting day of a week in the Schedule
* Fiscal Year Begin On—Gets or sets the starting month of a Fiscal Year
* Is FY Numbering Enabled—Gets or sets the FY Numbering to true or false in the Schedule
* Default Start Time—Gets or sets the task starting time of the day.
* Default End Time—Gets or sets the task ending time of the day.

Currently Default Start Time and Default End Time will reflect only in the Chart Background Panel. 

## Use Case Scenarios

You can use this feature when you want to change the schedule as needed. For example, if April to March is your financial year, you can set this as your fiscal year and schedule the tasks accordingly. 

You can also use this to schedule the works that have different week cycle. For example if your organization follows the week cycle from Wednesday to Tuesday, you can achieve this using calendar Customization feature.

## Properties

_Properties_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
WeekBeginsOn</td><td>
Gets or sets the starting day of a week in the project schedule. By default it is set to Sunday. </td><td>
DependencyProperty </td><td>
Enum</td><td>
N/A</td></tr>
<tr>
<td>
FiscalYearBeginsOn</td><td>
Gets or sets the starting month of a fiscal year. By default it is set to January</td><td>
DependencyProperty</td><td>
Enum</td><td>
N/A</td></tr>
<tr>
<td>
IsFYNumberingEnabled</td><td>
Gets or sets the Fiscal Year Numbering. If this property is changed, it will be reflected in the schedule.By default FY Numbering is set to false.</td><td>
Dependency Property</td><td>
bool</td><td>
N/A</td></tr>
<tr>
<td>
DefaultStartTime</td><td>
Gets or sets the task starting time in a day. This is based on the {{ '_GanttTime_' | markdownify }} class of the Gantt control.By default this is set to 9.00 AM</td><td>
Dependency Property</td><td>
GanttTime</td><td>
N/A</td></tr>
<tr>
<td>
DefaultEndTime</td><td>
Gets or sets the task ending time in a day. This is based on the {{ '_GanttTime_' | markdownify }} class of the Gantt control.By default this is set to 6.00 PM</td><td>
Dependency Property</td><td>
GanttTime</td><td>
N/A</td></tr>
</table>


## Adding Calendar Customization to an Application 

Define the value to weekdays, months, FY Numbering, default start time and default end time as required and assign it to the appropriate APIs in the Gantt.

The following code illustrates adding Calendar Customization to an Application:


{% highlight xml  %}
[XAML]



  <sync:GanttControl Grid.Row="1"  x:Name="Gantt">

                <sync:GanttControl.TaskAttributeMapping>

                    <sync:TaskAttributeMapping TaskIdMapping="Id"

                                            TaskNameMapping="Name"

                                            StartDateMapping="StDate" 

                                            ChildMapping="ChildTask"

                                            FinishDateMapping="EndDate"

                                            DurationMapping="Duration"                                            

                                            ProgressMapping="Complete"

                                            PredecessorMapping="Predecessor">

                    </sync:TaskAttributeMapping>

                </sync:GanttControl.TaskAttributeMapping>

            </sync:GanttControl>           



{% endhighlight  %}
{% highlight c# %}

[C#]



// To Set Week BeginsOn 

 Gantt.WeekBeginsOn = DayOfWeek.Wednesday;

// To Set Fiscal Year starting Month

 Gantt.FiscalYearBeginsOn = Month.July;

// To Set FY Numbering

 Gantt.IsFYNumberingEndbled = true;

// To Set Default Start Time

 Gantt.DefaultStartTime = new GanttTime() { Hour = 10};

// To Set Default End Time

Gantt.DefaultEndTime = new GanttTime() { Hour = 6};


{% endhighlight %}
The following image shows Customized Calender:



![](Calendar-Customization_images/Calendar-Customization_img1.png)



_Customized Calender_

### Samples Link

To view samples:

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
1. Click Run Samples for WPF under User Interface Edition panel.
2. Select Gantt.
3. Expand the Interactive Features item in the Sample Browser.
4. Choose the Calendar Customization sample to launch.



