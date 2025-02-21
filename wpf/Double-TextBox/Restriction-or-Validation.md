---
layout: post
title: Restriction or Validation in WPF Double TextBox control | Syncfusion®
description: Learn about Restriction or Validation support in Syncfusion® WPF Double TextBox control, its elements and more.
platform: WPF
control: DoubleTextBox 
documentation: ug
---

# Restriction or Validation in WPF Double TextBox

This section explains how to validate or restrict the `DoubleTextBox` control value.

## Restrict the value within minimum and maximum value

The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) of the [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) can be restricted within the maximum and minimum limits. Once the value has reached the maximum or minimum value , the value does not exceed the limit. We can change the maximum and minimum limits by using the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MinValue) property and [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MaxValue) property.

You can choose when to validate the maximum and minimum limits while changing the values by using the [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MinValidation) and [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MaxValidation) properties.

* `OnKeyPress` — When setting the `MaxValidation` or `MinValidation` to `OnKeyPress`, the value in the `DoubleTextBox` will be validated shortly after pressing a key. So, it is not possible to provide any invalid input at all and the value does not exceed the maximum and minimum limits.

* `OnLostFocus` - When setting `MaxValidation` or `MinValidation` to `OnLostFocus`, the value in the `DoubleTextBox` is validated, when the `DoubleTextBox` loses the focus. That is, the `DoubleTextBox` will accept any value, validation will only take place after the `DoubleTextBox` has lost its keyboard focus. After validation, when the value of the `DoubleTextBox` is greater than the `MaxValue` or less than the `MinValue`, the value will be automatically set to `MaxValue` or `MinValue`.

* [MaxValueOnExceedMaxDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MaxValueOnExceedMaxDigit) - When you give input greater than specified maximum limit, `MaxValueOnExceedMaxDigit` property will decide either it should retain the old value or reset to maximum limit that is specified. For example, if `MaxValue` is set to 100 and you are trying to input 200. `Value` will changed to 100 when `MaxValueOnExceedMaxDigit` is `true`. When `MaxValueOnExceedMaxDigit` is `false`, 20 will be retained and last entered 0 will be ignored.

  N> `MaxValueOnExceedMinDigit` property will be enabled only when the `MaxValidation` is set to `OnKeyPress`.

* [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_MinValueOnExceedMinDigit) - When you give input less than specified minimum limit, `MinValueOnExceedMinDigit` property will decide either it should retain the old value or reset to minimum limit that is specified. For example, if `MinValue` is set to 200 and the `Value` is 205 and you are trying change the value to 20. `Value` will changed to 200 when `MinValueOnExceedMinDigit` is `true`. When `MinValueOnExceedMinDigit` is `false`, Old value 205 will be retained.

  N> `MinValueOnExceedMinDigit` will be enabled only when the `MinValidation` is set to `OnKeyPress`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" MaxValue="100" MinValue="10"
                          MinValueOnExceedMinDigit="True" MaxValueOnExceedMaxDigit="True"
                          MinValidation="OnKeyPress" MaxValidation="OnLostFocus"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 10;
doubleTextBox.MaxValue =100;
doubleTextBox.MinValidation = MinValidation.OnKeyPress;
doubleTextBox.MaxValidation = MaxValidation.OnLostFocus;
doubleTextBox.MinValueOnExceedMinDigit = true;
doubleTextBox.MaxValueOnExceedMaxDigit = true;

{% endhighlight %}
{% endtabs %}

`MinValidation` is set to OnKeyPress, it cannot let to enter a value less than the `MinValue`. If try to enter a value less than the `MinValue`, then the `MinValue` will set to the `Value` property because `MinValueOnExceedMinDigit` is set to `true`.

![Validate minimun value of DoubleTextBox on pressing a key](Restriction-or-Validation_images/wpf-double-textbox-min-value-validation.jpeg)

`MaxValidation` is set to OnLostFocus, so the `MaxValidation` will be performed only in the lost focus.

![Validate maximum value of DoubleTextBox when keyboard focus is lost](Restriction-or-Validation_images/wpf-double-textbox-max-value-validation.jpeg)

## Restrict number of decimal digit

You can format the decimal digits in the [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) control using [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NumberDecimalDigits) property. You can restrict the decimal digits of the text within maximum and minimum limits in `DoubleTextBox` control using [MinimumNumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MinimumNumberDecimalDigits) and [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MaximumNumberDecimalDigits) properties. The default value of `MinimumNumberDecimalDigits`,`MaximumNumberDecimalDigits` and `DoubleDecimalDigits` properties is **-1**.

N> If the value of `MinimumNumberDecimalDigits` property is greater than the value of `MaximumNumberDecimalDigits` property, the text of `DoubleTextBox` will be updated based on the value of `MinimumNumberDecimalDigits` property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox Value="125.32545" HorizontalAlignment="Center" VerticalAlignment="Center"
                            MaximumNumberDecimalDigits="4"
                            MinimumNumberDecimalDigits="1" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Value = 125.32545;
doubleTextBox.MaximumNumberDecimalDigits = 4;
doubleTextBox.MinimumNumberDecimalDigits = 1;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox WPF restricts the number of decimal digits](Restriction-or-Validation_images/doubletextbox-wpf-restrict-numberof-decimal-digits.png)

When value of `MinimumNumberDecimalDigits`, `MaximumNumberDecimalDigits` and `NumberDecimalDigits` properties are specified, `NumberDecimalDigits` property takes high precedence and updates the text of `DoubleTextBox` property. 

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox Value="125.32545" HorizontalAlignment="Center" VerticalAlignment="Center"
                            MaximumNumberDecimalDigits="4"
                            MinimumNumberDecimalDigits="1" 
                            NumberDecimalDigits="3"
                            />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Value = 125.32545;
doubleTextBox.MaximumNumberDecimalDigits = 4;
doubleTextBox.MinimumNumberDecimalDigits = 1;
doubleTextBox.NumberDecimalDigits = 3;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox WPF change decimal digits](Restriction-or-Validation_images/doubletextbox-wpf-decimaldigits.png)

## Read only mode

The `DoubleTextBox` cannot allow the user input, edits when [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) property is sets to `true`. The user can still select text and display the cursor on the `DoubleTextBox` by setting the [IsReadOnlyCaretVisible](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonlycaretvisible?view=netframework-4.8) property to `true`. However, value can be changed programmatically in readonly mode.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" IsReadOnly="True" Value="10" IsReadOnlyCaretVisible="True"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Value = 10;
doubleTextBox.IsReadOnly = true;
doubleTextBox.IsReadOnlyCaretVisible = true;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox in read-only mode](Restriction-or-Validation_images/wpf-double-textbox-read-only.jpeg)
