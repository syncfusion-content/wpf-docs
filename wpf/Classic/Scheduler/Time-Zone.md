---
layout: post
title: Time Zone| SfSchedule | Wpf | Syncfusion
description: time zone
platform: wpf
control: SfSchedule
documentation: ug
---

# Time Zone

In Schedule, appointments can be created at various time zones using the properties StartTimeZone and EndTimeZone of the ScheduleAppointment.
{% highlight c# %}




SfSchedule schedule = new SfSchedule();

schedule.Appointments.Add(new ScheduleAppointment() { StartTimeZone= schedule.TimeZoneCollection[2], EndTimeZone= schedule.TimeZoneCollection[2], StartTime= new DateTime(2013,6,5,5,0,0), EndTime= new DateTime(2013,6,5,5,30,0), Subject="Meet the doc", Location="Hutchison road", AllDay=false });

{% endhighlight  %}

