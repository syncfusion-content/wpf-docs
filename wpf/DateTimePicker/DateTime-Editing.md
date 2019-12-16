---
layout: post
title: WPF DateTimeEdit Editing modes | Syncfusion
description: Editing mode supports default text editing and mask mode that helps to restrict the date input in formatted values based on a date-time pattern.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime editing

The **DateTimeEdit** control provides support for editing DateTime using text box. It supports both free flow editing and mask based editing. 

## Mask editing

This is the default editing mode. In this mode, you can provide only valid input. Any invalid input given will be automatically corrected or ignored. The mask edit mode provides an easy and reliable way of collecting user input and displaying standard data in a specific format. In mask editing mode, the date will be separated into different fields such as date, month, year, minutes, hours, and seconds. The field can be updated by selecting the field and pressing the up or down arrow to increase or decrease the selected field respectively.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"/>

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit mask editing](Editing-Support_images/wpf-datetimeedit-mask-mode.png)

### Validation

In mask editing mode, value will be validated and corrected immediately based on the edited input value.  The following table demonstrates some of the validation in DateTimeEdit control:

<table>
<tr>
<th>
{{'**Validation**'| markdownify }} </th><th>
{{'**Example**'| markdownify }} </th></tr>
<tr>
<td>
If the Space or next field character is pressed, focus will automatically navigated to next valid date / time field that can be edited.</td><td>
In short pattern, "/" character is used as the date separators: MM/dd/yyyy. On pressing "/" the focus will automatically navigated to next valid field.</td></tr>
<tr>
<td>
Field focus will be automatically navigated when value of the selected field is filled.</td><td>
<img src="Editing-Support_images/wpf-datetimeedit-automatic-navigation.gif" alt="WPF DateTimeEdit automatic navigation"> </td></tr>
<tr>
<td>
DateTimeEdit value will be validated and corrected immediately based on the edited input value.
</td><td>
<img src="Editing-Support_images/wpf-datetimeedit-automatic-validation.gif" alt="WPF DateTimeEdit automatic validation">

Ex: If the month field is February, then if we type 29 in day field year field will be automatically validated and moved to next leap year based on corresponding date.</td></tr>
<tr>
<td>
Month field which is in abbreviated form, can be edited when pressing number keys(1- 12) and initial letter of respective month.</td><td>
Pressing the {{'**j**'| markdownify }} key selects {{'**January**'| markdownify }}. On subsequent presses of the {{'**j**'| markdownify }} key selects {{'**June**'| markdownify }} and then {{'**July**'| markdownify }}.</td></tr>
<tr>
<td>
Day field of DateTimeEdit can not be selected as it cannot be edited.</td><td>
- </td></tr>
</table>

## Free flow editing

The DateTime value can be edited like a normal textbox editing when the [CanEdit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CanEdit.html) is true. Input given by an end-user, will be validated when pressing Enter key or if control lost its focus. If the entered value is invalid, it set the previously SelectedDate as [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) value. Otherwise, it will accept the given input.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         CanEdit="True"/>

{% endhighlight %}

{% highlight C# %}

dateTimeEdit.CanEdit = true;

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit default editing](Editing-Support_images/wpf-datetimeedit-default-mode.png)


