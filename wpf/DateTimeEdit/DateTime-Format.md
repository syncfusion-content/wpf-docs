---
layout: post
title: DateTime-Format
description: datetime format
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime Format

DateTimeFormat property defines the Format to display the date value in the DateTimeEdit control. Using this property you can customize the Standard datetime formats such as the YearMonthPattern, ShortTimePattern, ShortDatePattern, MonthDayPattern, LongTimePattern, LongDatePattern, and FullDateTimePattern. 



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="07/15/2010" Pattern="ShortDate">    <syncfusion:DateTimeEdit.DateTimeFormat>        <global:DateTimeFormatInfo ShortDatePattern="MM/dd/yy hh:mm:ss"/>    </syncfusion:DateTimeEdit.DateTimeFormat></syncfusion:DateTimeEdit></td></tr>
<tr>
<td>
C#</td></tr>
<tr>
<td>
Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();dateTimeEdit.Width = 200;dateTimeEdit.Height = 25;dateTimeEdit.DateTime = new DateTime(2010, 07, 05);dateTimeEdit.Pattern = DateTimePattern.ShortDate;dateTimeEdit.DateTimeFormat = new DateTimeFormatInfo(){    ShortDatePattern = "MM/dd/yy hh:mm:ss"};</td></tr>
</table>




{{ '![](DateTime-Format_images/DateTime-Format_img1.png)' | markdownify }}
{:.image }


