---
layout: post
title: Maximum and Minimum Value| PercentTextBox  | Wpf | Syncfusion
description: maximum and minimum value
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Maximum and Minimum Value

## MinValue

Minimum allowed PercentValue for the PercentTextBox. If the new MinValue property value is greater than the MaxValue property value, then the MaxValue is set equal to the MinValue. If the Value is less than the new MinValue, then the Value property is also set equal to the MinValue.

## MaxValue

Maximum allowed PercentValue for the PercentTextBox. If the MinValue property is greater than the new MaxValue property, then the MinValue property value is set equal to the MaxValue. If the current Value is greater than the new MaxValue, then the Value property is set equal to the MaxValue.

## MinValidation

You can validate the MinValue in two ways:

* OnKeyPress – MinValue of the PercentTextBox is validated on the key press.
* OnLostFocus – MinValue of the PercentTextBox is validated on the lost focus only.

## MaxValidation

You can validate the MaxValue in two ways:

* OnKeyPress – MaxValue of the PercentTextBox is validated on the key press.
* OnLostFocus – MaxValue of the PercentTextBox is validated on the lost focus only.

## MinValueOnExceedMinDigit

If this property is set to true, then when you enter a value less than the MinValue then it will automatically assign the MinValue to the PercentValue property. Otherwise it will not allow the key press.

N> This will be enabled only when the MinValidation is set to OnKeyPress.

## MaxValueOnExceedMaxDigit

If this property is set to true, then when you enter a value greater than the MaxValue then it will automatically assign the MaxValue to the PercentValue property. Otherwise it will not allow the key press.

N> This will be enabled only when the MaxValidation is set to OnKeyPress.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"      
                       MinValue="-999" MaxValue="999"    
					   MinValidation="OnKeyPress" MaxValidation="OnLostFocus"    
					   MinValueOnExceedMinDigit="True"                        
					   MaxValueOnExceedMaxDigit="True"/>{% endhighlight %}

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;percentTextBox.Height = 25;
percentTextBox.MinValue = -999.99;percentTextBox.MaxValue = 999.99;
percentTextBox.MinValidation = MinValidation.OnKeyPress;
percentTextBox.MaxValidation = MaxValidation.OnLostFocus;
percentTextBox.MinValueOnExceedMinDigit = true;
percentTextBox.MaxValueOnExceedMaxDigit = true;
{% endhighlight %}
{% endtabs %}


Initially there is no value assigned to the PercentTextBox. So it displays the default value as zero.

![](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img1.png)


MaxValidation is set to OnLostFocus, so the MaxValidation will be performed only in the lost focus.

![](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img2.png)


MinValidation is set to OnKeyPress, so you cannot enter a value less than the MinValue. If you try to enter a value less than the MinValue, then the MinValue will be set to the PercentValue property if the MinValueOnExceedMinDigit is set to true, otherwise it will not allow the key press.

![](Maximum-and-Minimum-Value_images/Maximum-and-Minimum-Value_img3.png)

