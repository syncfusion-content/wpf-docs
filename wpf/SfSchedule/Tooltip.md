---
layout: post
title: Tooltip
description: tooltip
platform: wpf
control: SfSchedule
documentation: ug
---

# Tooltip

Appointment Tooltip is used to view the details of the appointment in user required design. This tooltip will be displayed when the mouse is over the appointments whereas in touch device it will be displayed on holding over the appointments. The schedule appointment tooltip will be displayed only when the AppointmentTooltipTemplate property is set. The AppointmentTooltipTemplate is of type DataTemplate.

[XAML]



&lt;Schedule:SfSchedule ScheduleType="Week" Background="WhiteSmoke" &gt;

    &lt;Schedule:SfSchedule.AppointmentTooltipTemplate&gt;

        &lt;DataTemplate&gt;

            &lt;Grid Background="WhiteSmoke"  Height="90" Width="210"&gt;

                &lt;Grid.RowDefinitions&gt;

                    &lt;RowDefinition/&gt;

                    &lt;RowDefinition Height="10"/&gt;

                    &lt;RowDefinition/&gt;

                    &lt;RowDefinition /&gt;

                &lt;/Grid.RowDefinitions&gt;

                &lt;Border Grid.Row="0" Background="{Binding AppointmentBackground}"&gt;

                    &lt;TextBlock Margin="10,5,0,0"  FontSize="16" Text="{Binding Subject}" Grid.Row="0"/&gt;

                &lt;/Border&gt;

                &lt;TextBlock FontSize="16" FontWeight="Bold" FontStyle="Italic" Margin="20,0,0,0" Text="Location: " Grid.Row="2"/&gt;

                &lt;TextBlock FontSize="16" Margin="20,0,0,0" Text="{Binding Location}" Grid.Row="3"/&gt;

            &lt;/Grid&gt;

        &lt;/DataTemplate&gt;

    &lt;/Schedule:SfSchedule.AppointmentTooltipTemplate&gt;

&lt;/Schedule:SfSchedule&gt;





[C#]

 schedule.Appointments.Add(new ScheduleAppointment()

{

StartTime = DateTime.Now.Date.AddHours(9),

EndTime = DateTime.Now.Date.AddHours(11),

Subject = "Meet the doctor",

Location = "Hutchison Road"

});



{ ![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_23.jpg](Tooltip_images/Tooltip_img1.jpeg) | markdownify }
{:.image }


