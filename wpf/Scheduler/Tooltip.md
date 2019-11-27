---
layout: post
title: Tooltip| SfSchedule | Wpf | Syncfusion
description: Learn about ToolTip support and its customization in Syncfusion WPF SfSchedule control and more details.
platform: wpf
control: SfSchedule
documentation: ug
---

# Tooltip

Appointment Tooltip is used to view the details of the appointment in the user's required design and its visibility can be enabled by setting `AppointmentTooltipVisibility` as Visible. This tooltip will be displayed when the mouse is over the appointments whereas in touch device it will be displayed on holding over the appointments. The schedule appointment tooltip will be displayed only when the AppointmentTooltipTemplate property is set. The AppointmentTooltipTemplate is of type ControlTemplate.
{% tabs %}
{% highlight html %}




<Schedule:SfSchedule ScheduleType="Week" Background="WhiteSmoke" AppointmentTooltipVisibility="Visible">

<Schedule:SfSchedule.AppointmentTooltipTemplate>

<ControlTemplate>

<Grid Background="WhiteSmoke"  Height="90" Width="210">

<Grid.RowDefinitions>

<RowDefinition/>

<RowDefinition Height="10"/>

<RowDefinition/>

<RowDefinition />

</Grid.RowDefinitions>

<Border Grid.Row="0" Background="{Binding AppointmentBackground}">

<TextBlock Margin="10,5,0,0"  FontSize="16" Text="{Binding Subject}" Grid.Row="0"/>

</Border>

<TextBlock FontSize="16" FontWeight="Bold" FontStyle="Italic" Margin="20,0,0,0" Text="Location: " Grid.Row="2"/>

<TextBlock FontSize="16" Margin="20,0,0,0" Text="{Binding Location}" Grid.Row="3"/>

</Grid>

</ControlTemplate>

</Schedule:SfSchedule.AppointmentTooltipTemplate>

</Schedule:SfSchedule>


{% endhighlight  %}
{% highlight c# %}




 schedule.Appointments.Add(new ScheduleAppointment()

{

StartTime = DateTime.Now.Date.AddHours(9),

EndTime = DateTime.Now.Date.AddHours(11),

Subject = "Meet the doctor",

Location = "Hutchison Road"

});

{% endhighlight  %}
{% endtabs %}

![Appointment tooltip](Tooltip_images/Tooltip_img1.jpeg)



