---
layout: post
title: Multiline Text Support in WPF Button | Syncfusion®
description: Multiline text support in WPF Button (ButtonAdv) enables displaying Button content across multiple lines.
platform: wpf
control: ButtonAdv
documentation: ug
---

# Multiline Text in WPF Button (ButtonAdv)

The [WPF Button](https://www.syncfusion.com/wpf-controls/button) control supports rendering text across multiple lines. The WPF Button is implemented through the [ButtonAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html) class. You can enable multiline text by using the [IsMultiLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsMultiLine) property.

N> This property is applicable only when the WPF Button is in large size mode.

{% tabs %}
{% highlight XAML %}

<syncfusion:ButtonAdv x:Name="ButtonAdv" IsMultiLine="True" LargeIcon="image1/employee.png" Label="Sign in with your Syncfusion Account" SizeMode="Large" />

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();
button.SizeMode = SizeMode.Large;
button.LargeIcon = new BitmapImage(new Uri("employee.png"));
button.IsMultiLine="true";
button.Label = "Sign in with your Syncfusion Account";

{% endhighlight %}
{% endtabs %}

![WPF Button MultiLine](Multi-Line-Support_images/Multi-Line-Support_img1.png)
