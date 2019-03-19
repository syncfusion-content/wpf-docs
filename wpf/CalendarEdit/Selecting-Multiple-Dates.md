---
layout: post
title: Selecting Multiple Dates | CalendarEdit | WPF | Syncfusion
description: selecting multiple dates
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selecting Multiple Dates

CalendarEdit control allows you to select multiple dates, by setting the [AllowMultiplySelection](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~AllowMultiplySelection.html) property to true. The following code example illustrates this.

{% tabs %}
{% highlight xaml %}

<!-- Adding CalendarEdit with multiple selection feature-->
<syncfusion:CalendarEdit Name="calendarEdit" AllowMultiplySelection="True"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Allow multiple selection of date
calendarEdit.AllowMultiplySelection = true;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

![Multiple date selection](Selecting-Multiple-Dates_images/Selecting-Multiple-Dates_img1.jpeg)

{% seealso %}

[Scrolling to the Selected Date](/wpf/calendaredit/run-time-features#scrolling-to-the-selected-date)

{% endseealso %}
