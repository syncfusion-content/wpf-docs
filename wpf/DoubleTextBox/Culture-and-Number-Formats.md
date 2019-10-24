---
layout: post
title: Culture and Formatting in WPF DoubleTextBox control | Syncfusion
description: Learn about Culture and Formatting support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Culture and Formatting in WPF DoubleTextBox

This section explains how to format the value in the `DoubleTextBox` control based on culture and number format.

## Setting Culture

The [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~Culture.html) property. The `Culture` property is used to format the decimal separator and group separator of the `DoubleTextBox` value based on the respective culture.

{%tabs%}
{% highlight xaml %} 

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>

{% endhighlight %}
{% highlight C# %} 

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;

//Setting Latin culture for double textbox.
doubleTextBox.Culture = new System.Globalization.CultureInfo("bs-Latn");

{% endhighlight %}
{%endtabs%}

By default the US culture uses “,” as the `NumberGroupSeparator` and "." as the `NumberDecimalSeparator` where as the Latin culture uses “.” as the `NumberGroupSeparator` and "," as the `NumberDecimalSeparator`. 

**Default Culture**

![DoubleTextBox with default culture](Culture-and-Number-Formats-images/Culture-and-Number-Formats-img1.jpeg)

**Latin Culture**

![DoubleTextBox with Latin-Culture](Culture-and-Number-Formats-images/Latin.png)


## Formatting

The number formatting of `DoubleTextBox` can be customized by setting [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NumberFormat.html) property or by specifying the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSeparator.html), [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSizes.html), [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html), and [NumberDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalSeparator.html) properties. You can show the group separator by enable the [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~GroupSeperatorEnabled.html) property to `true`.


{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="200" Value="1234567"
                          GroupSeperatorEnabled = "True">

<syncfusion:DoubleTextBox.NumberFormat >
<numberformat:NumberFormatInfo NumberGroupSeparator="/"
              NumberDecimalDigits="4" NumberDecimalSeparator="*"/>
</syncfusion:DoubleTextBox.NumberFormat>

</syncfusion:DoubleTextBox>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 200;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.GroupSeperatorEnabled = true;
doubleTextBox.NumberFormat = new NumberFormatInfo()
{
    NumberGroupSeparator = "/",
    NumberDecimalDigits = 4,
    NumberDecimalSeparator = "*"
};

{% endhighlight %}
{% endtabs %}

![Setting DoubleTextBox number format by NumberFormatInfo](Culture-and-Number-Formats-images/Culture-and-Number-Formats-img2.jpeg)


The following code illustrate how to set number group size by using the `NumberFormat` property.

{% tabs %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 200;
doubleTextBox.Height = 25;
doubleTextBox.Value = 123456789;
doubleTextBox.NumberFormat = new System.Globalization.NumberFormatInfo()
{
    NumberDecimalDigits =4,
    NumberGroupSeparator = "/",
    NumberDecimalSeparator = "*",
    
    // Adding the Number group size via NumberFormat property.
    NumberGroupSizes = new int[] { 2, 3, 4 }
};
{% endhighlight %}
{% endtabs %}

![Setting DoubleTextBox number group size by NumberFormat](Culture-and-Number-Formats-images/NumberGroupSizes_format.png)

The following code illustrate how to set number group size by using the `NumberGroupSizes` property of the `DoubleTextBox`.

{% tabs %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 123456789;
doubleTextBox.NumberGroupSeparator = "/";
doubleTextBox.NumberDecimalSeparator = "*";
doubleTextBox.NumberDecimalDigits = 3;

// Adding the Number group size via NumberGroupSizes property.
doubleTextBox.NumberGroupSizes = new Int32Collection() { 4, 3, 2};

{% endhighlight %}
{% endtabs %}

![Setting DoubleTextBox number group size by NumberGroupSize collection](Culture-and-Number-Formats-images/NumberGroupSizes2.png)

N>When you use both the `NumberFormat` and the `NumberGroupSeparator`, `NumberGroupSizes`, `NumberDecimalDigits`, and `NumberDecimalSeparator` properties to customize the `DoubleTextbox` value format, the `NumberGroupSeparator`, `NumberGroupSizes`, `NumberDecimalDigits`, and `NumberDecimalSeparator` has higher priority.

N> When you use both `NumberFormat` and  `Culture`, the `NumberFormat` will have a higher priority.
