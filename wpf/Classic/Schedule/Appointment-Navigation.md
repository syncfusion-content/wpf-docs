---
layout: post
title: Appointment-Navigation in WPF Wizard Control control | Syncfusion
description: Learn here all about Appointment-Navigation support in Syncfusion WPF Schedule (Classic) control and more.
platform: wpf
control: SfSchedule
documentation: ug
---

# Appointment-Navigation in WPF Schedule (Classic)

When there is no appointment in the current view, we can navigate to view the previous appointment or next appointment from the current view. This can be enabled or disabled using the property ShowNavigationTap. The default value of ShowNavigationTap property is False.  
{% tabs %}
{% highlight html %}



<Schedule:SfSchedule x:Name="schedule" ScheduleType="Week"

ShowAppointmentNavigationButtons ="True"  /> 


{% endhighlight  %}
{% highlight c# %}





SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Week;

schedule.ShowAppointmentNavigationButtons = true;

this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}

![AppointmentNavigation](Appointment-Navigation_images/Appointment-Navigation_img1.png)



## PreviousNavigationButtonTemplate 

Previous appointment navigation button can be customized by PreviousNavigationButtonTemplate property.
{% highlight c# %}



<Schedule:SfSchedule x:Name="schedule" ScheduleType="Day" ShowAppointmentNavigationButtons="True">

<Schedule:SfSchedule.PreviousNavigationButtonTemplate>

<DataTemplate>

<Border Height="200" Width="50" Background="Red"/>                </DataTemplate>

</Schedule:SfSchedule.PreviousNavigationButtonTemplate>

</Schedule:SfSchedule>

{% endhighlight  %}

![AppointmentNavigationImage2](Appointment-Navigation_images/Appointment-Navigation_img2.png)



## NextNavigationButtonTemplate

By using the NextNavigationButtonTemplate property the next appointment navigation button can be customized to view the next appointment.
{% highlight html %}



<Schedule:SfSchedule x:Name="schedule" ScheduleType="Day" ShowAppointmentNavigationButtons="True">

<Schedule:SfSchedule.NextNavigationButtonTemplate>                <DataTemplate>

<Border Height="200" Width="50" Background="Red"/>                                </DataTemplate>

</Schedule:SfSchedule.NextNavigationButtonTemplate>

</Schedule:SfSchedule>

{% endhighlight  %}



![AppointmentNavigationImage3](Appointment-Navigation_images/Appointment-Navigation_img3.png)





