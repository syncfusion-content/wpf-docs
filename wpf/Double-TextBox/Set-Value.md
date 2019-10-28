---
layout: post
title: Set the Value | DoubleTextBox | WPF | Syncfusion
description: Learn how to set the values in DoubleTextBox control for WPF
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Set Value

This section describes about how to set the value in the DoubleTextBox

## Value

The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is used to set the value for the DoubleTextBox.

N> Do not use the [Text](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textbox.text?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_TextBox_Text) property to set the value for the DoubleTextBox. Use only the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="textBox" Width="100" Height="23" Value="100"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox textBox = new DoubleTextBox();
textBox.Width = 100;
textBox.Height = 23;
textBox.Value = 100;
Grid1.Children.Add(textBox);

{% endhighlight %}

{% highlight VB %}

Dim textBox As DoubleTextBox =  New DoubleTextBox() 
textBox.Width = 100
textBox.Height = 23
textBox.Value = 100
Grid1.Children.Add(textBox)

{% endhighlight %}

{% endtabs %}

![Double text box value](Set-Value-images/Set-Value-img1.jpeg)

## UseNullOption

DoubleTextBox accepts null values. To enable the null option, the [UseNullOption](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~UseNullOption.html) property need to set to `true`. By default its value is `false`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="170" UseNullOption="True" />

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 170;
doubleTextBox.Height = 25;
doubleTextBox.UseNullOption = true;
Grid1.Children.Add(doubleTextBox);

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 170
doubleTextBox.Height = 25
doubleTextBox.UseNullOption = True
Grid1.Children.Add(doubleTextBox)

{% endhighlight %}

{% endtabs %}

![Double text box null option](Set-Value-images/Set-Value-img2.jpeg)

## NullValue

To set the value, when the value of the DoubleTextBox is null the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NullValue.html) property is used. On setting the value to the [NullValue]([NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NullValue.html)) property, it will assigned to the Value property.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="150" UseNullOption="True" NullValue="10"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.NullValue = 10;
Grid1.Children.Add(doubleTextBox);

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.NullValue = 10
Grid1.Children.Add(doubleTextBox)

{% endhighlight %}

{% endtabs %}

![Double text box null value](Set-Value-images/Set-Value-img3.jpeg)

## Minimum value

Minimum allowed value for the DoubleTextBox. If the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is greater than the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property value, then the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) is set equal to the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html). If the Value is less than the new [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html), then the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is also set equal to the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html).

## Maximum value

Maximum allowed value for the DoubleTextBox. If the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property is greater than the new [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property, then the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property value is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html). If the current Value is greater than the new MaxValue, then the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is set equal to the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html).

## Setting minimum and maximum value

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
Grid1.Children.Add(textBox);

{% endhighlight %}

{% highlight VB %}

Dim textBox As DoubleTextBox =  New DoubleTextBox() 
textBox.Width = 100
textBox.Height = 23
textBox.Value = 100
textBox.MaxValue = 999.99
textBox.MinValue = -999.99
Grid1.Children.Add(textBox)

{% endhighlight %}

{% endtabs %}

## MinValidation

MinValue can be validate in two ways.

* OnKeyPress – MinValue of the DoubleTextBox is validated on the key press.
* OnLostFocus – MinValue of the DoubleTextBox is validated on the lost focus only.

## MaxValidation

The MaxValue can validate in two ways:

* OnKeyPress – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the key press.
* OnLostFocus – [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) of the DoubleTextBox is validated on the lost focus only.

## MinValueOnExceedMinDigit

If `MinValueOnExceedMinDigit` property is set to `true`, a value less than the MinValue entered, then it will automatically assign the MinValue to the Value property. Otherwise it will not allow the key press.

N> This will be enabled only when the MinValidation is set to OnKeyPress.

## MaxValueOnExceedMaxDigit

If `MaxValueOnExceedMaxDigit` property is set to `true`, then a value greater than the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) is entered, it will automatically assign the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) to the Value property. Otherwise it will not allow the key press.

N> This will be enabled only when the MaxValidation is set to OnKeyPress.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" MaxValue="100" MinValue="10"
						  MinValueOnExceedMinDigit="True" MaxValueOnExceedMaxDigit="True"
						  MinValidation="OnKeyPress" MaxValidation="OnLostFocus"/>


{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 10;
doubleTextBox.MaxValue =100;
doubleTextBox.MinValidation = Syncfusion.Windows.Shared.MinValidation.OnKeyPress;
doubleTextBox.MaxValidation = Syncfusion.Windows.Shared.MaxValidation.OnLostFocus;
doubleTextBox.MinValueOnExceedMinDigit = true;
doubleTextBox.MaxValueOnExceedMaxDigit = true;
Grid1.Children.Add(doubleTextBox);

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
Grid1.Children.Add(doubleTextBox)

{% endhighlight %}

{% endtabs %}

Initially there is no value assigned to the DoubleTextBox. So it displays the default value as zero.

![No value assigned to double text box](Set-Value-images/Set-Value-img4.jpeg)


MaxValidation is set to OnLostFocus, so the MaxValidation will be performed only in the lost focus.

![MaxValidation is set to OnLostFocus](Set-Value-images/Set-Value-img5.jpeg)


MinValidation is set to OnKeyPress, it cannot let to enter a value less than the MinValue. If try to enter a value less than the MinValue, then the MinValue will set to the Value property because MinValueOnExceedMinDigit is set to true.

![MinValidation is set to OnKeyPress](Set-Value-images/Set-Value-img6.jpeg)


## Value changed

[ValueChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ValueChanged_EV.html) – The event occurs when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property of the DoubleTextBox is changed.

{% tabs %}

{% highlight Xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox"
                          ValueChanged="doubleTextBox_ValueChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValueChanged+=doubleTextBox_ValueChanged;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.ValueChanged+=doubleTextBox_ValueChanged

{% endhighlight %}

{% endtabs %}

The ValueChanged event can be handled as follows:

{% tabs %}

{% highlight C# %}

private void doubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

// Insert code to do some operations when the value property is changed 
}

{% endhighlight %}

{% highlight VB %}

Private  Sub doubleTextBox_ValueChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs)
 
' Insert code to do some operations when the value property is changed 
End Sub

{% endhighlight %}

{% endtabs %}

## Text changed

[TextChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.textchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the `Value` property of the DoubleTextBox is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox TextChanged="DoubleTextBox_TextChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.TextChanged+=doubleTextBox_TextChanged;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.TextChanged+=doubleTextBox_TextChanged

{% endhighlight %}

{% endtabs %}

The TextChanged event can be handled as follows

{% tabs %}

{% highlight C# %}

private void DoubleTextBox_TextChanged(object sender, TextChangedEventArgs e)

{

// Insert code to do some operations when the Text property is changed 
}

{% endhighlight %}

{% highlight VB %}

Private  Sub DoubleTextBox_TextChanged(ByVal sender As Object, ByVal e As TextChangedEventArgs)
 
' Insert code to do some operations when the Text property is changed 
End Sub

{% endhighlight %}

{% endtabs %}

## Culture changed

[CultureChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CultureChanged_EV.html) – The event occurs when the `Culture` property of the DoubleTextBox is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox CultureChanged="DoubleTextBox_CultureChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.CultureChanged += doubleTextBox_CultureChanged;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.CultureChanged += doubleTextBox_CultureChanged

{% endhighlight %}

{% endtabs %}

The CultureChanged event can be handled as follows

{% tabs %}

{% highlight C# %}

private void DoubleTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{

// Insert code to do some operations when the culture property is changed 
}

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.CultureChanged += doubleTextBox_CultureChangedPrivate  Sub DoubleTextBox_CultureChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs)
 
' Insert code to do some operations when the culture property is changed 
End Sub


{% endhighlight %}

{% endtabs %}

## Maximum value changed

[MaxValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValueChanged_EV.html) – The event occurs when the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property of the DoubleTextBox is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox MaxValueChanged="DoubleTextBox_MaxValueChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MaxValueChanged += doubleTextBox_MaxValueChanged;


{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.MaxValueChanged += doubleTextBox_MaxValueChanged

{% endhighlight %}

{% endtabs %}

To handle the MaxValueChanged event, use the following code.

{% tabs %}

{% highlight C# %}

private void DoubleTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{      

// Insert code to do some operations when the MaxValue property is changed 

}

{% endhighlight %}

{% highlight VB %}

Private  Sub DoubleTextBox_MaxValueChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs)      
 
' Insert code to do some operations when the MaxValue property is changed 
End Sub

{% endhighlight %}

{% endtabs %}

## Minimum value changed

[MinValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValueChanged_EV.html) – The event occurs when the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property of the DoubleTextBox is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox MinValueChanged="DoubleTextBox_MinValueChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValueChanged += doubleTextBox_MinValueChanged;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.MinValueChanged += doubleTextBox_MinValueChanged

{% endhighlight %}

{% endtabs %}

To handle the MinValueChanged event, use this follow code below

{% tabs %}

{% highlight C# %}

private void DoubleTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{

// Insert code to do some operations when the MinValue property is changed 

}

{% endhighlight %}

{% highlight VB %}

Private  Sub DoubleTextBox_MinValueChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs)
 
' Insert code to do some operations when the MinValue property is changed 
End Sub

{% endhighlight %}

{% endtabs %}

## NumberDecimalDigits changed

[NumberDecimalDigitsChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigitsChanged_EV.html) – The event occurs when the [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html) property of the DoubleTextBox gets changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox NumberDecimalDigitsChanged="DoubleTextBox_NumberDecimalDigitsChanged" />

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.NumberDecimalDigitsChanged += DoubleTextBox_NumberDecimalDigitsChanged;

{% endhighlight %}

{% highlight VB %}

Private doubleTextBox As DoubleTextBox = New DoubleTextBox()
doubleTextBox.NumberDecimalDigitsChanged += DoubleTextBox_NumberDecimalDigitsChanged;

{% endhighlight %}

{% endtabs %}

To handle the NumberDecimalDigitsChanged, use this follow code below.

{% tabs %}

{% highlight C# %}


private void DoubleTextBox_NumberDecimalDigitsChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
           
// Insert code to do some operations when the NumberDecimalDigits property is changed 
}

{% endhighlight %}

{% highlight VB %}

Private Sub DoubleTextBox_NumberDecimalDigitsChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs) 
' Insert code to do some operations when th NumberDecimalDigits  property is changed 
 
End Sub


{% endhighlight %}

{% endtabs %}


## Selection changed

[SelectionChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the selection in the textbox is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox SelectionChanged="DoubleTextBox_SelectionChanged"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.SelectionChanged += doubleTextBox_SelectionChanged;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.SelectionChanged += doubleTextBox_SelectionChanged

{% endhighlight %}

{% endtabs %}

To handle the SelectionChanged, the following code is used.

{% tabs %}

{% highlight C# %}

private void DoubleTextBox_SelectionChanged(object sender, RoutedEventArgs e)
{

// Insert code to do some operations when the selection changed.
}

{% endhighlight %}

{% highlight VB %}

Private  Sub DoubleTextBox_SelectionChanged(ByVal sender As Object, ByVal e As RoutedEventArgs)
 
' Insert code to do some operations when the selection changed.
End Sub

{% endhighlight %}

{% endtabs %}
