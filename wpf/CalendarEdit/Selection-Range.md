---
layout: post
title: Selection Range | CalendarEdit | WPF | Syncfusion
description: selection range
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selection Range

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
