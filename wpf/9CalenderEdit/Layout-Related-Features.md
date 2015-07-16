---
layout: post
title: Layout-Related-Features
description: layout related features
platform: wpf
control: CalendarEdit
documentation: ug
---

# Layout Related Features

This section illustrates the Layout-related features of CalendarEdit control. The following features are discussed:

## Header Background and Foreground Color

CalendarEdit control provides the HeaderBackground and HeaderForeground properties to customize the appearance of the header background and foreground. Use the following code examples to set the above properties.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding calendar with header background and foreground --&gt;&lt;syncfusion:CalendarEdit Name="calendarEdit" HeaderBackground="SaddleBrown" HeaderForeground="Bisque"/&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Setting Header BackgroundcalendarEdit.HeaderBackground = Brushes.SaddleBrown;//Setting Header foregroundcalendarEdit.HeaderForeground = Brushes.Bisque;  //Adding CalendarEdit as window contentthis.Content = calendarEdit;</td></tr>
</table>


{ ![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg) | markdownify }
{:.image }


## Selection Border Color

Whenever a selection is made in the Calendar, the selected day grid can be associated with a border. The color of this selection border of the day grid can be customized using the SelectionBorderBrush property. This dependency property sets the brush value for the selection border brush of the day grid.

To set the SelectionBorderBrush property, use the following code.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding calendar with selection border brush --&gt;&lt;syncfusion:CalendarEdit Name="calendarEdit" SelectionBorderBrush="Aqua"/&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Setting the brush for the Selection day gridcalendarEdit.SelectionBorderBrush = Brushes.Aqua;    //Adding CalendarEdit as window contentthis.Content = calendarEdit;</td></tr>
</table>




{ ![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg) | markdownify }
{:.image }




## Corner Radius for the Selection Border

You can set the corner radius for the selection border by using the SelectionBorderCornerRadius property. This is dependency property sets the value for the corner radius as follows.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding calendar with selection border corner radius --&gt;&lt;syncfusion:CalendarEdit Name="calendarEdit" SelectionBorderCornerRadius="0"/&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance of CalendarEdit controlCalendarEdit calendarEdit = new CalendarEdit();//Setting corner radius for selection bordercalendarEdit.SelectionBorderCornerRadius = new CornerRadius(0); //Adding CalendarEdit as window contentthis.Content = calendarEdit; </td></tr>
</table>


{ ![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg) | markdownify }
{:.image }


## CalendarEdit

Feature: Foreground for Selected Dates

Property Name: SelectionForeground

This property is used to set the foreground color of the dates that are all selected.

This is mainly used to differentiate the SelectedDates from other dates.

<table>
<tr>
<td>
[XAML]&lt;syncfusion:CalendarEdit Name="calendarEdit1" SelectionForeground="Red"/&gt;</td></tr>
<tr>
<td>
[C#]calendarEdit1.SelectionForeground = new SolidColorBrush(Colors.Red);</td></tr>
</table>


{ ![](Layout-Related-Features_images/Layout-Related-Features_img4.png) | markdownify }
{:.image }


