---
layout: post
title: Appointment Template Customization| SfSchedule | Wpf | Syncfusion
description: appointment template customization
platform: wpf
control: SfSchedule
documentation: ug
---

# Appointment Template Customization

The default appearance of the Appointment can be customized by using the AppointmentTemplate property. The AppointmentTemplate is a ControlTemplate type, used to customize or override the default template of the Appointments.
{% tabs %}
{% highlight xaml %}

<Schedule:SfSchedule>

<Schedule:SfSchedule.AppointmentTemplate>

<ControlTemplate>

<Grid>

<Rectangle Fill="{Binding AppointmentBackground}"/>

<Grid>

<Grid.RowDefinitions>

<RowDefinition Height="0.25*"/>

<RowDefinition Height="0.75*"/>

</Grid.RowDefinitions>

<Grid.ColumnDefinitions>

<ColumnDefinition/><ColumnDefinition/>

</Grid.ColumnDefinitions>

<TextBlock Margin="10,2,0,0" Text="{Binding Subject}" Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="2" HorizontalAlignment="Left" VerticalAlignment="Center" FontSize="20" Foreground="White" FontWeight="Light" FontFamily="Segoe UI"/>

<Image Source="../Assets/Team.png" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Center" Stretch="Fill" />

<TextBlock Text="{Binding StartTime}" Grid.Row="1" Grid.Column="1" HorizontalAlignment="Left" VerticalAlignment="Center" FontSize="20" Foreground="White" FontWeight="Light" FontFamily="Segoe UI" TextWrapping="NoWrap"/>

</Grid></Grid>

</ControlTemplate>

</Schedule:SfSchedule.AppointmentTemplate>

</Schedule:SfSchedule>  

{% endhighlight %}
{% highlight c# %}


        schedule.Appointments.Add(new ScheduleAppointment()

            {

                StartTime = DateTime.Now.Date.AddHours(9),

                EndTime = DateTime.Now.Date.AddHours(11),

                Subject = "Meet the doctor",

                Location = "Hutchison road",

            });


{% endhighlight  %}
{% endtabs %}



![](Appointment-Template-Customization_images/Appointment-Template-Customization_img1.png)





