---
layout: post
title: Appointment-Navigation
description: appointment navigation
platform: wpf
control: SfSchedule
documentation: ug
---

# Appointment Navigation

When there is no appointment in the current view, we can navigate to view the previous appointment or next appointment from the current view. This can be enabled or disabled using the property ShowNavigationTap. The default value of ShowNavigationTap property is False.  

[XAML]



     <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week"

                          ShowAppointmentNavigationButtons ="True"  /> 





[C#]



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.ShowAppointmentNavigationButtons = true;

            this.grid.Children.Add(schedule);





{{ '![](Appointment-Navigation_images/Appointment-Navigation_img1.png)' | markdownify }}
{:.image }


PreviousNavigationButtonTemplate 

Previous appointment navigation button can be customized by PreviousNavigationButtonTemplate property.

[XAML]



            <Schedule:SfSchedule x:Name="schedule" ScheduleType="Day" ShowAppointmentNavigationButtons="True">

            <Schedule:SfSchedule.PreviousNavigationButtonTemplate>

                <DataTemplate>

<Border Height="200" Width="50" Background="Red"/>                </DataTemplate>

            </Schedule:SfSchedule.PreviousNavigationButtonTemplate>

        </Schedule:SfSchedule>



{{ '![](Appointment-Navigation_images/Appointment-Navigation_img2.png)' | markdownify }}
{:.image }


NextNavigationButtonTemplate

By using the NextNavigationButtonTemplate property the next appointment navigation button can be customized to view the next appointment.

[XAML]



            <Schedule:SfSchedule x:Name="schedule" ScheduleType="Day" ShowAppointmentNavigationButtons="True">

             <Schedule:SfSchedule.NextNavigationButtonTemplate>                <DataTemplate>

<Border Height="200" Width="50" Background="Red"/>                                </DataTemplate>

            </Schedule:SfSchedule.NextNavigationButtonTemplate>

        </Schedule:SfSchedule>





{{ '![](Appointment-Navigation_images/Appointment-Navigation_img3.png)' | markdownify }}
{:.image }




