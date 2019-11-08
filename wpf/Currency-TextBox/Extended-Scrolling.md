---
layout: post
title: Extended Scrolling | CurrencyTextBox | wpf | Syncfusion
description: Extended scrolling represents the customization of the CurrencyTextBox value by mouse click and mouse move 
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Extended Scrolling

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is used to change the values based on the click and drag direction of the mouse movements. The range will increase when the mouse moves to the right or top of the screen, and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state.

![Extended scrolling](Extended-Scrolling_images/Extended-Scrolling_img1.png)

## Adding extended scrolling

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property must be set either in XAML or the code file.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="93" EnableExtendedScrolling = "true" />

{% endhighlight %}
  
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Value = 93;
currencyTextBox.EnableExtendedScrolling = true

{% endhighlight %}
{% endtabs %}
