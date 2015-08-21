---
layout: post
title: Visible-Dates-customization
description: visible dates customization
platform: wpf
control: SfSchedule
documentation: ug
---

# Visible Dates customization

All views in the schedule have their own number of visible dates. The SfSchedule control allows users to view multiple dates in the day and time line views.

If users want to view particular dates in a single view, users can provide a DateTime collection to the ScheduleDateRange property to view the particular dates in the day and time line view types.
{% highlight c# %}


ObservableCollection<DateTime> selectedDates = newObservableCollection<DateTime>();

            DateTime Date1 = new DateTime(2013, 9, 1);

            DateTime Date2 = new DateTime(2013, 9, 22);

            selectedDates.Add(Date1);

            selectedDates.Add(Date2);

            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleDateRange= visibleDates;

{% endhighlight %}

![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_32.jpg](Visible-Dates-customization_images/Visible-Dates-customization_img1.jpeg)





![http://help.syncfusion.com/ug/wpf/sfschedule/ImagesExt/image632_33.jpg](Visible-Dates-customization_images/Visible-Dates-customization_img2.jpeg)



