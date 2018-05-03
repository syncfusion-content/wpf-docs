---
layout: post
title: Getting Started with Syncfusion DoubleTextBox control for WPF
description: A quick tour to initial users on Syncfusion DoubleTextBox control for WPF
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Getting Started

This section explains how to add the `DoubleTextBox` control to an application and its structure.

## Adding DoubleTextBox to a WPF application

`DoubleTextBox` can be added to an application in the following way.

### Create the DoubleTextBox control to an application by using XAML

The following ways explains how to add DoubleTextBox control using XAML code:

* Create a WPF project in Visual Studio and refer `Syncfusion.Shared.Wpf` assembly to the project.    
* Include an XML namespace for the above assemblies to the Main window. 

{% tabs %}

{% highlight XAML %}

<Window x:Class="Application_New.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
Title="MainWindow" Height="350" Width="525">

{% endhighlight %}

{% endtabs %}

* Now add the DoubleTextBox control with a required optimal name using the namespace 

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="TextBox" Width="100" Height="23" />

{% endhighlight %}

{% endtabs %}


![](Getting-Started-images/Getting-Started-img1.jpeg)


### Create the DoubleTextBox control to an application by C#:

The following code illustrate how to add DoubleTextBox control to an application by C#.

{% tabs %}

{% highlight C# %}

DoubleTextBox textBox = new DoubleTextBox();
textBox.Width = 100;
textBox.Height = 23;
Grid1.Children.Add(textBox);

{% endhighlight %}

{% endtabs %}


## DoubleTextBox member

DoubleTextBox exposes the following members:

### Properties

<table>
<tr>
<th>
Name</th><th>
Type</th><th>
DataType</th><th>
Description</th><th>
DefaultValue</th>
</tr>
<tr>
<td>
ApplyNegativeForeground<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or sets the value that determines whether to apply the NegativeForeground in the DoubleTextBox.<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
ApplyZeroColor<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or sets the value that determines whether to apply the ZeroColor in the DoubleTextBox<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
CornerRadius<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
CornerRadius<br/><br/></td><td>
Gets or sets a value that represents the degree to which the corners of the DoubleTextBox are rounded.<br/><br/></td><td>
0.<br/><br/></td></tr>
<tr>
<td>
Culture<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
CultureInfo<br/><br/></td><td>
Gets or sets the Culture information associated with the DoubleTextBox.<br/><br/></td><td>
CultureInfo.CurrentCulture<br/><br/></td></tr>
<tr>
<td>
EnterToMoveNext<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the EnterToMoveNext property.If this is set to true then the Enter key is used to change the focus from one field to another.<br/><br/></td><td>
true<br/><br/></td></tr>
<tr>
<td>
IsReadOnly<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or sets the value that determines if the user can change the value in the DoubleTextBox.<br/><br/></td><td>
true<br/><br/></td></tr>
<tr>
<td>
IsScrollingOnCircle<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the IsScrollingOnCircle property The spin behavior in the DoubleTextBox can be enabled or disabled by setting the IsScrollingOnCircle property.<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
NegativeForeground<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets the NegativeForeground property.<br/><br/></td><td>
Red<br/><br/></td></tr>
<tr>
<td>
NullValue<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Double?<br/><br/></td><td>
Gets or sets the NullValue property.<br/><br/></td><td>
Null<br/><br/></td></tr>
<tr>
<td>
NumberFormat<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
NumberFormatInfo<br/><br/></td><td>
A NumberFormat that defines the culturally appropriate format of displaying numbers, currency, and percentage.<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
MaxValue<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets the maximum value for the DoubleTextBox.<br/><br/></td><td>
1.7976931348623157E+308<br/><br/></td></tr>
<tr>
<td>
MaxValidation<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Enum of type MaxValidation<br/><br/></td><td>
Represents the Maximum value Validation constraint for the DoubleTextBox.<br/><br/></td><td>
MaxValidation.OnKeyPress<br/><br/></td></tr>
<tr>
<td>
MaxValueOnExceedMaxDigit<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Represents the behavior when the value exceeds the MaxValue.<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
MinValue<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets the minimum allowed value for the DoubleTextBox.<br/><br/></td><td>
-(1.7976931348623157E+308.)<br/><br/></td></tr>
<tr>
<td>
MinValueOnExceedMinDigit<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Represents the behavior when the Value exceeds the MinValue.<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
MinValidation<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Enum of type MinValidation<br/><br/></td><td>
Represents the Minimum value Validation constraint for the DoubleTextBox.<br/><br/></td><td>
MinValidation.OnKeyPress<br/><br/></td></tr>
<tr>
<td>
NumberDecimalDigits<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td><td>
Gets or sets the number of decimal places to use in the Value.<br/><br/></td><td>
2<br/><br/></td></tr>
<tr>
<td>
NumberDecimalSeparator<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
string<br/><br/></td><td>
Gets or sets the string to use as the decimal separator in the Value.<br/><br/></td><td>
String.Empty<br/><br/></td></tr>
<tr>
<td>
NumberGroupSeparator<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets the string that separates groups of digits in the value.<br/><br/></td><td>
String.Empty<br/><br/></td></tr>
<tr>
<td>
NumberGroupSizes<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int32Collection<br/><br/></td><td>
Gets or sets the number of digits in each group to the left of the decimal in the value.<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
PositiveForeground<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets the Foreground for the DoubleTextBox.<br/><br/></td><td>
Black<br/><br/></td></tr>
<tr>
<td>
SelectedText<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets the current selection in the DoubleTextBox.<br/><br/></td><td>
Empty String.<br/><br/></td></tr>
<tr>
<td>
SelectionStart<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td><td>
Gets or sets a character index for the beginning of the current selection.<br/><br/></td><td>
0<br/><br/></td></tr>
<tr>
<td>
SelectionLength<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td><td>
Gets or sets a value indicating the number of characters in the current selection in the DoubleTextBox.<br/><br/></td><td>
0<br/><br/></td></tr>
<tr>
<td>
TextSelectionOnFocus<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
If this property is set to true, then it will select all the text in the CurrencyTextBox when it gets focused.<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
UseNullOption<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Disable or enable the NullValue support in the DoubleTextBox.<br/><br/></td><td>
False<br/><br/></td></tr>
<tr>
<td>
Value<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Double?<br/><br/></td><td>
Gets or sets the value for the DoubleTextBox.<br/><br/></td><td>
0<br/><br/></td></tr>
<tr>
<td>
WatermarkOpacity<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Double<br/><br/></td><td>
Gets or sets the opacity of the WatermarkText in the DoubleTextBox.<br/><br/></td><td>
0.5<br/><br/></td></tr>
<tr>
<td>
WatermarkTemplate<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
DateTemplate<br/><br/></td><td>
Gets or sets the DataTemplate for the WatermarkText.<br/><br/></td><td>
Null<br/><br/></td></tr>
<tr>
<td>
WatermarkText<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets the WatermarkTextProperty.<br/><br/></td><td>
Empty String<br/><br/></td></tr>
<tr>
<td>
WatermarkTextForeground<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets the Foreground for the WatermarkText.<br/><br/></td><td>
Transparent<br/><br/></td></tr>
<tr>
<td>
WatermarkTextIsVisible<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or sets the value that determines the visibility of the WatermarkText in the DoubleTextBox.<br/><br/></td><td>
False<br/><br/></td></tr>
<tr>
<td>
ZeroColor<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets the ZeroColor property.<br/><br/></td><td>
Green<br/><br/></td></tr>
<tr>
<td>
RangeAdornerBackground<br/><br/></td><td>
. Dependency Property<br/><br/></td><td>
Brush<br/><br/></td><td>
Gets or sets the RangeBackground property<br/><br/></td><td>
LightGray<br/><br/></td></tr>
<tr>
<td>
EnableRangeAdorner<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or sets the EnableRangeAdorner property.<br/><br/></td><td>
False.<br/><br/></td></tr>
<tr>
<td>
IsCaretAnimationEnabled<br/><br/></td><td>
Dependency property<br/><br/></td><td>
bool <br/><br/></td><td>
Gets or sets the IsCaretAnimationEnabled property<br/><br/></td><td>
False.<br/><br/></td></tr>
<tr>
<td>
EnableExtendedScrolling<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the EnableExtendedScrolling property<br/><br/></td><td>
False<br/><br/></td></tr>
<tr>
<td>
EnableFocusColor<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the EnableFocusColor property<br/><br/></td><td>
False<br/><br/></td></tr>
<tr>
<td>
EnableTouch<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the EnableTouch property<br/><br/></td><td>
False.<br/><br/></td></tr>
<tr>
<td>
Scrolling Interval<br/><br/></td><td>
Dependency property<br/><br/></td><td>
double<br/><br/></td><td>
Gets or Sets the ScrollingInterval property<br/><br/></td><td>
1.0<br/><br/></td></tr>
<tr>
<td>
Step<br/><br/></td><td>
Dependency<br/><br/></td><td>
double<br/><br/></td><td>
Gets or Sets the Step property<br/><br/></td><td>
1.0<br/><br/></td></tr>
<tr>
<td>
GroupSeparatorEnabled <br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the GroupSeparatorEnabled property<br/><br/></td><td>
True<br/><br/></td></tr>
<tr>
<td>
ValidationCompleted<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Bool<br/><br/></td><td>
Gets or Sets the ValidationCompleted property<br/><br/></td><td>
False<br/><br/></td></tr>
<tr>
<td>
ValueValidation<br/><br/></td><td>
Dependency property<br/><br/></td><td>
StringValidation<br/><br/></td><td>
Gets or Sets the ValueValidation property<br/><br/></td><td>
StringValidation.OnLostFocus().<br/><br/></td></tr>
<tr>
<td>
InvalidValueBehavior<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
InvalidInputBehavior<br/><br/></td><td>
Gets or Sets the InvalidValueBehavior<br/><br/></td><td>
InvalidInputBehavior.None<br/><br/></td></tr>
<tr>
<td>
ValidationValue<br/><br/></td><td>
Dependency property<br/><br/></td><td>
String<br/><br/></td><td>
Gets or Sets the ValidationValue<br/><br/></td><td>
String.Empty<br/><br/></td></tr>
</table>

### Methods

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Return Type</th><th>
Overloads</th></tr>
<tr>
<td>
Copy()<br/><br/></td><td>
Copies the current selection of the DoubleTextBox to the Clipboard.<br/><br/></td><td>
Void<br/><br/></td><td>
Zero parameter<br/><br/></td></tr>
<tr>
<td>
Select()<br/><br/></td><td>
Selects a range of text in the DoubleTextBox.<br/><br/></td><td>
Void<br/><br/></td><td>
(+2) Overloads.Parameters:start (Int32):First character in the selection.Length:The length of the selection, in characters.<br/><br/></td></tr>
<tr>
<td>
SelectAll()<br/><br/></td><td>
Selects all the content of the DoubleTextBox.<br/><br/></td><td>
Void<br/><br/></td><td>
Zero parameter<br/><br/></td></tr>
</table>

### Events

<table>
<tr>
<th>
Name</th><th>
Event Type</th><th>
Event Args Parameter</th><th>
Description</th></tr>
<tr>
<td>
ValueChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the value of the DoubleTextBox has changed.<br/><br/></td></tr>
<tr>
<td>
TextChanged<br/><br/></td><td>
TextChangedEventHandler<br/><br/></td><td>
TextChangedEventArgs<br/><br/></td><td>
Occurs when the text changes in the DoubleTextBox.<br/><br/></td></tr>
<tr>
<td>
CultureChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the Culture of the DoubleTextBox has changed.<br/><br/></td></tr>
<tr>
<td>
MaxValueChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the MaxValue of the DoubleTextBox has changed.<br/><br/></td></tr>
<tr>
<td>
MinValueChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the MinValue of the DoubleTextBox has changed.<br/><br/></td></tr>
<tr>
<td>
SelectionChanged<br/><br/></td><td>
RoutedEventHandler<br/><br/></td><td>
RoutedEventArgs<br/><br/></td><td>
Occurs when the text selection has changed.<br/><br/></td></tr>
<tr>
<td>
ValueChanging<br/><br/></td><td>
ValueChangingEventHandler<br/><br/></td><td>
ValueChangingEventArgs<br/><br/></td><td>
Occurs before the value of the DoubleTextBox has changed.<br/><br/></td></tr>
<tr>
<td>
NumberDecimalDigitsChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the number of decimal digits changed.<br/><br/></td></tr>
<tr>
<td>
NumberDecimalSeparatorChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the decimal separator of the number changed<br/><br/></td></tr>
<tr>
<td>
NumberGroupSeparatorChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the Group Separator of the number changed.<br/><br/></td></tr>
<tr>
<td>
NumberGroupSizesChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the group size of the number changed<br/><br/></td></tr>
<tr>
<td>
ValidationCompletedChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the validation completed.<br/><br/></td></tr>
<tr>
<td>
ValidationValueChanged<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td><td>
DependencyPropertyChangedEventArgs<br/><br/></td><td>
Occurs after the validation value changed.<br/><br/></td></tr>
</table>
