---
layout: post
title: Culture
description: culture
platform: wpf
control: CalendarEdit
documentation: ug
---

# Culture

CalendarEdit control supports different cultures. The culture information can be applied using the Culture property. This dependency property sets the culture for the CalendarEdit control. 

To change the culture for the CalendarEdit control, use the following code example.  

{% highlight xml %}
<!-- Adding calendar with culture as Afrikaans -->
<syncfusion:CalendarEdit Name="calendarEdit" Culture="Afrikaans"/>
{% endhighlight  %}
{% highlight c# %}
//Creating an instance of CalendarEdit 
controlCalendarEdit calendarEdit = new CalendarEdit();
//Setting the culture
calendarEdit.Culture = new CultureInfo(2); 
//Adding CalendarEdit as window content
this.Content = calendarEdit; 
{% endhighlight  %}


![](Culture_images/Culture_img1.jpeg)

_Culture = "Afrikaans"_

