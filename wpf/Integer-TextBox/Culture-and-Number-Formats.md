---
layout: post
title: Culture and Formatting in WPF IntegerTextBox | Syncfusion®
description: Format the integer value in the Syncfusion WPF IntegerTextBox control using culture settings, number formats, and grouping separators.
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Culture and Formatting in WPF Integer TextBox

Value of `WPF Integer TextBox` can be formatted in following ways:

* Culture
* NumberFormatInfo
* Dedicated properties (NumberGroupSeparator, NumberGroupSizes)

## Culture based formatting

The [WPF Integer TextBox](https://www.syncfusion.com/wpf-controls/integer-textbox) provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_Culture) property. The `Culture` property is used to format the number group size and group separator of the `WPF Integer TextBox` value based on the respective culture.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Globalization;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 1234567;

//Setting Latin culture for integer textbox.
integerTextBox.Culture = new CultureInfo("bs-Latn");

{% endhighlight %}
{% endtabs %}

By default the US culture uses “,” as the `NumberGroupSeparator`, whereas the Latin culture uses “.” as the `NumberGroupSeparator`.

**Default Culture**

![WPF IntegerTextBox with Default Culture](Culture-and-Number-Formats_images/wpf-integer-textbox-default-culture.png)

**Latin Culture**

![WPF IntegerTextBox with Latin culture](Culture-and-Number-Formats_images/wpf-integer-textbox-latin-culture.png)

## NumberFormatInfo based formatting

The number formatting of `WPF Integer TextBox` can be customized by setting the [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NumberFormat) property.

{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:numberformat="clr-namespace:System.Globalization;assembly=mscorlib"
        x:Class="IntegerTextBoxSample.MainWindow"
        Title="IntegerTextBox Sample" Height="350" Width="525">
    <Grid>
        <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="en-US"
                                   Value="123456789012345" GroupSeperatorEnabled="True" >
            <syncfusion:IntegerTextBox.NumberFormat>
                <numberformat:NumberFormatInfo NumberGroupSeparator="/"/>
            </syncfusion:IntegerTextBox.NumberFormat>
        </syncfusion:IntegerTextBox>
    </Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Globalization;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.GroupSeperatorEnabled = true;
integerTextBox.Value = 123456789012345;
integerTextBox.Culture = new CultureInfo("en-US");
integerTextBox.NumberFormat = new NumberFormatInfo()
{
    NumberGroupSeparator = "/"
};

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox with Formatting](Culture-and-Number-Formats_images/wpf-integer-textbox-formatting.png)

The following code illustrates how to set `NumberGroupSizes` by using the `NumberFormat` property.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Globalization;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 123456789012345;
integerTextBox.GroupSeperatorEnabled = true;
integerTextBox.NumberFormat = new NumberFormatInfo()
{
    NumberGroupSeparator = "/",
    NumberGroupSizes = new int[] { 2, 3, 4 }
};

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Different Group Size between Numbers](Culture-and-Number-Formats_images/wpf-integer-textbox-group-size.png)

## Formatting with dedicated properties

The number formatting of `IntegerTextBox` can also be customized by setting the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NumberGroupSeparator) and [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NumberGroupSizes) properties. You can show the group separator by enabling the [GroupSeperatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_GroupSeperatorEnabled) property to `true`. The default value of `GroupSeperatorEnabled` is `false`.

The following code illustrates how to format using the `NumberGroupSeparator` and `NumberGroupSizes` properties of the `WPF Integer TextBox`. Use a standard `int[]` for the `NumberGroupSizes` property.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 123456789012345;
integerTextBox.NumberGroupSeparator = "/";
integerTextBox.GroupSeperatorEnabled = true;
integerTextBox.NumberGroupSizes = new int[] { 2, 3, 0 };

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox with Formatting](Culture-and-Number-Formats_images/wpf-integer-textbox-number-format.png)

N> When you use both the `NumberFormat` and the dedicated properties (`NumberGroupSeparator` and `NumberGroupSizes`) to format the value of `WPF Integer TextBox`, the dedicated properties take priority over `NumberFormat`.

N> When you use both `NumberFormat` and `Culture`, the `NumberFormat` will have a higher priority.
