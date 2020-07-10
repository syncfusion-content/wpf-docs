---
layout: post
title: Header in Syncfusion WPF SfScheduler| SfScheduler | Wpf | Syncfusion
description: This section explain about how to customize header height, date format and appearance of Syncfusion WPF Scheduler.. 
platform: wpf
control: SfScheduler
documentation: ug
---

# Headers in WPF scheduler (SfScheduler)
You can change the header height, date format and appearance of [SfScheduler](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler.html).

## Header height
You can change the scheduler header height by using [HeaderHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~HeaderHeight.html) property of SfScheduler. by default the header height is 50.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        HeaderHeight="100" >
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
this.Schedule.HeaderHeight = 100;
{% endhighlight %}
{% endtabs %}

![WPF Scheduler header ViewHeaderHeight](Schedule-Header_Images/HeaderHeight.png)

## Header date format
You can change the Scheduler header date format of scheduler by using the  [HeaderDateFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~HeaderDateFormat.html) property of SfScheduler. by default the header date format is `MMMM yyyy`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                        HeaderDateFormat="MMM/yyyy">   
</syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c#%}
this.Schedule.HeaderDateFormat = "MMM/yyyy";
{% endhighlight %}
{% endtabs %}

![WPF Scheduler header HeaderDateFormat](Schedule-Header_Images/HeaderDateFormat.png)

## Appearance

### Customize header appearance using Style
You can style Scheduler header appearance using [SchedulerHeaderControl](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SchedulerHeaderControl.html) in scheduler. You can change the background color, textStyle, and borderBrush etc. by setting style property for `SchedulerHeaderControl`.

{% tabs %}
{% highlight xaml %}
<Style TargetType="syncfusion:SchedulerHeaderControl">
    <Setter Property="Background" Value="LightCyan"/>
    <Setter Property="Foreground" Value="Red"/>
    <Setter Property="FontStyle" Value="Italic"/>
    <Setter Property="BorderBrush" Value="LightCoral"/>
    <Setter Property="BorderThickness" Value="2"/>
</Style>
{% endhighlight %}
{% endtabs %}

![WPF Scheduler header CustomizedHeader](Schedule-Header_Images/CustomizedHeader.png)

### Customize header appearance using DataTemplate
You can customize header appearance of scheduler by using [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfScheduler.WPF~Syncfusion.UI.Xaml.Scheduler.SfScheduler~HeaderTemplate.html) property of SfScheduler.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule">
    <syncfusion:SfScheduler.HeaderTemplate>
        <DataTemplate >
                <TextBlock FontStyle="Italic"
                           Foreground="Blue"
                           FontSize="25"
                           Text="{Binding}"/>
        </DataTemplate>
    </syncfusion:SfScheduler.HeaderTemplate>
</syncfusion:SfScheduler>
{% endhighlight %}
{% endtabs %}

![WPF Scheduler header HeaderTemplate](Schedule-Header_Images/HeaderTemplate.png)
