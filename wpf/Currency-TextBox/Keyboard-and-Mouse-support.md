---
layout: post
title: Keyboard and Mouse support | CurrencyTextBox | wpf | Syncfusion
description: keyboard and mouse support represents the customization of the CurrencyTextBox value by keyboard buttons and mouse scrolling
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Keyboard and Mouse Support

Up or down arrows in the CurrencyTextBox spin the values one step up or down. Mouse Scroll in the CurrencyTextBox spin values one step up or down. The spin behavior in the CurrencyTextBox can be enabled by setting the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property to true.

The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~ScrollInterval.html) property is used to set spin value of CurrencyTextBox. Based on the [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~ScrollInterval.html) value, CurrencyTextBox spins up or down.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="150" Height="25" Value="8"
                            IsScrollingOnCircle="True" ScrollInterval="2"/>

{% endhighlight %}

{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 8;
currencyTextBox.IsScrollingOnCircle = true;
currencyTextBox.ScrollInterval = 2;
{% endhighlight %}

{% endtabs %}

![Keyboard and Mouse Support](Keyboard-and-Mouse-Support_images/Keyboard-and-Mouse-Support_img1.png)
