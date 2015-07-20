---
layout: post
title: Minimum-and-Maximum-Value
description: minimum and maximum value
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Minimum and Maximum Value

## MinValue

Minimum allowed value for the IntegerTextBox. If the new MinValue property value is greater than the MaxValue property value, then the MaxValue is set equal to the MinValue. If the Value is less than the new MinValue, then the Value property is also set equal to the MinValue.

## MaxValue

Maximum allowed value for the IntegerTextBox. If the MinValue property is greater than the new MaxValue property, then the MinValue property value is set equal to the MaxValue. If the current Value is greater than the new MaxValue, then the Value property is set equal to the Maxvalue.

## MinValidation

You can validate the MinValue in two ways:

* OnKeyPress – MinValue of the IntegerTextBox is validated on the key press.
* OnLostFocus – MinValue of the IntegerTextBox is validated on the lost focus only.
## MaxValidation


You can validate the MaxValue in two ways:

* OnKeyPress – MaxValue of the IntegerTextBox is validated on the key press.
* OnLostFocus – MaxValue of the IntegerTextBox is validated on the lost focus only.
## MinValueOnExceedMinDigit


If this property is set to true, then when you enter a value less than the MinValue then it will automatically assign the MinValue to the Value property. Otherwise it will not allow the key press.

> _Note: This will be enabled only when the MinValidation is set to OnKeyPress._

## MaxValueOnExceedMaxDigit

If this property is set to true, then when you enter a value greater than the MaxValue then it will automatically assign the MaxValue to the Value property. Otherwise it will not allow the key press.

> _Note: This will be enabled only when the MaxValidation is set to OnKeyPress._



<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             MinValue="-999" MaxValue="999"                             MinValidation="OnKeyPress" MaxValidation="OnLostFocus"                            MinValueOnExceedMinDigit="True"                             MaxValueOnExceedMaxDigit="True"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.MinValue = -999;integerTextBox.MaxValue = 999;integerTextBox.MinValidation = Syncfusion.Windows.Shared.MinValidation.OnKeyPress;integerTextBox.MaxValidation = Syncfusion.Windows.Shared.MaxValidation.OnLostFocus;integerTextBox.MinValueOnExceedMinDigit = true;integerTextBox.MaxValueOnExceedMaxDigit = true;</td></tr>
</table>


Initially there is no value assigned to the IntegerTextBox. So it displays the default value as zero.

{ ![](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img1.png) | markdownify }
{:.image }


MaxValidation is set to OnLostFocus, so the MaxValidation will be performed only in the lost focus.

{ ![](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img2.png) | markdownify }
{:.image }


MinValidation is set to OnKeyPress, so you cannot enter a value less than the MinValue. If you try to enter a value less than the MinValue, then the MinValue will set to the Value property because MinValueOnExceedMinDigit is set to true.

{ ![](Minimum-and-Maximum-Value_images/Minimum-and-Maximum-Value_img3.png) | markdownify }
{:.image }


See Also

Nullvalue support

Culture and NumberFormats

