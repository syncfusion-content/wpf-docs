---
layout: post
title: Calendar Types in WPF Scheduler control | Syncfusion
description: Learn here all about how to change the calendar types in scheduler (SfScheduler) control, its elements, and more.
platform: WPF
control: SfScheduler
documentation: ug
---

# Calendar Types in WPF Scheduler (SfScheduler)
This section describes how to change the calendar types of scheduler control using `CalendarIdentifier`.

## Types of Calendar
The Scheduler control supports the different type of calendars such as Gregorian, Korean, Hebrew, etc. You can change the calendar types by using the `CalendarIdentifier` property in Scheduler. The default value of `CalendarIdentifier` property is `GregorianCalendar`.

You can select the required `CalendarIdentifier` value from below types.

* GregorianCalendar
* HebrewCalendar
* HijriCalendar
* KoreanCalendar
* TaiwanCalendar
* ThaiCalendar
* UmAlQuraCalendar
* PersianCalendar
* JulianCalendar

N> 
* Japanese and Lunar type calendars are not supported in `Scheduler` control.
 * When `CalendarIdentifier` and `FlowDirection` properties are set, `FlowDirection` property is given higher precedence. If you want to override this behavior set `FlowDirection` after `CalendarIdentifier`.

{% tabs %}
{% highlight xaml %}
<scheduler:SfScheduler x:Name="Schedule"
                       CalendarIdentifier="HebrewCalendar" />
{% endhighlight %}
{% highlight c# %}
this.Schedule.CalendarIdentifier = "HebrewCalendar";
{% endhighlight %}
{% endtabs %}

![Hebrew Calendar](Calendar-Types_Images/CalendarTypes.png)

## DateTime values in Calendar types
You can give all the DateTime values such as `DispalyDate`, `SelectedDate`, `BlackoutDates`, Appointment `StartTime` and `EndTime`, `SpecialTimeRegion` Start and End time values in two ways When calendar identifier is specified other than `GregorianCalendar`.

* `DateTime` instance without specifying calendar type. Scheduler will handle the `DateTime` value for the specified calendar type.

* `DateTime` instance with specified calendar type. If calendar type is mentioned then the date should be respective to that calendar so that the date value will be converted to Gregorian DateTime and scheduler will handle that DateTime.