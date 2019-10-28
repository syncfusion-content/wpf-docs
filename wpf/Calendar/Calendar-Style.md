---
layout: post
title: Calendar Style | CalendarEdit | WPF | Syncfusion
description: calendar style
platform: wpf
control: CalendarEdit
documentation: ug
---

# Calendar Style

Using the [CalendarStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CalendarEdit~CalendarStyle.html) property, you can enhance the appearance of the CalendarEdit control. This dependency property sets the calendar style for the control. 

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with calendar style as standard -->
<syncfusion:CalendarEdit Name="calendarEdit" CalendarStyle="Standard"/>

{% endhighlight %}


{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Setting calendar style as standard
calendarEdit.CalendarStyle = CalendarStyle.Standard;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}