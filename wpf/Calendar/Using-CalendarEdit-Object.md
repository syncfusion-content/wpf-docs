---
layout: post
title: Using CalendarEdit Object in WPF Calendar control | Syncfusion
description: Learn here all about Using CalendarEdit Object support in Syncfusion WPF Calendar (CalendarEdit) control and more.
platform: wpf
control: CalendarEdit
documentation: ug
---

# Using CalendarEdit Object in WPF Calendar (CalendarEdit)

You can get the object of the CalendarEdit control by using the Calendar property. When you want to see the content after calling the methods, you can store the date in one variable to display or use a MessageBox. The description of each calendar option and code is described as follows.

N> In the following code examples, calendarEdit is used as the instance of the CalendarEdit control.

### AddDays

Returns the system datetime, that is, the specified number of days away from the specified system datetime. Use MessageBox to see the content of date after this method is called. 

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddDays(calendarEdit.Date, 5);
MessageBox.Show(calendarEdit.Calendar.AddDays(calendarEdit.Date, 5);.ToString());

{% endhighlight %}
{% endtabs %}

### AddHours

Returns the system datetime, that is, the specified number of hours away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddHours(calendarEdit.Date, 2);
MessageBox.Show(calendarEdit.Calendar.AddHours(calendarEdit.Date, 2).ToString());

{% endhighlight %}
{% endtabs %}

### AddMonths

Returns the system datetime, that is, the specified number of months away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddMonths(calendarEdit.Date, 3);
MessageBox.Show(calendarEdit.Calendar.AddMonths(calendarEdit.Date, 3).ToString());

{% endhighlight %}
{% endtabs %}

### AddMilliseconds 

Returns the system datetime, that is, the specified number of milliseconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddMilliseconds(calendarEdit.Date, 200);
MessageBox.Show(calendarEdit.Calendar.AddMilliseconds(calendarEdit.Date, 200).ToString());

{% endhighlight %}
{% endtabs %}

### AddMinutes

Returns the system datetime, that is, the specified number of milliseconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddMinutes(calendarEdit.Date, 5);
MessageBox.Show(calendarEdit.Calendar.AddMinutes(calendarEdit.Date, 5).ToString());

{% endhighlight %}
{% endtabs %}

### AddSeconds

Returns the system datetime, that is, specified number of seconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddSeconds(calendarEdit.Date, 30);
MessageBox.Show(calendarEdit.Calendar.AddSeconds(calendarEdit.Date, 30).ToString());

{% endhighlight %}
{% endtabs %}

### AddWeeks

Returns the system datetime, that is, specified number of weeks away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddWeeks(calendarEdit.Date, 2);
MessageBox.Show(calendarEdit.Calendar.AddWeeks(calendarEdit.Date, 2).ToString());

{% endhighlight %}
{% endtabs %}

### AddYears

Returns the system datetime, that is, the specified number of years away from the specified system datetime. Use Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.AddYears(calendarEdit.Date, 1);
MessageBox.Show(calendarEdit.Calendar.AddYears(calendarEdit.Date, 1).ToString());

{% endhighlight %}
{% endtabs %}

### GetDayOfMonth

Returns the day of the month, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetDayOfMonth(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetDayOfMonth(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetDayOfWeek

Returns the day of the week, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetDayOfWeek(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetDayOfWeek(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetDayOfYear

Returns the day of the year, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetDayOfYear(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetDayOfYear(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetDayOfYear

Returns the number of days, in the specified month and year of the current era. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetDaysInMonth(2009, 2);
MessageBox.Show(calendarEdit.Calendar.GetDaysInMonth(2009, 2).ToString());

{% endhighlight %}
{% endtabs %}

### GetDaysInYear

Returns the number of days, in the specified year of the current era. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetDaysInYear(2009);
MessageBox.Show(calendarEdit.Calendar.GetDaysInYear(2009).ToString());

{% endhighlight %}
{% endtabs %}

### GetEra

Returns the era, in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetEra(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetEra(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetHour

Returns the hour, in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetHour(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetHour(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetLeapMonth

Returns the leap month, in the specified year. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetLeapMonth(2009);
MessageBox.Show(calendarEdit.Calendar.GetLeapMonth(2009).ToString());

{% endhighlight %}
{% endtabs %}

### GetMilliseconds

Returns the milliseconds, in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetMilliSeconds(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetMilliseconds(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetMinute

Returns the minute, in the specified datetime. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetMinute(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetMinute(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetMonth

Returns the month, in the specified datetime. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetMonth(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetMonth(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetMonthsInYear

Returns the month in the specified year in the current era. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetMonthsInYear(2009);
MessageBox.Show(calendarEdit.Calendar.GetMonthsInYear(2009).ToString());

{% endhighlight %}
{% endtabs %}

### GetSecond

Returns the seconds, in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetSecond(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetSecond(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### GetWeekOfYear

Returns the week of the year that includes the date in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetWeekOfYear(calendarEdit.Date, System.Globalization.CalendarWeekRule.FirstDay, DayOfWeek.Friday);
MessageBox.Show(calendarEdit.Calendar.GetWeekOfYear(calendarEdit.Date, System.Globalization.CalendarWeekRule.FirstDay, DayOfWeek.Friday).ToString());

{% endhighlight %}
{% endtabs %}

### GetYear

Returns the week of the year that includes the date in the specified date time. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.GetYear(calendarEdit.Date);
MessageBox.Show(calendarEdit.Calendar.GetYear(calendarEdit.Date).ToString());

{% endhighlight %}
{% endtabs %}

### IsLeapDay

Determines whether the specified date in the current era is a leap day. You can use a Message Box to see the content of date after this method is called. 

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.IsLeapDay(2009, 2, 2);
MessageBox.Show(calendarEdit.Calendar.IsLeapDay(2009, 2, 2).ToString());

{% endhighlight %}
{% endtabs %}

### IsLeapMonth

Determines whether the specified month, in the specified year, in the current era, is a leap month. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.IsLeapMonth(2009, 3);
MessageBox.Show(calendarEdit.Calendar.IsLeapMonth(2009, 3).ToString());

{% endhighlight %}
{% endtabs %}

### IsLeapYear

Determines whether the specified year, in the current era, is a leap year. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.IsLeapYear(2009);
MessageBox.Show(calendarEdit.Calendar.IsLeapYear(2009).ToString());

{% endhighlight %}
{% endtabs %}

### MaxSupportedDateTime

Gets the latest date and time, supported by the calendar object. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.MaxSupportedDateTime;
MessageBox.Show(calendarEdit.Calendar.MaxSupportedDateTime.ToString());

{% endhighlight %}
{% endtabs %}

### MinSupportedDateTime

Gets the earliest date and time, supported by the calendar object. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.MinSupportedDateTime;
MessageBox.Show(calendarEdit.Calendar.MinSupportedDateTime.ToString());

{% endhighlight %}
{% endtabs %}

### TwoDigitYearMax

Gets or sets the last year of a 100-year range that can be represented as a 2 digit year. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.TwoDigitYearMax;
MessageBox.Show(calendarEdit.Calendar.TwoDigitYearMax.ToString());

{% endhighlight %}
{% endtabs %}

### ToDateTime

Returns the datetime that is set to the specified date and time in the current era. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.ToDateTime(2009, 4, 5, 2, 30, 5, 200);
MessageBox.Show(calendarEdit.Calendar.ToDateTime(2009, 4, 5, 2, 30, 5, 200).ToString());

{% endhighlight %}
{% endtabs %}

### ToFourDigitYear

Convert specified year to a 4 digit year. You can use a Message Box to see the content of date after this method is called.

{% tabs %}
{% highlight c# %}

calendarEdit.Calendar.ToFourDigitYear(2009);
MessageBox.Show(calendarEdit.Calendar.ToFourDigitYear(2009).ToString());

{% endhighlight %}
{% endtabs %}
