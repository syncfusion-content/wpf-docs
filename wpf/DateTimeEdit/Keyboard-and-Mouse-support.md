---
layout: post
title: Keyboard and Mouse support | DateTimeEdit | wpf | Syncfusion
description: keyboard and mouse support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Keyboard and Mouse support

Up or down arrows in the DateTimeEdit control spin the selected parts (month, day, year, hour, second, and minute) one step up or down. Mouse Scroll in the DateTimeEdit control spin the selected parts in the DateTime property one step up or down. The spin behavior in the DateTimeEdit control can be enabled by setting the IsScrollingOnCircle property to true.

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10"  IsScrollingOnCircle="True"/>

{% endhighlight %}

After selecting any part in the DateTime value if you press the Up or Down arrows (or Scroll the Mouse Up or Down) then the selected value will automatically change.

![](Keyboard-and-Mouse-support_images/Keyboard-and-Mouse-support_img1.png)


## Open and Close DropDown through Keyboard

`DateTimeEdit` dropdown Popup can be opened and closed by pressing Enter key. This behavior can be enabled by setting the `AllowEnter` property of DateTimeEdit to true.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="datetimeedit" CanEdit="False" AllowEnter="True">

</syncfusion:DateTimeEdit>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

datetimeedit.CanEdit = false;

datetimeedit.AllowEnter = true;


{% endhighlight %}

{% highlight VB %}

datetimeedit.CanEdit = False

datetimeedit.AllowEnter = True

{% endhighlight %}

{% endtabs %}

N> Dropdown popup of DateTimeEdit cannot be opened by pressing Enter Key when CanEdit Property set to `True`.

{% seealso %}

Repeat Buttons

Setting Date

{% endseealso %}

