---
layout: post
title: Visible Dates customization| SfSchedule | Wpf | Syncfusion
description: This section explains about how to visible dates customization for ScheduleAppointment in WPF Scheduler.
platform: wpf
control: SfSchedule
documentation: ug
---

# Visible Dates customization Of WPF SfSchedule

All views in the schedule have their own number of visible dates. The SfSchedule control allows users to view multiple dates in the day and time line views.

If users want to view particular dates in a single view, users can provide a DateTime collection to the ScheduleDateRange property to view the particular dates in the day and time line view types.

{% highlight c# %}


ObservableCollection<DateTime> visibleDates = newObservableCollection<DateTime>();

            DateTime Date1 = new DateTime(2013, 9, 1);

            DateTime Date2 = new DateTime(2013, 9, 22);

            visibleDates.Add(Date1);

            visibleDates.Add(Date2);

            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleDateRange= visibleDates;

{% endhighlight %}

![Multiple dates visbiled](Visible-Dates-customization_images/Visible-Dates-customization_img1.jpeg)





![Single date visible](Visible-Dates-customization_images/Visible-Dates-customization_img2.jpeg)



