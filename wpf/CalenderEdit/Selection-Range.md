---
layout: post
title: Selection-Range
description: selection range
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selection Range

You can set the selection range mode for CalendarEdit control in two different ways, using the SelectionRangeMode property. They are as follows.

* CurrentMonth: selects only days, belonging to the current month from the column
* WholeColumn: selects the whole column



For setting the selection range mode, use the following code.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding CalendarEdit with selection range mode --&gt;&lt;syncfusion:CalendarEdit Name="calendarEdit" SelectionRangeMode="WholeColumn"/&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Sets selection range mode as whole columncalendarEdit.SelectionRangeMode = SelectionRangeMode.WholeColumn;  //Adding CalendarEdit as window contentthis.Content = calendarEdit;</td></tr>
</table>


