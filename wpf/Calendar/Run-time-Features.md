---
layout: post
title: Run time Features | CalendarEdit | WPF | Syncfusion
description: run time features
platform: wpf
control: CalendarEdit
documentation: ug
---

# Run time Features

This section illustrates the following run-time features of CalendarEdit control:

## Direction for month navigation

In the CalendarEdit control, the direction of month navigation is horizontal by default. You can also change this direction to vertical by setting the [MonthChangeDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~MonthChangeDirection.html) property to Vertical. This dependency property sets the month change direction. Following are the two month change directions.

* Vertical: Enables navigating through the months vertically 
* Horizontal: Enables navigating through the months horizontally

For setting the [MonthChangeDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~MonthChangeDirection.html) property, use the following code.

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with month change direction as vertical -->
<syncfusion:CalendarEdit Name="calendarEdit" MonthChangeDirection="Vertical"/>

{% endhighlight %}

{% highlight c# %}
//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();
//Month change direction as verticalcalendarEdit.MonthChangeDirection = AnimationDirection.Vertical;
//Adding CalendarEdit as window contentthis.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

## Animation

This section describes the following:

* Animation Time for Changing the CalendarEdit Mode
* Animation Time for Month Navigation

### Animation Time for Changing the CalendarEdit Mode

You can set the animation time for changing the mode of the CalendarEdit control, using the [ChangeModeTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~ChangeModeTime.html) property. This dependency property sets the calendar mode changing animation time. It returns an integer value.

To set this property, use the following code.

{% tabs %}
{% highlight XAML %}

<!-- Adding calendar with change mode time -->
<syncfusion:CalendarEdit Name="calendarEdit" ChangeModeTime="10"/>

{% endhighlight %}

{% highlight C# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Setting calendar mode changing animation time
calendarEdit.ChangeModeTime = 10;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

## Animation Time for Month Navigation

The time taken to navigate from one month to another month can be controlled using [FrameMovingTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~FrameMovingTime.html) the property. This dependency property sets the value for month changing animation time. It returns an integer value.

To set this property, use the following code.

{% tabs %}
{% highlight XAML %}
<!-- Adding calendar with Frame moving time as 500 -->
<syncfusion:CalendarEdit Name="calendarEdit" FrameMovingTime="500"/>

{% endhighlight %}

{% highlight C# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Setting the frame moving time
calendarEdit.FrameMovingTime = 500;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

## ToolTip

You can set tooltip for specific days in the CalendarEdit control, using the [SetToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~SetToolTip.html) method. The following code example illustrates tooltip setting for the current system date. 

{% tabs %}
{% highlight C# %}

//Creating an instance date
Date a = new Date();

//Creating an instance of tooltip
ToolTip toolTip = new ToolTip();

//Setting tooltip text
toolTip.Content = "CurrentDate"; 

//Getting the current day
a.Day = DateTime.Now.Day;   

//Getting the current month
a.Month = DateTime.Now.Month;  

//Getting the current year
a.Year = DateTime.Now.Year;

//Setting tooltip for current date
calendarEdit.SetToolTip(a, toolTip); 

{% endhighlight %}
{% endtabs %}

## Scrolling to the selected date

CalendarEdit control enables you to navigate to a particular date in the Calendar, by using the ScrollToDate option. To enable this, set the [ScrollToDateEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~ScrollToDateEnabled.html) property to true. This dependency property indicates whether to scroll to the selected date. 

Here is the code example for setting this property.

{% tabs %}
{% highlight XAML %}
<!-- Adding calendar with scroll to date as true -->
<syncfusion:CalendarEdit Name="calendarEdit" ScrollToDateEnabled="True"/>

{% endhighlight %}

{% highlight C# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Enable scroll to date
calendarEdit.ScrollToDateEnabled = true;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}
