---
layout: post
title: Custom-format-string
description: custom format string
platform: wpf
control: TimeSpanEdit
documentation: ug
---

# Custom format string

The fields can be formatted to show what the numerals denote i.e. hours minutes or days.



{ ![](Custom-format-string_images/Custom-format-string_img1.png) | markdownify }
{:.image }




[XAML]

&lt;syncfusion:TimeSpanEdit Value="10.2:25:52" Format="d ‘days’ h 'hours'"  Height="40"/&gt;



[C#]

timeSpanEdit1.Format = @" d 'days' h 'hours'";



