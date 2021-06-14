---
layout: post
title: Restriction or Validation in WPF Percent TextBox control | Syncfusion
description: Learn about Restriction or Validation support in Syncfusion WPF Percent TextBox control, its elements and more.
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Restriction or Validation in WPF Percent TextBox

This section explains how to validate or restrict the `PercentTextBox` control value.

## Restrict the value within minimum and maximum value

The [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) of the [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) can be restricted within the maximum and minimum limits. Once the percent value has reached the maximum or minimum value , the value does not exceed the limit. We can change the maximum and minimum limits by using the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_MinValue) property and [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_MaxValue) property.

You can choose when to validate the maximum and minimum limits while changing the percent values by using the [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MinValidation) and [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MaxValidation) properties.

* `OnKeyPress` — When setting the `MaxValidation` or `MinValidation` to `OnKeyPress`, the percent value in the `PercentTextBox` will be validated shortly after pressing a key. So, it is not possible to provide any invalid input at all and the percent value does not exceed the maximum and minimum limits.

* `OnLostFocus` - When setting `MaxValidation` or `MinValidation` to `OnLostFocus`, the percent value in the `PercentTextBox` is validated, when the `PercentTextBox` loses the focus. That is, the `PercentTextBox` will accept any percent value, validation will only take place after the `PercentTextBox` has lost its keyboard focus. After validation, when the percent value of the `PercentTextBox` is greater than the `MaxValue` or less than the `MinValue`, the percent value will be automatically set to `MaxValue` or `MinValue`.

* [MaxValueOnExceedMaxDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MaxValueOnExceedMaxDigit) - When you give input greater than specified maximum limit, `MaxValueOnExceedMaxDigit` property will decide either it should retain the old percent value or reset to maximum limit that is specified. For example, if `MaxValue` is set to 100 and you are trying to input 200. `PercentValue` will changed to 100 when `MaxValueOnExceedMaxDigit` is `true`. When `MaxValueOnExceedMaxDigit` is `false`, 20 will be retained and last entered 0 will be ignored.

  N> `MaxValueOnExceedMinDigit` property will be enabled only when the `MaxValidation` is set to `OnKeyPress`.

* [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MinValueOnExceedMinDigit) - When you give input less than specified minimum limit, `MinValueOnExceedMinDigit` property will decide either it should retain the old percent value or reset to minimum limit that is specified. For example, if `MinValue` is set to 200 and the `PercentValue` is 205 and you are trying change the percent value to 20. `PercentValue` will changed to 200 when `MinValueOnExceedMinDigit` is `true`. When `MinValueOnExceedMinDigit` is `false`, Old percent value 205 will be retained.

  N> `MinValueOnExceedMinDigit` will be enabled only when the `MinValidation` is set to `OnKeyPress`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150" MaxValue="100" MinValue="10"
                          MinValueOnExceedMinDigit="True" MaxValueOnExceedMaxDigit="True"
                          MinValidation="OnKeyPress" MaxValidation="OnLostFocus"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.MinValue = 10;
percentTextBox.MaxValue =100;
percentTextBox.MinValidation = MinValidation.OnKeyPress;
percentTextBox.MaxValidation = MaxValidation.OnLostFocus;
percentTextBox.MinValueOnExceedMinDigit = true;
percentTextBox.MaxValueOnExceedMaxDigit = true;

{% endhighlight %}
{% endtabs %}

`MinValidation` is set to OnKeyPress, it cannot let to enter a percent value less than the `MinValue`. If try to enter a percent value less than the `MinValue`, then the `MinValue` will set to the `PercentValue` property because `MinValueOnExceedMinDigit` is set to `true`.

![Validate minimun value of PercentTextBox on pressing a key](Restriction-or-Validation_images/Restriction-or-Validation_MinValidation.jpeg)

`MaxValidation` is set to OnLostFocus, so the `MaxValidation` will be performed only in the lost focus.

![Validate maximum value of PercentTextBox when keyboard focus is lost](Restriction-or-Validation_images/Restriction-or-Validation_MaxValidation.jpeg)

## Restrict number of decimal digit

## Restrict number of decimal digit

You can change the decimal digits of text property in the `PercentTextBox` control using `PercentDecimalDigits` property. You can restrict the decimal digits of `Text` property value within maximum and minimum decimal digits in `PercentTextBox` control using `MinPercentDecimalDigits` and `MaxPercentDecimalDigits` properties. The default value of `MinPercentDecimalDigits`,`MaxPercentDecimalDigits` and `DoubleDecimalDigits` properties is **-1**.

N> If value of `MinPercentDecimalDigits` property is greater than `MaxPercentDecimalDigits` property value, then text of `PercentTextBox` will be updated based on `MinPercentDecimalDigits` property value.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox Value="125.32545" HorizontalAlignment="Center" VerticalAlignment="Center"
                            MaxPercentDecimalDigits="4"
                            MinPercentDecimalDigits="1" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Value = 125.32545;
percentTextBox.MaxPercentDecimalDigits = 4;
percentTextBox.MinPercentDecimalDigits = 1;

{% endhighlight %}
{% endtabs %}

![PercentTextBox in read-only mode](Restriction-or-Validation_images/maxandmin_decimaldigits.png)

When `MinPercentDecimalDigits`, `MaxPercentDecimalDigits` and `PercentDecimalDigits` are specified, `PercentDecimalDigits` property takes higher precedence and updates the text of `PercentTextBox` property. 

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox Value="125.32545" HorizontalAlignment="Center" VerticalAlignment="Center"
                            MaxPercentDecimalDigits="4"
                            MinPercentDecimalDigits="1" 
                            PercentDecimalDigits="3"
                            />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Value = 125.32545;
percentTextBox.MaxPercentDecimalDigits = 4;
percentTextBox.MinPercentDecimalDigits = 1;
percentTextBox.PercentDecimalDigits = 3;

{% endhighlight %}
{% endtabs %}

![PercentTextBox in read-only mode](Restriction-or-Validation_images/number_decimalDigits.png)

## Read only mode

The `PercentTextBox` cannot allow the user input, edits when [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) property is sets to `true`. The user can still select text and display the cursor on the `PercentTextBox` by setting the [IsReadOnlyCaretVisible](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonlycaretvisible?view=netframework-4.8) property to `true`. However, value can be changed programmatically in readonly mode.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" IsReadOnly="True" PercentValue="10" IsReadOnlyCaretVisible="True"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.PercentValue = 10;
percentTextBox.IsReadOnly = true;
percentTextBox.IsReadOnlyCaretVisible = true;

{% endhighlight %}
{% endtabs %}

![PercentTextBox in read-only mode](Restriction-or-Validation_images/Restriction-or-Validation_ReadOnly.jpeg)
