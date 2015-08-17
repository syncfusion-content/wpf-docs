---
layout: post
title: Selecting-Multiple-Dates
description: selecting multiple dates
platform: wpf
control: CalendarEdit
documentation: ug
---

# Selecting Multiple Dates

CalendarEdit control allows you to select multiple dates, by setting the AllowMultiplySelection property to true. The following code example illustrates this.

<table>
<tr>
<td>
[XAML]<!-- Adding CalendarEdit with multiple selection feature--><syncfusion:CalendarEdit Name="calendarEdit" AllowMultiplySelection="True"/></td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Allow multiple selection of datecalendarEdit.AllowMultiplySelection = true; //Adding CalendarEdit as window contentthis.Content = calendarEdit;</td></tr>
</table>




{{ '![](Selecting-Multiple-Dates_images/Selecting-Multiple-Dates_img1.jpeg)' | markdownify }}
{:.image }




See Also

Selecting the Date and Year at Run Time, Scrolling to the Selected Date

