---
layout: post
title: Maximum and Minimum Value| DoubleTextBox  | Wpf | Syncfusion
description: maximum and minimum value
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Maximum and Minimum Value

## MinValue

Minimum allowed value for the DoubleTextBox. If the new [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is greater than the MaxValue property value, then the MaxValue is set equal to the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html). If the Value is less than the new [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html), then the Value property is also set equal to the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html).

## MaxValue

Maximum allowed value for the DoubleTextBox. If the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property is greater than the new [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property, then the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is set equal to the [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html). If the current Value is greater than the new [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html), then the Value property is set equal to the [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html).

## MinValidation

You can validate the MinValue in two ways:

* OnKeyPress – [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) of the DoubleTextBox is validated on the key press.
* OnLostFocus – [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) of the DoubleTextBox is validated on the lost focus only.

## MaxValidation


You can validate the MaxValue in two ways:

* OnKeyPress – [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the key press.
* OnLostFocus – [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the lost focus only.

## MinValueOnExceedMinDigit


If this property is set to true, then when you enter a value less than the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) then it will automatically assign the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) to the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. Otherwise it will not allow the key press.

Note: This will be enabled only when the MinValidation is set to OnKeyPress.


## MaxValueOnExceedMaxDigit

If this property is set to true, then when you enter a value greater than the MaxValue then it will automatically assign the [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) to the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. Otherwise it will not allow the key press.

Note: This will be enabled only when the MaxValidation is set to OnKeyPress.



{% highlight xaml %} <syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150"                             MinValue="-999" MaxValue="999"                             MinValidation="OnKeyPress" MaxValidation="OnLostFocus"                            MinValueOnExceedMinDigit="True"                             MaxValueOnExceedMaxDigit="True"/> {% endhighlight %} 

{% highlight C# %} Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();doubleTextBox.Width = 150;doubleTextBox.Height = 25;doubleTextBox.MinValue = -999;doubleTextBox.MaxValue = 999;doubleTextBox.MinValidation = Syncfusion.Windows.Shared.MinValidation.OnKeyPress;doubleTextBox.MaxValidation = Syncfusion.Windows.Shared.MaxValidation.OnLostFocus;doubleTextBox.MinValueOnExceedMinDigit = true;doubleTextBox.MaxValueOnExceedMaxDigit = true; {% endhighlight %} 



Initially there is no value assigned to the DoubleTextBox. So it displays the default value as zero.



![Max value on exceed max digit](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img1.png)





MaxValidation is set to OnLostFocus, so the MaxValidation will be performed only in the lost focus.



![MaxValidation is set to OnLostFocus](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img2.png)





MinValidation is set to OnKeyPress, so you cannot enter a value less than the MinValue. If you try to enter a value less than the MinValue, then the MinValue will set to the Value property because MinValueOnExceedMinDigit is set to true.



![MinValidation is set to OnKeyPress](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img3.png)



{% seealso %}

NullValue support

Binding support

{% endseealso %}