---
layout: post
title: Events
description: events
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Events

DateTimeEdit control exposes the following events:

## DateTimeChanged

This event occurs when the DateTime property of the DateTimeEdit control is changed.



<table>
<tr>
<td>
[XAML]</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit Width="150" DateTimeChanged="DateTimeEdit_DateTimeChanged"/></td></tr>
</table>


You can handle the event as follows:



<table>
<tr>
<td>
[C#]</td></tr>
<tr>
<td>
private void DateTimeEdit_DateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }</td></tr>
</table>
## MinDateTimeChanged

This event occurs when the MinDateTime property of the DateTimeEdit control is changed.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit Width="150" MinDateTimeChanged="DateTimeEdit_MinDateTimeChanged"/></td></tr>
</table>


You can handle the event as follows:



<table>
<tr>
<td>
C#</td></tr>
<tr>
<td>
private void DateTimeEdit_MinDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }</td></tr>
</table>
## MaxDateTimeChanged

This event occurs when the MaxDateTime property of the DateTimeEdit control is changed.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit Width="150" MaxDateTimeChanged="DateTimeEdit_MaxDateTimeChanged"/></td></tr>
</table>


You can handle the event as follows:



<table>
<tr>
<td>
C#</td></tr>
<tr>
<td>
private void DateTimeEdit_MaxDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }</td></tr>
</table>
## PatternChanged

This event occurs when the Pattern property of the DateTimeEdit control is changed.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit Width="150" PatternChanged="DateTimeEdit_PatternChanged"/></td></tr>
</table>


You can handle the event as follows:



<table>
<tr>
<td>
C#</td></tr>
<tr>
<td>
private void DateTimeEdit_PatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }</td></tr>
</table>
## CalendarPopupOpened

This event occurs when the Calendar popup is open.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit Height="25" Width="150" EnableClassicStyle="True" CalendarPopupOpened="DateTimeEdit_CalendarPopupOpened"/></td></tr>
</table>


You can handle the event as follows:



<table>
<tr>
<td>
C#</td></tr>
<tr>
<td>
private void DateTimeEdit_CalendarPopupOpened(object sender, RoutedEventArgs e)        {        }</td></tr>
</table>


