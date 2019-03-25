---
layout: post
title: Repeat Buttons | DateTimeEdit | wpf | Syncfusion
description: repeat buttons
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Repeat Buttons

Repeat Buttons are used to spin the selected part (month, day, year, hour, second, and minute) one step up or down. The visibility of the Repeat Button can be enabled by setting the [IsVisibleRepeatButton](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsVisibleRepeatButton.html) property to true. The [RepeatButtonBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~RepeatButtonBackground.html), [RepeatButtonBorderThickness](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~RepeatButtonBorderThickness.html), [UpRepeatButtonTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~UpRepeatButtonTemplate.html), [DownRepeatButtonTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~DownRepeatButtonTemplate.html), [UpRepeatButtonMargin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~UpRepeatButtonMargin.html), and [DownRepeatButtonMargin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~DownRepeatButtonMargin.html) properties are used to customize the appearance of the Repeat Buttons.

{% tabs %}
{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10" IsVisibleRepeatButton="True" UpRepeatButtonMargin="1" DownRepeatButtonMargin="1"/>

{% endhighlight  %}
{% endtabs %}

![Repeat button](Repeat-Buttons_images/Repeat-Buttons_img1.png)

{% seealso %}

[Keyboard and Mouse support](/wpf/datetimeedit/keyboard-and-mouse-support)

{% endseealso %}

