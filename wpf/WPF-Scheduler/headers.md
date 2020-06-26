---     
layout: post     
title: Headers | SfSchedule | WPF | Syncfusion    
description: Describes how to customize appearance of header view in Scheduler (SfSchedule) control in WPF
platform: WPF    
control: SfSchedule     
documentation: ug   
---  

# Headers in WPF Scheduler (SfSchedule)

You can customize the header of the Schedule using `HeaderStyle` and `HeaderHeight` property in schedule.

## Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% tabs %} 
{% highlight xaml %}
<syncfusion:SfScheduler x:Name="Schedule"   HeaderHeight="100"/>
{% endhighlight %} 
{% highlight c# %}
 Schedule.HeaderHeight = 100;
{% endhighlight %}
{% endtabs %} 

## Appearance

You can change the header format and style using `SchedulerHeaderControl` in scheduler.
You can change the background color, font family, font attributes and font size using properties such as `BackgroundColor`, `FontFamily`, `FontAttributes`, `FontSize`, `Foreground`, of Header using `SchedulerHeaderControl` in scheduler.

{% tabs %} 
{% highlight xaml %}
 <Window.Resources>
<Style TargetType="syncfusion:SchedulerHeaderControl">
 <Setter Property="Background" Value="Green"/>
<Setter Property="FontFamily" Value="Arial"/>
<Setter Property="Foreground" Value="Red"/>
</Style>
</Window.Resources>
{% endhighlight %}
{% endtabs %} 

![WPF SfSchedule Header Style](Headers_images/Apperance.png) 

### Customize Font Appearance

You can change the appearance of Font by setting the  [FontFamily](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderStyle~FontFamilyProperty.html) property of [HeaderStyle](https://help.syncfusion.com/xamarin/sfschedule/headers#appearance) property in Schedule.

{% tabs %} 
{% highlight xaml %}
<schedule:HeaderStyle.FontFamily>
	<OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:HeaderStyle.FontFamily>
{% endhighlight %}
{% highlight c# %}
headerStyle.FontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
{% endhighlight %}
{% endtabs %} 

![Xamarin.Forms SfSchedule Header customization](Header_images/xamarin.forms-schedule-customize-font.png) 

Refer [this](https://help.syncfusion.com/xamarin/sfschedule/monthview#custom-font-setting-in-xamarinforms-android) to configure the custom fonts in Xamarin.Forms.

## Loading Custom Headers

You can collapse the default header of schedule by setting `HeaderHeight` property of `SfSchedule` as 0. Instead you can use your own custom header for it. While navigating views in schedule, text labels available in the header will be changed based on it visible dates, so while using custom header , respective text value can be obtained from the `VisibleDatesChanged` event of `SfSchedule`.

{% tabs %}   
{% highlight c# %}
//triggering the visible dates changed event.
schedule.VisibleDatesChangedEvent += Schedule_VisibleDatesChangedEvent;

... 

private void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs args)
{
	List<DateTime> dateList = new List<DateTime>();
	dateList = (args.visibleDates);
	var headerString = String.Empty;
	var item = dateList[0];
	if (Schedule.ScheduleView == ScheduleView.DayView)
	{
		item = dateList[0];
		headerString = item.Date.ToString("MMMM, yyyy");
	}
	else
	{
		item = dateList[dateList.Count / 2];
		headerString = item.Date.ToString("MMMM, yyyy");
	}
}
{% endhighlight %}
{% endtabs %}   

You can get the complete sample for customizing the Header of Schedule [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Header_Sample-1251673941.zip)

## Header Date Format

You can customize the date format of SfSchedule Header by using [ScheduleHeaderDateFormat](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~ScheduleHeaderDateFormat.html) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleHeaderDateFormat = "LLL yy" />
{% endhighlight %}
{% highlight c# %}
//Creating instance of Schedule
SfSchedule schedule = new SfSchedule();
//Customizing date format
schedule.ScheduleHeaderDateFormat = "LLL yy";
{% endhighlight %}
{% endtabs %}

![Xamarin.Forms SfSchedule Header DateFormat](Header_images/xamarin.forms-schedule-date-format.png)

## Header Tapped Event

You can handle single tap action of Header by using [HeaderTapped](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~HeaderTapped_EV.html) event of `SfSchedule`. This event will be triggered when the Header is Tapped. This event contains [HeaderTappedEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderTappedEventArgs.html) argument which holds [DateTime](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderTappedEventArgs~DateTime.html) details in it.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" HeaderTapped="Handle_HeaderTapped" />
{% endhighlight %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.HeaderTapped += Handle_HeaderTapped;
{% endhighlight %}
{% endtabs %}

{% tabs %}   
{% highlight c# %}
private void Handle_HeaderTapped(object sender, HeaderTappedEventArgs e)
{
    var dateTime = e.DateTime;
}
{% endhighlight %}
{% endtabs %}   

## See also

[How to create custom header and view header in Xamarin.Forms Schedule?](https://www.syncfusion.com/kb/10083/how-to-create-custom-header-and-view-header-in-xamarin-forms-schedule)



