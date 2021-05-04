---
layout: post
title: Resources in WPF Wizard Control control | Syncfusion
description: Learn here all about Resources support in Syncfusion WPF Schedule (Classic) control and more.
platform: wpf
control: SfSchedule
documentation: ug
---

# Resources in WPF Schedule (Classic)

The Scheduler allows to define resources that can be assigned to appointments. Resources let you associate additional information with your appointments. The schedule can group appointments based on the resources associated with them. Appointments will be grouped based on the resource associated with them only when both the [Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Resource) and [ScheduleResourceTypeCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleResourceTypeCollection) properties are set, and also when the value set for a `Resource` matches with any types specified in the `ScheduleResourceTypeCollection` property.
For example, end user can create appointments for different doctors.

{% tabs %}
{% highlight xaml %}
<Schedule:SfSchedule Name="Schedule1" ScheduleType="Week" Background="WhiteSmoke" Resource="Doctors" >
    <Schedule:SfSchedule.ScheduleResourceTypeCollection >
        <Schedule:ResourceType TypeName="Doctors">
            <Schedule:Resource   DisplayName="Dr.Jacob John, M.D " ResourceName="Dr.Jacob"/>
            <Schedule:Resource  DisplayName="Dr.Darsy Mascio, M.D" ResourceName="Dr.Darsy"/>
        </Schedule:ResourceType>
    </Schedule:SfSchedule.ScheduleResourceTypeCollection>
</Schedule:SfSchedule>
{% endhighlight  %}
{% highlight c# %}
ScheduleAppointment app = new ScheduleAppointment() { StartTime = currentDate, EndTime = currentDate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[m % 3] };
app.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Jacob", TypeName = "Doctors" });
ScheduleAppointment app1 = new ScheduleAppointment() { StartTime = nextDate, EndTime = nextDate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[(m + 2) % 3] };
app1.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Darsy", TypeName = "Doctors" });
Schedule1.Appointments.Add(app);
Schedule1.Appointments.Add(app1);
{% endhighlight  %}
{% endtabs %}

![WPF Scheduler workweek view with resource](Resources_images/workweek-view-with-resources.jpeg)

![WPF Scheduler month view with resource](Resources_images/month-view-with-resources.jpeg)

![WPF Scheduler timeline view with resource](Resources_images/timeline-view-with-resources.jpeg)

## Creating Resource for Schedule

Let's see the steps to add resources in Scheduler.

The first step is set the [Resource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Resource) in Scheduler

{% tabs %}
{% highlight xaml %}

<schedule:SfSchedule  Resource="Doctors" >
    ...
</schedule:SfSchedule>
{% endhighlight  %}
{% endtabs %}

After this, we need to create a [ScheduleResourceTypeCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleResourceTypeCollection), to assign the [ResourceType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ResourceType.html):

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule Resource="Doctors"  >
    ...
    <schedule:SfSchedule.ScheduleResourceTypeCollection>
        ...
    </schedule:SfSchedule.ScheduleResourceTypeCollection>
</schedule:SfSchedule>
{% endhighlight  %}
{% endtabs %}


## Adding ResourceType to a resource collection

After Creating the `ScheduleResourceTypeCollection` add the [ResourceType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.ResourceType.html), here we create the example for `ResourceType` as Doctors.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule  Resource="Doctors" >
    <schedule:SfSchedule.ScheduleResourceTypeCollection >
        <schedule:ResourceType TypeName="Doctors">
        . . .
        </schedule:ResourceType>
    </schedule:SfSchedule.ScheduleResourceTypeCollection>
</schedule:SfSchedule>
{% endhighlight  %}
{% endtabs %}

## Adding a Resource to a ResourceType 

The next step is create and assign resources to `ResourceType`.

{% tabs %}
{% highlight xaml  %}
<schedule:SfSchedule  Resource="Doctors" >
    <schedule:SfSchedule.ScheduleResourceTypeCollection >
        <schedule:ResourceType TypeName="Doctors">
            <schedule:Resource   DisplayName="Dr.Jacob John, M.D " ResourceName="Dr.Jacob"/>
            <schedule:Resource  DisplayName="Dr.Darsy Mascio, M.D" ResourceName="Dr.Darsy"/>
         </schedule:ResourceType>
     </schedule:SfSchedule.ScheduleResourceTypeCollection>
</schedule:SfSchedule>
{% endhighlight  %}
{% endtabs %}

## Creating appointments by specifying the resource

You can add an appointments to group of added resources.

{% tabs %}
{% highlight c# %}
ScheduleAppointment app = new ScheduleAppointment() { StartTime = currentDate, EndTime = currentDate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[m % 3] };
app.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Jacob", TypeName = "Doctors" });
ScheduleAppointment app1 = new ScheduleAppointment() { StartTime = nextDate, EndTime = nextDate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[(m + 2) % 3] };
app1.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Darsy", TypeName = "Doctors" });
Schedule1.Appointments.Add(app);
Schedule1.Appointments.Add(app1);
{% endhighlight  %}
{% endtabs %}

## Adding Resources in code behind

Refer to the following code to add a resources in the code behind

{% tabs %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Week;
schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;
ResourceType resourceType = new ResourceType { TypeName = "Doctor" };
resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Jacob", ResourceName = "Dr.Jacob", });
resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Darsy", ResourceName = "Dr.Darsy" });
schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };
schedule.Resource = "Doctor";
this.grid.Children.Add(schedule);
{% endhighlight %}
{% endtabs %}

## SubResource Support

This feature enables users to view appointments based on their subcategory only in day and week views. Using this feature, the end user can group appointments under various subcategories (resources). 

### DayHeaderOrder property

[DayHeaderOrder](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_DayHeaderOrder) property is used to set the order by which resources have to be displayed

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
SubResourceType</td><td>
Gets or sets the ResourceType value which is a SubResource type of its parent Resource type.</td></tr>
</table>

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule1" ScheduleType="Week"
                     Resource="Hospital" DayHeaderOrder="OrderByDate">
    <schedule:SfSchedule.ScheduleResourceTypeCollection>
         <schedule:ResourceType TypeName="Hospital">
             <schedule:ResourceType.ResourceCollection>
                  <schedule:Resource DisplayName="Apollo Hospital"ResourceName="ApolloHospital"/>
                  <schedule:Resource DisplayName="Malar Hospital"ResourceName="MalarHospital"/>
              </schedule:ResourceType.ResourceCollection>
              <schedule:ResourceType.SubResourceType>
                   <schedule:ResourceType TypeName="Department">
                         <schedule:ResourceType.ResourceCollection>
                               <schedule:Resource DisplayName="Eye Department" ResourceName="Eye"/>
                               <schedule:Resource DisplayName="Heart Department" ResourceName="Heart"/>
                         </schedule:ResourceType.ResourceCollection>
                    </schedule:ResourceType>
              </schedule:ResourceType.SubResourceType>
         </schedule:ResourceType>
    </schedule:SfSchedule.ScheduleResourceTypeCollection>
</schedule:SfSchedule>
{% endhighlight  %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Week;
schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;
ResourceType resourceType = new ResourceType { TypeName = "Hospital" };
ResourceType subResourceType = new ResourceType { TypeName = "Department" };
resourceType.ResourceCollection.Add(new Resource { DisplayName = "Apollo Hospital", ResourceName = "ApolloHospital", });
resourceType.ResourceCollection.Add(new Resource { DisplayName = "Malar Hospital", ResourceName = "MalarHospital" });
subResourceType.ResourceCollection.Add(new Resource { DisplayName = "Eye Department", ResourceName = "Eye" });
subResourceType.ResourceCollection.Add(new Resource { DisplayName = "Heart Department", ResourceName = "Heart" });
schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };
schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { subResourceType };
schedule.Resource = "Hospital";
schedule.Resource = "Department";
this.grid.Children.Add(schedule);
{% endhighlight  %}
{% endtabs %}

![WPF Scheduler with subresources](Resources_images/subresources.png)

## N Number of Resources in Day View

This feature supports to display `N` number of resources in the Schedule view. You can achieve this by specifying the count of resources that needs to be displayed per view. This support is offered for `Day` view alone.

This support can be enabled by using property [DayViewColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_DayViewColumnCount) in `SfSchedule`. By default, its value is “zero”.

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
DayViewColumnCount</td><td>
int</td><td>
Gets or sets a value to specify the number of resources that need to be shown in the view.</td></tr>
</table>

### Example:

In the following code example, [DayViewColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_DayViewColumnCount) is “two”, so the Scheduler displays two resources in the view. This count is maintained while scrolling to view the other resources.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="Schedule" ScheduleType="Day"
                       Resource="Doctors" DayViewColumnCount="2">
    <syncfusion:SfSchedule.ScheduleResourceTypeCollection>
        <syncfusion:ResourceType TypeName="Doctors">
            <syncfusion:Resource ResourceName="Res1" DisplayName="Heart Treatments"/>
            <syncfusion:Resource ResourceName="Res2" DisplayName="Cancer Treatments"/>
            <syncfusion:Resource ResourceName="Res3" DisplayName="Diabetic Treatments"/>
            <syncfusion:Resource ResourceName="Res4" DisplayName="Eye Treatments"/>
            <syncfusion:Resource ResourceName="Res5" DisplayName="Psychology Treatments"/>
            <syncfusion:Resource ResourceName="Res6" DisplayName="Dermatology Treatments"/>
        </syncfusion:ResourceType>
    </syncfusion:SfSchedule.ScheduleResourceTypeCollection>
</syncfusion:SfSchedule>
{% endhighlight  %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule();
schedule.ScheduleType = ScheduleType.Day;
schedule.DayViewColumnCount = 0;
ResourceType resourceType = new ResourceType { TypeName = "Doctors" };
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res1", DisplayName = "Heart Treatments" });
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res2", DisplayName = "Cancer Treatments" });
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res3", DisplayName = "Diabetic Treatments" });
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res4", DisplayName = "Eye Treatments" });
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res5", DisplayName = "Psychology Treatments" });
resourceType.ResourceCollection.Add(new Resource { ResourceName = "Res6", DisplayName = "Dermatology Treatments" });
schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };
schedule.Resource = "Doctors";
this.grid.Children.Add(schedule); 
{% endhighlight  %}
{% endtabs %}

The following screenshot shows a view with default value of `DayViewColumnCount` property set to “Zero”.


![WPF Scheduler dayviewcolumnt with default value](Resources_images/default-value-of-dayviewcolumncount.png)

The following screenshot shows a view with default value of `DayViewColumnCount` property set to “Two”.

![WPF Scheduler dayviewcolumnt with custom value](Resources_images/dayviewcolumncount-settings.png)