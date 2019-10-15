---
layout: post
title: Restriction or Validation| DoubleTextBox  | Wpf | Syncfusion
description: Restriction or Validation represents to restrict and validate the minimum, maximum values and value validation modes in the DoubleTextBox
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Restriction or Validation

## Restrict within min and max value

### Minimum value

Minimum allowed value for the DoubleTextBox. If the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is greater than the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property value, then the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) is set equal to the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html). If the Value is less than the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html), then the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is also set equal to the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html).

### Maximum value

Maximum allowed value for the DoubleTextBox. If the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property is greater than the new [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property, then the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html). If the current Value is greater than the new MaxValue, then the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html).

### Setting minimum and maximum value

The Minimum and Maximum value can be changed by using the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) and [MaxVal](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) properties of the DoubleTextBox.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1"
                          Width="100" Height="23" Value="100"
                          MaxValue="999.99" MinValue="-999.99"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox textBox = new DoubleTextBox();
textBox.Width = 100;
textBox.Height = 23;
textBox.Value = 100;
textBox.MaxValue = 999.99;
textBox.MinValue = -999.99;

{% endhighlight %}

{% highlight VB %}

Dim textBox As DoubleTextBox =  New DoubleTextBox() 
textBox.Width = 100
textBox.Height = 23
textBox.Value = 100
textBox.MaxValue = 999.99
textBox.MinValue = -999.99

{% endhighlight %}

{% endtabs %}

![Min Max value](Restriction-or-Validation_images/Restriction-or-Validation_MinMaxValue.jpeg)

### MinValidation

MinValue can be validate in two ways.

* OnKeyPress – MinValue of the DoubleTextBox is validated on the key press.
* OnLostFocus – MinValue of the DoubleTextBox is validated on the lost focus only.

### MaxValidation

The MaxValue can validate in two ways:

* OnKeyPress – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the key press.
* OnLostFocus – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the lost focus only.

### MinValueOnExceedMinDigit

If [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~MinValueOnExceedMinDigit.html) property is set to `true`, a value less than the MinValue entered, then it will automatically assign the MinValue to the Value property. Otherwise it will not allow the key press.

N> This will be enabled only when the MinValidation is set to OnKeyPress.

### MaxValueOnExceedMaxDigit

If `MaxValueOnExceedMaxDigit` property is set to `true`, then a value greater than the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) is entered, it will automatically assign the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) to the Value property. Otherwise it will not allow the key press.

N> This will be enabled only when the [MaxValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MaxValidation.html) is set to OnKeyPress.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" MaxValue="100" MinValue="10"
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

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.MinValue = 10
doubleTextBox.MaxValue =100
doubleTextBox.MinValidation = Syncfusion.Windows.Shared.MinValidation.OnKeyPress
doubleTextBox.MaxValidation = Syncfusion.Windows.Shared.MaxValidation.OnLostFocus
doubleTextBox.MinValueOnExceedMinDigit = True
doubleTextBox.MaxValueOnExceedMaxDigit = True

{% endhighlight %}

{% endtabs %}

Initially there is no value assigned to the DoubleTextBox. So it displays the default value as zero.

![No value assigned to double text box](Restriction-or-Validation_images/Restriction-or-Validation_No-Value.jpeg)


[MaxValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MaxValidation.html) is set to OnLostFocus, so the [MaxValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MaxValidation.html) will be performed only in the lost focus.

![MaxValidation is set to OnLostFocus](Restriction-or-Validation_images/Restriction-or-Validation_MaxValidation.jpeg)


[MinValidation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.MinValidation.html) is set to OnKeyPress, it cannot let to enter a value less than the MinValue. If try to enter a value less than the MinValue, then the MinValue will set to the Value property because MinValueOnExceedMinDigit is set to true.

![MinValidation is set to OnKeyPress](Restriction-or-Validation_images/Restriction-or-Validation_MinValidation.jpeg)

## Restrict number of decimal digit

### NumberDecimalDigits 

Number of decimal digits can be set for DoubleTextBox using [NumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html) property. [NumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html) property value will be set based on the in-between range of [MinimumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinimumNumberDecimalDigits.html) and [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaximumNumberDecimalDigits.html) property values.

### MinimumNumberDecimalDigits

If [MinimumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinimumNumberDecimalDigits.html) is set, the DoubleTextbox allows the user to enter the range of decimal digits from [MinimumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinimumNumberDecimalDigits.html).

### MaximumNumberDecimalDigits

If [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaximumNumberDecimalDigits.html) is set, the DoubleTextbox allows users to enter [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaximumNumberDecimalDigits.html) in the decimal range.


{% tabs %}
{% highlight xaml %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" 
                          NumberDecimalDigits = 4 MinimumNumberDecimalDigits = 2					   MaximumNumberDecimalDigits = 5/>
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


![DecimalDigits](Restriction-or-Validation_images/DecimalDigits.png)


## Read only value

If the DoubleTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. DoubleTextBox allows to apply the different background brushes using the [ReadOnlyBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ReadOnlyBackground.html) property. The user can still select text and the cursor still appears. 

N> The Cursor in the DoubleTextBox can be displayed by setting the `IsReadOnlyCaretVisible` property to true.

To enable this feature set [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) to `true`. By default its value is `false`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" ReadOnlyBackground="Orange" IsReadOnly="True" IsReadOnlyCaretVisible="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.IsReadOnly = true;
doubleTextBox.IsReadOnlyCaretVisible = true;
doubleTextBox.ReadOnlyBackground = Brushes.Orange;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.IsReadOnly = True
doubleTextBox.IsReadOnlyCaretVisible = true
doubleTextBox.ReadOnlyBackground = Brushes.Orange

{% endhighlight %}

{% endtabs %}

![readonly](Restriction-or-Validation_images/ReadOnly.png)

## Validate Invalid Value

The [InvalidValueBehavior](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~InvalidValueBehavior.html) property is used to alert the user when the input data is wrong.

It includes the following three behaviors,

* DisplayErrorMessage
* None
* ResetValue

### DisplayErrorMessage  

If [InvalidValueBehavior](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~InvalidValueBehavior.html) property is `DisplayErrorMessage`, the error message will be shown when the user enters incorrect data.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" InvalidValueBehavior="DisplayErrorMessage" />

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.DisplayErrorMessage;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox()
doubleTextBox.MinValue = 0
doubleTextBox.MaxValue = 100
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.DisplayErrorMessage;

{% endhighlight %}

{% endtabs %}

### None  

If [InvalidValueBehavior](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~InvalidValueBehavior.html) property is `None`, when the user enters incorrect input data, no operations can occur.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" InvalidValueBehavior="None" MaxValue= "100" MinValue="0" />

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.None;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.MinValue = 0
doubleTextBox.MaxValue = 100
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.None;

{% endhighlight %}

{% endtabs %}


### ResetValue  

If the [InvalidValueBehavior](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~InvalidValueBehavior.html)  property is `ResetValue`, if incorrect input data is entered, the DoubleTextBox resets the value to the default value.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox"  InvalidValueBehavior="ResetValue" MaxValue= "100" MinValue="0"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.ResetValue;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.MinValue = 0
doubleTextBox.MaxValue = 100
doubleTextBox.InvalidValueBehavior = InvalidInputBehavior.ResetValue;

{% endhighlight %}

{% endtabs %}


