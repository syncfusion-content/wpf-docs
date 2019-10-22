---
layout: post
title: Restriction or Validation in WPF DoubleTextBox control | Syncfusion
description: Learn about Restriction or Validation support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Restriction or Validation in WPF DoubleTextBox

This section explains how to validate or restrict the `DoubleTextBox` control value.

## Restrict the value within minimum and maximum value

The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) of the [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) can be restricted within the maximum and minimum limits. Once the value has reached the maximum or minimum value , the value does not exceed the limit. We can change the maximum and minimum limits by using the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property and [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property.

You can choose when to validate the maximum and minimum limits while changing the values by using the [MinValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MinValidation.html) and [MaxValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MaxValidation.html) properties.

* `OnKeyPress` — When setting the `MaxValidation` or `MinValidation` to `OnKeyPress`, the value in the `DoubleTextBox` will be validated shortly after pressing a key. So, it is not possible to provide any invalid input at all and the value does not exceed the maximum and minimum limits.

* `OnLostFocus` - When setting `MaxValidation` or `MinValidation` to `OnLostFocus`, the value in the `DoubleTextBox` is validated when the `DoubleTextBox` loses the focus. That is, the `DoubleTextBox` will accept any value, validation will only take place after the `DoubleTextBox` has lost its keyboard focus. After validation, when the value of the `DoubleTextBox` is greater than the `MaxValue` or less than the `MinValue`, the value will be automatically set to `MaxValue` or `MinValue`.

* [MaxValueOnExceedMaxDigit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~MaxValueOnExceedMaxDigit.html) - When you give input greater than specified maximum limit, `MaxValueOnExceedMaxDigit` property will decide either it should retain the old value or reset to maximum limit that is specified. For example, if `MaxValue` is set to 100 and you are trying to input 200. `Value` will changed to 100 when `MaxValueOnExceedMaxDigit` is `true`. When `MaxValueOnExceedMaxDigit` is `false`, 20 will be retained and last entered 0 will be ignored.

  N> `MaxValueOnExceedMinDigit` property will be enabled only when the `MaxValidation` is set to `OnKeyPress`.

* [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~MinValueOnExceedMinDigit.html) - When you give input less than specified minimum limit, `MinValueOnExceedMinDigit` property will decide either it should retain the old value or reset to minimum limit that is specified. For example, if `MinValue` is set to 200 and the `Value` is 205 and you are trying change the value to 20. `Value` will changed to 200 when `MinValueOnExceedMinDigit` is `true`. When `MinValueOnExceedMinDigit` is `false`, Old value 205 will be retained.

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

![MinValidation of DoubleTextBox On KeyPress](Restriction-or-Validation_images/Restriction-or-Validation_MinValidation.jpeg)

`MaxValidation` is set to OnLostFocus, so the `MaxValidation` will be performed only in the lost focus.

![MaxValidation of DoubleTextBox On LostFocus](Restriction-or-Validation_images/Restriction-or-Validation_MaxValidation.jpeg)




## Restrict number of decimal digit

The `DoubleTextbox` allows the user to customize the number of digits to be displayed after the decimal point of `DoubleTextBox` value
by using [NumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html) property.
The decimal digit can be restricted within the maximum and minimum limits. Once the decimal digit has reached the maximum or minimum digit , the decimal digits does not exceed the limit. We can change the maximum and minimum decimal digits limit by using the [MinimumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinimumNumberDecimalDigits.html) and [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaximumNumberDecimalDigits.html)

{% tabs %}
{% highlight xaml %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" 
                          NumberDecimalDigits = 4 MinimumNumberDecimalDigits = 2
                          MaximumNumberDecimalDigits = 5/>
{% endhighlight %}

{% highlight c# %}
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.NumberDecimalDigits = 4;
doubleTextBox.MinimumNumberDecimalDigits = 2;
doubleTextBox.MaximumNumberDecimalDigits = 5;
{% endhighlight %}
{% endtabs %}


![DoubleTextBox limits the number of decimal digits](Restriction-or-Validation_images/DecimalDigits.png)

N> `NumberDecimalDigits` property value will be allows set based on the in-between range of `MinimumNumberDecimalDigits` and `MaximumNumberDecimalDigits` property values.

## Read only mode

The `DoubleTextBox` cannot allow the user input or edits and programmatic changes can be made when [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) property is sets to `true`. The user can still select text and the cursor on the `DoubleTextBox` can be displayed by setting the [IsReadOnlyCaretVisible](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonlycaretvisible?view=netframework-4.8) property to `true`.


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

![DoubleTextBox read-only mode enabled](Restriction-or-Validation_images/Restriction-or-Validation_ReadOnly.jpeg)

## Validate Invalid Value

You can use the [ValidationValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~ValidationValue.html) property to compare the value of the `DoubleTextBox` with a specific value. If the value of `DoubleTextBox` is not equal to the `ValidationValue` property, the `DoubleTextBox` will be perform some operation. This is achieved by the [InvalidValueBehavior](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~InvalidValueBehavior.html) property.

It includes the following three behaviors,

* Display ErrorMessage
* None
* Reset Value

### Display ErrorMessage  

If the value entered by the user is not equal to `ValidationValue`, the error message will be shown by setting the `InvalidValueBehavior` property as `DisplayErrorMessage`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" ValidationValue = "5.5" InvalidValueBehavior="DisplayErrorMessage" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValidationValue = "5.5";
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.DisplayErrorMessage;

{% endhighlight %}
{% endtabs %}

![After entering the incorrect value, DoubleTextBox Display the pop-up ErrorMessage](Restriction-or-Validation_images/Error-message.png)

### Reset Value  

If the value entered by the user is not equal to `ValidationValue`, the `DoubleTextBox` value will be reset with the `ValidationValue` by setting the `InvalidValueBehavior` property as `ResetValue`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox"  InvalidValueBehavior="ResetValue" ValidationValue = "3.75" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValidationValue = "3.75";
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.ResetValue;

{% endhighlight %}
{% endtabs %}

![After entering the incorrect value, DoubleTextBox resets the value](Restriction-or-Validation_images/Reset-Value.png)


