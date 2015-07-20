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

<table>
<tr>
<td>
[XAML]<!-- Adding calendar with culture as Afrikaans --><syncfusion:CalendarEdit Name="calendarEdit" Culture="Afrikaans"/></td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Setting the culturecalendarEdit.Culture = new CultureInfo(2); //Adding CalendarEdit as window contentthis.Content = calendarEdit;   </td></tr>
</table>


{{ '![](Culture_images/Culture_img1.jpeg)' | markdownify }}
{:.image }


