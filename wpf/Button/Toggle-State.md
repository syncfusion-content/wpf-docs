---
layout: post
title: Toggle State in WPF Button control | Syncfusion
description: Learn here all about Toggle State support in Syncfusion WPF Button (ButtonAdv) control and more.
platform: wpf
control: ButtonAdv
documentation: ug
---

# Toggle State in WPF Button (ButtonAdv)

The button control can also be used as a toggle button, similar to the on/off view when the [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property is set to **true**. The default value of this property is **false**.

N> In addition to [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property, the [IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsChecked) property helps to check the button by default. In other words, during initial rendering, the button will appear in **on** state using the later property.

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
