---
layout: post
title: Selection Range in WPF CalendarEdit| Syncfusion
description: This section explains how to set a selection range to select a date in within the particular range.
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selection Range in WPF CalendarEdit

You can set the selection range mode for CalendarEdit control in two different ways, using the [SelectionRangeMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~SelectionRangeMode.html) property. They are as follows.

* CurrentMonth: selects only days, belonging to the current month from the column
* WholeColumn: selects the whole column

For setting the selection range mode, use the following code.

{% tabs %}
{% highlight xaml %}

<!-- Adding CalendarEdit with selection range mode -->
<syncfusion:CalendarEdit Name="calendarEdit" SelectionRangeMode="WholeColumn"/>

{% endhighlight %}

{% highlight c# %}
//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Sets selection range mode as whole column
calendarEdit.SelectionRangeMode = SelectionRangeMode.WholeColumn;  

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

## Block particular dates 

You can restrict the user to select the dates within some range by blocking the particular dates in the `CalendarEdit`. You can also block the more date ranges by adding that date ranges into the [BlackoutDates](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~BlackoutDates.html) collection.



{% tabs %}
{% highlight xaml %}

<syncfusion:CalendarEdit x:Name="calendarEdit">
    <syncfusion:CalendarEdit.BlackoutDates>    
        <syncfusion:BlackoutDatesRange StartDate="1/01/2020" EndDate="1/10/2020"/>
        <syncfusion:BlackoutDatesRange StartDate="5/01/2020" EndDate="{x:Static system:DateTime.Today}"/>
    </syncfusion:CalendarEdit.BlackoutDates>
</syncfusion:CalendarEdit>


{% endhighlight  %}
{% highlight C# %}


{% endhighlight  %}
{% endtabs %}

![Block particular dates in WPF CalendarEdit](Selecting-Multiple-Dates_images/BlackOutDays.png)

N> View [Sample]() in GitHub
