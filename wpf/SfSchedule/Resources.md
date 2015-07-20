---
layout: post
title: Resources
description: resources
platform: wpf
control: SfSchedule
documentation: ug
---

# Resources

The Schedule control allows you to define resources that can be assigned to appointments. Resources let you associate additional information with your appointments. The schedule can group appointments based on the resources associated with them. For example, you can create appointments for different doctors.

Appointments will be grouped based on the resource associated with them only when both the Resource and ScheduleResourceTypeCollection properties are set, and also when the Value set for a Resource matches with any types specified in the ScheduleResourceTypeCollection property.

[XAML] 



&lt;Schedule:SfSchedule Name="Schedule1" ScheduleType="Week" Background="WhiteSmoke" Resource="Doctors" &gt;

    &lt;Schedule:SfSchedule.ScheduleResourceTypeCollection &gt;

        &lt;Schedule:ResourceType TypeName="Doctors"&gt;

            &lt;Schedule:Resource   DisplayName="Dr.Jacob John, M.D " ResourceName="Dr.Jacob"/&gt;

            &lt;Schedule:Resource  DisplayName="Dr.Darsy Mascio, M.D" ResourceName="Dr.Darsy"/&gt;

        &lt;/Schedule:ResourceType&gt;

    &lt;/Schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

&lt;/Schedule:SfSchedule&gt;





[C#] 



ScheduleAppointment app = new ScheduleAppointment() { StartTime = currentdate, EndTime = currentdate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[m % 3] };

            app.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Jacob", TypeName = "Doctors" });



            ScheduleAppointment app1 = new ScheduleAppointment() { StartTime = nextdate, EndTime = nextdate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[(m + 2) % 3] };

            app1.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Darsy", TypeName = "Doctors" });

            Schedule1.Appointments.Add(app);

            Schedule1.Appointments.Add(app1);





{ ![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_28.jpg](Resources_images/Resources_img1.jpeg) | markdownify }
{:.image }






{ ![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_29.jpg](Resources_images/Resources_img2.jpeg) | markdownify }
{:.image }






{ ![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_30.jpg](Resources_images/Resources_img3.jpeg) | markdownify }
{:.image }




## Creating ResourceTypesCollection for Schedule

_Let's_ see the steps to _add Resources in your schedule._

_The first step is set the ResourceTypesCollection in schedule_ 

[XAML]

     &lt;schedule:SfSchedule  Resource="Doctors" &gt;

         ...

        &lt;/schedule:SfSchedule&gt;





After this, we need to create a ResourceTypeCollection, to assign the ResourceType:

[XAML]

      &lt;schedule:SfSchedule Resource="Doctors"  &gt;

               ...

            &lt;schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

               ...

            &lt;/schedule:SfSchedule.ScheduleResourceTypeCollection&gt;



        &lt;/schedule:SfSchedule&gt;





## Adding ResourceType to a ResourceTypeCollection

After Creating the ResourceTypeCollection add the ResourecType, here we create the example for ResourceType as Doctors.

[XAML]

      &lt;schedule:SfSchedule  Resource="Doctors" &gt;

            &lt;schedule:SfSchedule.ScheduleResourceTypeCollection &gt;

                &lt;schedule:ResourceType TypeName="Doctors"&gt;

                    . . .

                &lt;/schedule:ResourceType&gt;

            &lt;/schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

        &lt;/schedule:SfSchedule&gt;





## Adding a Resource to a ResourceType 

The next step is create and assign Resources to ResourceType.

[XAML]

    &lt;schedule:SfSchedule  Resource="Doctors" &gt;

            &lt;schedule:SfSchedule.ScheduleResourceTypeCollection &gt;

                &lt;schedule:ResourceType TypeName="Doctors"&gt;

                    &lt;schedule:Resource   DisplayName="Dr.Jacob John, M.D " ResourceName="Dr.Jacob"/&gt;

                    &lt;schedule:Resource  DisplayName="Dr.Darsy Mascio, M.D" ResourceName="Dr.Darsy"/&gt;

                &lt;/schedule:ResourceType&gt;

            &lt;/schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

        &lt;/schedule:SfSchedule&gt;





## Creating appointments by specifying the resource

You can add an appointments to group of added resources.

[XAML]



ScheduleAppointment app = new ScheduleAppointment() { StartTime = currentdate, EndTime = currentdate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[m % 3] };

            app.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Jacob", TypeName = "Doctors" });



            ScheduleAppointment app1 = new ScheduleAppointment() { StartTime = nextdate, EndTime = nextdate.AddHours(ran.Next(0, 2)), Subject = subject[count % subject.Length], Location = "Chennai", AppointmentBackground = brush[(m + 2) % 3] };

            app1.ResourceCollection.Add(new Resource() { ResourceName ="Dr.Darsy", TypeName = "Doctors" });

            Schedule1.Appointments.Add(app);

            Schedule1.Appointments.Add(app1);





## Adding Resources in code behind

Refer to the following code to add a Resources in the code behind

[C#]

          SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;

            ResourceType resourceType = new ResourceType { TypeName = "Doctor" };

            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Jacob", ResourceName = "Dr.Jacob", });

            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Darsy", ResourceName = "Dr.Darsy" });

            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };

            schedule.Resource = "Doctor";

            this.grid.Children.Add(schedule);





## Subresource Support

This feature enables users to view appointments based on their subcategory only in day and week views. Using this feature, the end user can group appointments under various subcategories (resources). 

DayHeaderOrder property:

DayHeaderOrder property is used to set the order by which resources have to be displayed

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
SubResourceType</td><td>
Gets or sets the ResourceType value which is a subresource type of its parent Resource type.</td></tr>
</table>


[XAML]



        <schedule:SfSchedule x:Name="schedule1" ScheduleType="Week"

                             Resource="Hospital" DayHeaderOrder="OrderByDate">

            &lt;schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

                &lt;schedule:ResourceType TypeName="Hospital"&gt;

                    &lt;schedule:ResourceType.ResourceCollection&gt;

                        &lt;schedule:Resource DisplayName="Apollo Hospital"ResourceName="ApolloHospital"/&gt;

                        &lt;schedule:Resource DisplayName="Malar Hospital"ResourceName="MalarHospital"/&gt;

                    &lt;/schedule:ResourceType.ResourceCollection&gt;

                    &lt;schedule:ResourceType.SubResourceType&gt;

                        &lt;schedule:ResourceType TypeName="Department"&gt;

                            &lt;schedule:ResourceType.ResourceCollection&gt;

                                &lt;schedule:Resource DisplayName="Eye Department" ResourceName="Eye"/&gt;

                                &lt;schedule:Resource DisplayName="Heart Department" ResourceName="Heart"/&gt;

                            &lt;/schedule:ResourceType.ResourceCollection&gt;

                        &lt;/schedule:ResourceType&gt;

                    &lt;/schedule:ResourceType.SubResourceType&gt;

                &lt;/schedule:ResourceType&gt;

            &lt;/schedule:SfSchedule.ScheduleResourceTypeCollection&gt;

        &lt;/schedule:SfSchedule&gt;





[C#]

            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;

            ResourceType resourceType = new ResourceType { TypeName = "Hospital" };

            ResourceType subresourceType = new ResourceType { TypeName = "Department" };

            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Apollo Hospital", ResourceName = "ApolloHospital", });

            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Malar Hospital", ResourceName = "MalarHospital" });

            subresourceType.ResourceCollection.Add(new Resource { DisplayName = "Eye Department", ResourceName = "Eye" });

            subresourceType.ResourceCollection.Add(new Resource { DisplayName = "Heart Department", ResourceName = "Heart" });

            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };

            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { subresourceType };

            schedule.Resource = "Hospital";

            schedule.Resource = "Department";

            this.grid.Children.Add(schedule);





{ ![](Resources_images/Resources_img4.png) | markdownify }
{:.image }




## N Number of Resources in Day View

This feature supports to display ‘N’ number of resources in the Schedule view. You can achieve this by specifying the count of resources that needs to be displayed per view. This support is offered for Day view alone.

This support can be enabled by using property “DayViewColumnCount” in SfSchedule. By default, its value is “zero”.

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
DayViewColumnCount</td><td>
int</td><td>
Gets or sets a value to specify the number of resources that need to be shown in the view.</td></tr>
</table>
Example:

In the following code example, “DayViewColumnCount” is “two”, so the Schedule displays two resources in the view. This count is maintained while scrolling to view the other resources.



[XAML]



<syncfusion:SfSchedule x:Name="Schedule" ScheduleType="Day"

                       Resource="Doctors" DayViewColumnCount="2">

    &lt;syncfusion:SfSchedule.ScheduleResourceTypeCollection&gt;

        &lt;syncfusion:ResourceType TypeName="Doctors"&gt;

            &lt;syncfusion:Resource ResourceName="Res1" DisplayName="Heart Treatments"/&gt;

            &lt;syncfusion:Resource ResourceName="Res2" DisplayName="Cancer Treatments"/&gt;

            &lt;syncfusion:Resource ResourceName="Res3" DisplayName="Diabetic Treatments"/&gt;

            &lt;syncfusion:Resource ResourceName="Res4" DisplayName="Eye Treatments"/&gt;

            &lt;syncfusion:Resource ResourceName="Res5" DisplayName="Psychology Treatments"/&gt;

            &lt;syncfusion:Resource ResourceName="Res6" DisplayName="Dermatology Treatments"/&gt;

        &lt;/syncfusion:ResourceType&gt;

    &lt;/syncfusion:SfSchedule.ScheduleResourceTypeCollection&gt;

&lt;/syncfusion:SfSchedule&gt;





[C#]

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

The following screenshot shows a view with default value of DayViewColumnCount property set to “Zero”.

<table>
<tr>
<td>
![](Resources_images/Resources_img5.png)
{:.image }
The following screenshot shows a view with default value of DayViewColumnCount property set to “Two”.</td></tr>
<tr>
<td>
![](Resources_images/Resources_img6.png)
{:.image }
</td></tr>
</table>


