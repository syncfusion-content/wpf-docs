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



{% highlight xml %}
[XAML]<syncfusion:DateTimeEdit Name="myDateTimeEdit" Pattern="ShortDate" DateTime="null" CanEdit="True">
</syncfusion:DateTimeEdit>
{% endhighlight  %}
{% highlight c# %}
[C#]
DateTimeEdit myDateTimeEdit = new DateTimeEdit();
myDateTimeEdit.Pattern = DateTimePattern.ShortDate;
myDateTimeEdit.CanEdit = true;myDateTimeEdit.DateTime = null;
{% endhighlight  %}


![](Editing-Support_images/Editing-Support_img1.png)



Properties

_Edit property table_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Data Type </th></tr>
<tr>
<td>
CanEdit</td><td>
Allows users to type and select the date value in the empty DateTimeEdit text box.</td><td>
bool</td></tr>
</table>


