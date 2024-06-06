---
layout: post
title: Tooltip in WPF Scheduler control | Syncfusion
description: Learn here all about Tooltip support in Syncfusion WPF Scheduler (SfScheduler) control and more.
platform: wpf
control: SfScheduler
documentation: ug
---

# Tooltip in WPF Scheduler (SfScheduler)

The tooltip provides information when hovering over or selecting items in the interactive appointments, displaying details about each appointment.

## Enable tooltip

To enable the tooltip for the Scheduler control, utilize the `EnableTooltip` property of SfScheduler. By default, the value of `EnableTooltip` is set to false. To provide users with additional information or context about appointments, simply set this property to true.

{% tabs %}
{% highlight xaml %}
      <syncfusion:SfScheduler x:Name="Schedule"
                EnableToolTip="True">
      </syncfusion:SfScheduler>
{% endhighlight %}
{% highlight c# %}
  SfScheduler Schedule = new SfScheduler();      
  Schedule.EnableToolTip = true;
  this.Content = Schedule;
{% endhighlight %}
{% endtabs %}

## Customize tooltip appearance using DataTemplate

You can customize the tooltip appearance by using the `ToolTipTemplate` property in the `SfScheduler`.

The following code example shows the usage of DataTemplate.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"
                EnableToolTip="True">
    <syncfusion:SfScheduler.ToolTipTemplate>
     <DataTemplate>
    <Border x:Name="PART_ToolTipBorder"
        BorderBrush="White"
        Background="Black"
        CornerRadius="0"
        VerticalAlignment="Stretch"
        HorizontalAlignment="Stretch"
        BorderThickness="1"
        Padding="5">
         <StackPanel>
             <TextBlock x:Name="PART_AppointmentTextBlock"
                        Text="{Binding Subject}"
                        Foreground="White"
                        FontSize="12"
                        TextWrapping="Wrap"
                        TextTrimming="CharacterEllipsis" />
         </StackPanel>
     </Border>
     </DataTemplate>
    </syncfusion:SfScheduler.ToolTipTemplate>
</syncfusion:SfScheduler>

{% endhighlight %}
{% highlight c# %}
  SfScheduler Schedule = new SfScheduler();      
  Schedule.EnableToolTip = true;
  this.Content = Schedule;
{% endhighlight %}
{% endtabs %}

