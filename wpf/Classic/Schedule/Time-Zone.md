---
layout: post
title: Time-Zone in WPF SfSchedule Control | Syncfusion
description: Learn here all about Time-Zone support in Syncfusion WPF Schedule (Classic) control, its elements and more details.
platform: wpf
control: SfSchedule
documentation: ug
---

# Time-Zone in WPF Schedule (Classic)

In Schedule, appointments can be created at various time zones using the properties StartTimeZone and EndTimeZone of the ScheduleAppointment.
{% highlight c# %}




SfSchedule schedule = new SfSchedule();

schedule.Appointments.Add(new ScheduleAppointment() { StartTimeZone= schedule.TimeZoneCollection[2], EndTimeZone= schedule.TimeZoneCollection[2], StartTime= new DateTime(2013,6,5,5,0,0), EndTime= new DateTime(2013,6,5,5,30,0), Subject="Meet the doc", Location="Hutchison road", AllDay=false });

{% endhighlight  %}

