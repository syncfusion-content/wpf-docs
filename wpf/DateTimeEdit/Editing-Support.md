---
layout: post
title: Editing-Support
description: editing support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Editing Support

It is possible to type and select date values in the empty DateTimeEdit text box by setting the CanEdit property as true.



<table>
<tr>
<td>
[XAML]<syncfusion:DateTimeEdit Name="myDateTimeEdit" Pattern="ShortDate" DateTime="null" CanEdit="True">&lt;/syncfusion:DateTimeEdit&gt;</td></tr>
<tr>
<td>
[C#]DateTimeEdit myDateTimeEdit = new DateTimeEdit();myDateTimeEdit.Pattern = DateTimePattern.ShortDate;myDateTimeEdit.CanEdit = true;myDateTimeEdit.DateTime = null;</td></tr>
</table>


{ ![](Editing-Support_images/Editing-Support_img1.png) | markdownify }
{:.image }


Properties

_Edit property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Data Type </td></tr>
<tr>
<td>
CanEdit</td><td>
Allows users to type and select the date value in the empty DateTimeEdit text box.</td><td>
bool</td></tr>
</table>


