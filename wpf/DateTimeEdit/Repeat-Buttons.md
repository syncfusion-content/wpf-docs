---
layout: post
title: Repeat-Buttons
description: repeat buttons
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Repeat Buttons

Repeat Buttons are used to spin the selected part (month, day, year, hour, second, and minute) one step up or down. The visibility of the Repeat Button can be enabled by setting the IsVisibleRepeatButton property to true. The RepeatButtonBackground, RepeatButtonBorderThickness, UpRepeatButtonTemplate, RepeatButtonTemplate, UpRepeatButtonMargin, and DownRepeatButtonMargin properties are used to customize the appearance of the Repeat Buttons.


{% highlight html %}


<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10"                          IsVisibleRepeatButton="True"                          UpRepeatButtonMargin="1" DownRepeatButtonMargin="1"/>
{% endhighlight  %}


![](Repeat-Buttons_images/Repeat-Buttons_img1.png)


See Also

Keyboard and Mouse support

Setting Date

