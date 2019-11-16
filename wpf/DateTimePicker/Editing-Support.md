---
layout: post
title: Editing Support | DateTimeEdit | WPF | Syncfusion
description: Editing Support provides an easy way to select and edit date and time values by setting CanEdit property.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Editing Support

It is possible to type and select date values in the empty DateTimeEdit text box by setting the [CanEdit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CanEdit.html) property as true.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit Name="myDateTimeEdit" Pattern="ShortDate" DateTime="null" CanEdit="True">

</syncfusion:DateTimeEdit>

{% endhighlight  %}

{% highlight c# %}

DateTimeEdit myDateTimeEdit = new DateTimeEdit();
myDateTimeEdit.Pattern = DateTimePattern.ShortDate;
myDateTimeEdit.CanEdit = true;
myDateTimeEdit.DateTime = null;

{% endhighlight  %}

{% endtabs %}

![Editing support](Editing-Support_images/Editing-Support_img1.png)
