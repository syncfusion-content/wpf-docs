---
layout: post
title: Calendar-Style
description: calendar style
platform: wpf
control: CalendarEdit
documentation: ug
---

# Calendar Style

Using the CalendarStyle property, you can enhance the appearance of the CalendarEdit control. This dependency property sets the calendar style for the control. 

_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
CalendarStyle</td><td>
Sets the calendar style for the CalendarEdit control. The options provided are as follows.StandardVista</td></tr>
</table>
Use the following code example to set this property.

<table>
<tr>
<td>
[XAML]<!-- Adding calendar with calendar style as standard --><syncfusion:CalendarEdit Name="calendarEdit" CalendarStyle="Standard"/></td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Setting calendar style as standardcalendarEdit.CalendarStyle = CalendarStyle.Standard;//Adding CalendarEdit as window contentthis.Content = calendarEdit;</td></tr>
</table>


