---
layout: post
title: Minimum and Maximum Value | IntegerTextBox | wpf | Syncfusion
description: minimum and maximum value
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Minimum and Maximum Value

## MinValue

Minimum allowed value for the IntegerTextBox. If the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) property value is greater than the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) property value, then the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) is set equal to the MinValue. If the Value is less than the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html), then the Value property is also set equal to the MinValue.

## MaxValue

Maximum allowed value for the IntegerTextBox. If the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) property is greater than the new MaxValue property, then the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) property value is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html). If the current Value is greater than the new MaxValue, then the Value property is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html).

## MinValidation

You can validate the MinValue in two ways:

* OnKeyPress – [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) of the IntegerTextBox is validated on the key press.
* OnLostFocus – [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) of the IntegerTextBox is validated on the lost focus only.


## MaxValidation


You can validate the MaxValue in two ways:

* OnKeyPress – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) of the IntegerTextBox is validated on the key press.
* OnLostFocus – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) of the IntegerTextBox is validated on the lost focus only.


## MinValueOnExceedMinDigit


If this property is set to true, then when you enter a value less than the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) then it will automatically assign the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) to the Value property. Otherwise it will not allow the key press.

N> This will be enabled only when the MinValidation is set to OnKeyPress.

## MaxValueOnExceedMaxDigit

If this property is set to true, then when you enter a value greater than the MaxValue then it will automatically assign the MaxValue to the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property. Otherwise it will not allow the key press.

N> This will be enabled only when the MaxValidation is set to OnKeyPress.

{%tabs%}

{% highlight xaml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             MinValue="-999" MaxValue="999"                             MinValidation="OnKeyPress" MaxValidation="OnLostFocus"                            MinValueOnExceedMinDigit="True"                             MaxValueOnExceedMaxDigit="True"/>{% endhighlight %}

{% highlight C# %} Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.MinValue = -999;integerTextBox.MaxValue = 999;integerTextBox.MinValidation = Syncfusion.Windows.Shared.MinValidation.OnKeyPress;integerTextBox.MaxValidation = Syncfusion.Windows.Shared.MaxValidation.OnLostFocus;integerTextBox.MinValueOnExceedMinDigit = true;integerTextBox.MaxValueOnExceedMaxDigit = true;{% endhighlight %}

{%endtabs%}

Initially there is no value assigned to the IntegerTextBox. So it displays the default value as zero.

![Integer text box has no value](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img1.png)



MaxValidation is set to OnLostFocus, so the MaxValidation will be performed only in the lost focus.

![MaxValidation is set to OnLostFocus](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img2.png)



MinValidation is set to OnKeyPress, so you cannot enter a value less than the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html). If you try to enter a value less than the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html), then the MinValue will set to the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property because [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~MinValueOnExceedMinDigit.html) is set to true.

![MinValidation is set to OnKeyPress](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img3.png)



{%seealso%}

NullValue support

Culture and NumberFormats

{%endseealso%}

