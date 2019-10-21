---
layout: post
title: Culture and Formatting in WPF DoubleTextBox control | Syncfusion
description: Learn about Culture and Formatting support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Culture and Formatting in WPF DoubleTextBox

## Setting the Culture

The `DoubleTextBox` provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~Culture.html) property. The `Culture` property is used to format the decimal separator and group separator of the `DoubleTextBox` value based on the respective culture.

**US Culture**

The US culture uses “,” as the `NumberGroupSeparator` and "." as the `NumberDecimalSeparator`.

{%tabs%}
{% highlight xaml %} 

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" Culture="en-US" Value="1234567"/>

{% endhighlight %}
{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.Culture = new System.Globalization.CultureInfo("en-US");

{% endhighlight %}
{%endtabs%}

![Setting DoubleTextBox US-Culture](Culture-and-Number-Formats-images/Culture-and-Number-Formats-img1.jpeg)

**Latin Culture**

The Latin culture uses “.” as the `NumberGroupSeparator` and "," as the `NumberDecimalSeparator`.

{%tabs%}
{% highlight xaml %} 

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>

{% endhighlight %}
{% highlight C# %} 

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.Culture = new System.Globalization.CultureInfo("bs-Latn");

{% endhighlight %}
{%endtabs%}

![Setting DoubleTextBox Latin-Culture](Culture-and-Number-Formats-images/Culture-and-Number-Formats-Latin.jpeg)


## Setting the Format

The number formatting of `DoubleTextBox` can be customized by setting [DoubleTextBox.NumberFormat](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.editorbase~NumberFormat.html) property or by specifying the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSeparator.html), [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSizes.html), [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html), and [NumberDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalSeparator.html) properties. You can show the group separator by enable the [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~GroupSeperatorEnabled.html) property to `true`.


{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="200" Value="1234567"
                          GroupSeperatorEnabled = "True">

<syncfusion:DoubleTextBox.NumberFormat>
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


The following code illustrate how to set `NumberGroupSeparator`, `NumberDecimalDigits` and `NumberDecimalSeparator`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="200" Value="1234567"
                          NumberGroupSeparator="/" NumberDecimalDigits="4"
                          NumberDecimalSeparator="*"/>


{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 200;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.NumberGroupSeparator = "/";
doubleTextBox.NumberDecimalSeparator = "*";
doubleTextBox.NumberDecimalDigits = 4;

{% endhighlight %}
{% endtabs %}

![Setting the DoubleTextBox number format](Culture-and-Number-Formats-images/Culture-and-Number-Formats-img3.jpeg)


N> When you use both `NumberFormat` and  `Culture`, the `NumberFormat` will have a higher priority.
