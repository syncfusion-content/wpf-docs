---
layout: post
title: Using-CalendarEdit-Object
description: using calendaredit object
platform: wpf
control: CalendarEdit
documentation: ug
---

# Using CalendarEdit Object

You can get the object of the CalendarEdit control by using the Calendar property. When you want to see the content after calling the methods, you can store the date in one variable to display or use a MessageBox. The description of each calendar option and code is described as follows.

> _Note: In the following code examples, calendarEdit is used as the instance of the CalendarEdit control._

AddDays

Returns the system datetime, that is, the specified number of days away from the specified system datetime. Use MessageBox to see the content of date after this method is called. 

[C#]



calendarEdit.Calendar.AddDays(calendarEdit.Date, 5);

MessageBox.Show(calendarEdit.Calendar.AddDays(calendarEdit.Date, 5);.ToString());





AddHours

Returns the system datetime, that is, the specified number of hours away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddHours(calendarEdit.Date, 2);

MessageBox.Show(calendarEdit.Calendar.AddHours(calendarEdit.Date, 2).ToString());



AddMonths

Returns the system datetime, that is, the specified number of months away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddMonths(calendarEdit.Date, 3);

MessageBox.Show(calendarEdit.Calendar.AddMonths(calendarEdit.Date, 3).ToString());



AddMilliseconds 

Returns the system datetime, that is, the specified number of milliseconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddMilliseconds(calendarEdit.Date, 200);

MessageBox.Show(calendarEdit.Calendar.AddMilliseconds(calendarEdit.Date, 200).ToString());



AddMinutes

Returns the system datetime, that is, the specified number of milliseconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.



[C#]



calendarEdit.Calendar.AddMinutes(calendarEdit.Date, 5);

MessageBox.Show(calendarEdit.Calendar.AddMinutes(calendarEdit.Date, 5).ToString());



AddSeconds

Returns the system datetime, that is, specified number of seconds away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddSeconds(calendarEdit.Date, 30);

MessageBox.Show(calendarEdit.Calendar.AddSeconds(calendarEdit.Date, 30).ToString());



AddWeeks

Returns the system datetime, that is, specified number of weeks away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddWeeks(calendarEdit.Date, 2);

MessageBox.Show(calendarEdit.Calendar.AddWeeks(calendarEdit.Date, 2).ToString());



AddYears

Returns the system datetime, that is, the specified number of years away from the specified system datetime. Use Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.AddYears(calendarEdit.Date, 1);

MessageBox.Show(calendarEdit.Calendar.AddYears(calendarEdit.Date, 1).ToString());



GetDayOfMonth

Returns the day of the month, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetDayOfMonth(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetDayOfMonth(calendarEdit.Date).ToString());



GetDayOfWeek

Returns the day of the week, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetDayOfWeek(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetDayOfWeek(calendarEdit.Date).ToString());



GetDayOfYear

Returns the day of the year, in the specified System datetime. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetDayOfYear(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetDayOfYear(calendarEdit.Date).ToString());



GetDayOfYear

Returns the number of days, in the specified month and year of the current era. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetDaysInMonth(2009, 2);

MessageBox.Show(calendarEdit.Calendar.GetDaysInMonth(2009, 2).ToString());





GetDaysInYear

Returns the number of days, in the specified year of the current era. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetDaysInYear(2009);

MessageBox.Show(calendarEdit.Calendar.GetDaysInYear(2009).ToString());



GetEra

Returns the era, in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetEra(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetEra(calendarEdit.Date).ToString());



GetHour

Returns the hour, in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetHour(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetHour(calendarEdit.Date).ToString());



GetLeapMonth

Returns the leap month, in the specified year. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetLeapMonth(2009);

MessageBox.Show(calendarEdit.Calendar.GetLeapMonth(2009).ToString());



GetMilliseconds

Returns the milliseconds, in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetMilliSeconds(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetMilliseconds(calendarEdit.Date).ToString());



GetMinute

Returns the minute, in the specified datetime. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetMinute(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetMinute(calendarEdit.Date).ToString());



GetMonth

Returns the month, in the specified datetime. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetMonth(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetMonth(calendarEdit.Date).ToString());



GetMonthsInYear

Returns the month in the specified year in the current era. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetMonthsInYear(2009);

MessageBox.Show(calendarEdit.Calendar.GetMonthsInYear(2009).ToString());



GetSecond

Returns the seconds, in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetSecond(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetSecond(calendarEdit.Date).ToString());





GetWeekOfYear

Returns the week of the year that includes the date in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetWeekOfYear(calendarEdit.Date, System.Globalization.CalendarWeekRule.FirstDay, DayOfWeek.Friday);

MessageBox.Show(calendarEdit.Calendar.GetWeekOfYear(calendarEdit.Date, System.Globalization.CalendarWeekRule.FirstDay, DayOfWeek.Friday).ToString());





GetYear

Returns the week of the year that includes the date in the specified date time. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.GetYear(calendarEdit.Date);

MessageBox.Show(calendarEdit.Calendar.GetYear(calendarEdit.Date).ToString());





IsLeapDay

Determines whether the specified date in the current era is a leap day. You can use a Message Box to see the content of date after this method is called. 

[C#]



calendarEdit.Calendar.IsLeapDay(2009, 2, 2);

MessageBox.Show(calendarEdit.Calendar.IsLeapDay(2009, 2, 2).ToString());



IsLeapMonth

Determines whether the specified month, in the specified year, in the current era, is a leap month. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.IsLeapMonth(2009, 3);

MessageBox.Show(calendarEdit.Calendar.IsLeapMonth(2009, 3).ToString());





IsLeapYear

Determines whether the specified year, in the current era, is a leap year. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.IsLeapYear(2009);

MessageBox.Show(calendarEdit.Calendar.IsLeapYear(2009).ToString());



MaxSupportedDateTime

Gets the latest date and time, supported by the calendar object. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.MaxSupportedDateTime;

MessageBox.Show(calendarEdit.Calendar.MaxSupportedDateTime.ToString());





MinSupportedDateTime

Gets the earliest date and time, supported by the calendar object. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.MinSupportedDateTime;

MessageBox.Show(calendarEdit.Calendar.MinSupportedDateTime.ToString());





TwoDigitYearMax

Gets or sets the last year of a 100-year range that can be represented as a 2 digit year. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.TwoDigitYearMax;

MessageBox.Show(calendarEdit.Calendar.TwoDigitYearMax.ToString());





ToDateTime

Returns the datetime that is set to the specified date and time in the current era. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.ToDateTime(2009, 4, 5, 2, 30, 5, 200);

MessageBox.Show(calendarEdit.Calendar.ToDateTime(2009, 4, 5, 2, 30, 5, 200).ToString());





ToFourDigitYear

Convert specified year to a 4 digit year. You can use a Message Box to see the content of date after this method is called.

[C#]



calendarEdit.Calendar.ToFourDigitYear(2009);

MessageBox.Show(calendarEdit.Calendar.ToFourDigitYear(2009).ToString());





