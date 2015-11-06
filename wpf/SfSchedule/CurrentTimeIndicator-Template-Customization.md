---
layout: post
title: CurrentTimeIndicator Template Customization| SfSchedule | Wpf | Syncfusion
description: currenttimeindicator template customization
platform: wpf
control: SfSchedule
documentation: ug
---

# CurrentTimeIndicator Template Customization

## CurrentTimeIndicatorVisibility 

The visibility of current time indicator enabled by using the CurrentTimeIndicatorVisibility property of SfSchedule Control.
{% tabs %}
{% highlight html %}



  <Grid Background="White" Name="grid">

     <Schedule:SfSchedule ScheduleType="Week"   CurrentTimeIndicatorVisibility="Visible">     

        </Schedule:SfSchedule>

    </Grid>


{% endhighlight  %}

{% highlight c# %}



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.CurrentTimeIndicatorVisibility = Visibility.Visible;

            this.grid.Children.Add(schedule);


{% endhighlight  %}
{% endtabs %}

![](CurrentTimeIndicator-Template-Customization_images/CurrentTimeIndicator-Template-Customization_img1.png)





![](CurrentTimeIndicator-Template-Customization_images/CurrentTimeIndicator-Template-Customization_img2.png)



## CurrentTimeIndicatorTemplate

The CurrentTimeIndicator can be customized by using the__CurrentTimeIndicatorTemplate of SfScheduleControl.
{% tabs %}
{% highlight html %}



<Grid Background="White" Name="grid">

<Schedule:SfSchedule x:Name="schedule" ScheduleType="Week" CurrentTimeIndicatorVisibility="Visible">

<Schedule:SfSchedule.CurrentTimeIndicatorTemplate>

<DataTemplate>

<Border Background="DarkGreen" Height="10" Width="100"></Border>

</DataTemplate>

</Schedule:SfSchedule.CurrentTimeIndicatorTemplate>

</Schedule:SfSchedule>        



</Grid>


{% endhighlight  %}

{% highlight c# %}



SfSchedule schedule = new SfSchedule();

schedule.ScheduleType = ScheduleType.Week;

schedule.CurrentTimeIndicatorVisibility = Visibility.Visible;

schedule.CurrentTimeIndicatorTemplate = (DataTemplate)this.Resources["CurrentTimeIndicatorTemplate"];

this.grid.Children.Add(schedule);


{% endhighlight %}
{% endtabs %}


![](CurrentTimeIndicator-Template-Customization_images/CurrentTimeIndicator-Template-Customization_img3.png)





