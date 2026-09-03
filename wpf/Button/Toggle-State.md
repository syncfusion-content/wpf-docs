---
layout: post
title: Toggle State in WPF Button | Syncfusion®
description: Toggle State in WPF Button (ButtonAdv) enables buttons to maintain checked and unchecked states using the IsCheckable and IsChecked properties.
platform: wpf
control: ButtonAdv
documentation: ug
---

# Toggle State in WPF Button (ButtonAdv)

The [WPF Button](https://www.syncfusion.com/wpf-controls/button) control can also be used as a ToggleButton, similar to an on/off switch, when the [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property is set to **true**. The WPF Button is implemented through the `ButtonAdv` class. The default value of this property is **false**.

N> In addition to the [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property, the [IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsChecked) property lets you check the WPF Button by default. During initial rendering, the WPF Button appears in the **on** state when you use the latter property.

{% tabs %}
{% highlight xaml %}

<syncfusion:ButtonAdv Label="Log-in" SmallIcon="image/employee.png" SizeMode="Normal" IsCheckable="True" IsChecked="True"/>

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();
button.Label = "Log-in";
button.SizeMode = SizeMode.Normal;
button.SmallIcon = new BitmapImage(new Uri("employee.png"));
button.IsCheckable = true;
button.IsChecked = true;

{% endhighlight %}
{% endtabs %}

![Checkable Image](Checkable-Support_images/Checkable-Support_img1.png)

Checkable Button control
{:.caption}
