---
layout: post
title: Selecting the Date and Year at Run Time | CalendarEdit | WPF | Syncfusion
description: selecting the date and year at run time
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selecting the Date and Year at Runtime

Selecting Date at Run Time

By setting the AllowSelection property to true, you can enable user selection in CalendarEdit control at run time. This dependency property indicates whether the date selection is allowed during runtime. It returns a Boolean value indicating the state of this property.

For setting the AllowSelection property, use the following code.

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with allow selection of a date -->
<syncfusion:CalendarEdit Name="calendarEdit" AllowSelection="True"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Allow selection of a date
calendarEdit.AllowSelection = true;

//Adding calendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

![](Selecting-the-Date-and-Year-at-Run-Time_images/Selecting-the-Date-and-Year-at-Run-Time_img1.jpeg)

### Selecting year at runtime

By setting the AllowYearEditing property to _true_, you can edit the year at run time. This is dependency property indicates whether the year can be edited at run time. It returns the Boolean value that indicates the state of this property.

To set the AllowYearEditing property, use the following code.

{% tabs %}
{% highlight xaml %}
<!-- Setting AllowYearEditing property-->
<syncfusion:CalendarEdit Name="calendarEdit" AllowYearEditing="True"/>

{% endhighlight %}

{% highlight c# %}
//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Allow selection of year
calendarEdit.AllowYearEditing = true;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

![](Selecting-the-Date-and-Year-at-Run-Time_images/Selecting-the-Date-and-Year-at-Run-Time_img2.jpeg)

{% seealso %}

[Selecting Multiple Dates](/wpf/calendaredit/selecting-multiple-dates), [Scrolling to the Selected Date](/wpf/calendaredit/run-time-features#scrolling-to-the-selected-date)

{% endseealso %}
