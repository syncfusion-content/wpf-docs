---
layout: post
title: WPF DateTimeEdit Editing modes | Syncfusion
description: Editing mode supports default text editing and mask mode that helps to restrict the date input in formatted values based on a date-time pattern.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime editing

The DateTime value of the `DateTimeEdit` control can be updated by editing the text in the control. The [CanEdit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CanEdit.html) decides how to insert the input values for the DateTimeEdit from the keyboard. The DateTimeText can be edited by two ways as follows:

* Default editing
* Mask editing

## Default editing

The DateTime can be edited in the textbox of the `DateTimeEdit` control when the [CanEdit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CanEdit.html) is true. In default editing mode, the value can be assigned in any valid format. Even if the text box text is not in the correct pattern, the DateTimeEdit control automatically updates the value in the correct pattern on lost focus. i.e, if the date time pattern is LongDate with pattern "dddd, MMMM dd, yyyy" and date is entered as "Mar 28 2017" in the editing text box, the DateTimeText will be automatically converted according to the LongDate pattern while pressing the enter key or on lost focus of the control.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" CanEdit="True"  DateTime="2/3/2019"/>

{% endhighlight %}

{% highlight C# %}

dateTimeEdit.CanEdit = true;

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit default editing](Editing-Support_images/wpf-datetimeedit-default-mode.png)

## Mask editing

The mask edit mode provides an easy and reliable way of collecting user input and displaying standard data in a specific format. In mask editing mode, the date will be separated into different fields such as date, month, year, minutes, hours, and seconds. The field can be updated by selecting the field and pressing the up or down arrow to increase or decrease the selected field respectively.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="2/3/2019"/>

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit mask editing](Editing-Support_images/wpf-datetimeedit-mask-mode.png)

### Validation

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
<img src="Editing-Support_images/wpf-datetimeedit-automatic-validation.gif" alt="WPF DateTimeEdit automatic validation"></td></tr>
<tr>
<td>
Month field which is in abbreviated form, can be edited when pressing number keys(1- 12) and initial letter of respective month.</td><td>
Pressing the {{'**j**'| markdownify }} key selects {{'**January**'| markdownify }}. On subsequent presses of the {{'**j**'| markdownify }} key selects {{'**June**'| markdownify }} and then {{'**July**'| markdownify }}.</td></tr>
<tr>
<td>
Day field of DateTimeEdit can not be selected as it cannot be edited.</td><td>
- </td></tr>
</table>