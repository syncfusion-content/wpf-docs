---
layout: post
title: DateTime-Patterns
description: datetime patterns
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime Patterns

You can customize the display format of the date in the DateTimeEdit control by using the Pattern and CustomPattern properties.

## Pattern

The date patterns supported by the DateTimeEdit control can be classified into the following eleven patterns: 

* LongDate 
* LongTime 
* ShortDate 
* ShortTime 
* FullDateTime 
* MonthDay 
* CustomPattern 
* ShortableDateTime 
* UniversalShortableDateTime 
* RFC1123 
* YearMonth 

The pattern is set by using the Pattern property. The following code snippet illustrates how to set the pattern as FullDateTime:



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"                          DateTime="07/15/2010" Pattern="ShortDate"></syncfusion:DateTimeEdit></td></tr>
<tr>
<td>
C#</td></tr>
<tr>
<td>
Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new                    Syncfusion.Windows.Shared.DateTimeEdit();dateTimeEdit.Width = 200;dateTimeEdit.Height = 25;dateTimeEdit.DateTime = new DateTime(2010, 07, 05);//Setting predefined patterndateTimeEdit.Pattern = DateTimePattern.ShortDate;</td></tr>
</table>


{{ '![](DateTime-Patterns_images/DateTime-Patterns_img1.png)' | markdownify }}
{:.image }


## Custom Pattern

You can also set the custom pattern for displaying the date in the DateTimeEdit control by using the CustomPattern property.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"                          DateTime="07/15/2010" Pattern="CustomPattern"                          CustomPattern="MM/dd/yy hh:mm:ss"></syncfusion:DateTimeEdit></td></tr>
<tr>
<td>
C#</td></tr>
<tr>
<td>
Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();dateTimeEdit.Width = 200;dateTimeEdit.Height = 25;dateTimeEdit.DateTime = new DateTime(2010, 07, 05);dateTimeEdit.Pattern = DateTimePattern.CustomPattern;//Setting Custom PatterndateTimeEdit.CustomPattern = "MM/dd/yy hh:mm:ss";this.LayoutRoot.Children.Add(dateTimeEdit);</td></tr>
</table>


{{ '![](DateTime-Patterns_images/DateTime-Patterns_img2.png)' | markdownify }}
{:.image }


> _Note: CustomPattern support can be enabled by setting the Pattern property to the DateTimePattern.CustomPattern._

> 

