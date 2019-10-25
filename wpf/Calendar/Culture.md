---
layout: post
title: Culture | CalendarEdit | WPF | Syncfusion
description: culture
platform: wpf
control: CalendarEdit
documentation: ug
---

# Culture

CalendarEdit control supports different cultures. The culture information can be applied using the Culture property. This dependency property sets the culture for the CalendarEdit control. 

To change the culture for the CalendarEdit control, use the following code example.  

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with culture as Afrikaans --><syncfusion:CalendarEdit Name="calendarEdit" Culture="Afrikaans"/></td></tr>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Setting the culture
calendarEdit.Culture = new CultureInfo(2);

//Adding CalendarEdit as window content
this.Content = calendarEdit;  

{% endhighlight %}
{% endtabs %}

![](Culture_images/Culture_img1.jpeg)
