---
layout: post
title: Culture and Formatting in WPF IntegerTextBox control | Syncfusion
description: Learn about Culture and Formatting support in Syncfusion WPF IntegerTextBox control and more details about the control features.
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Culture and Formatting in WPF IntegerTextBox

Value of `IntegerTextBox` can be formatted in following ways:

* Culture
* NumberFormatInfo
* Dedicated properties (NumberGroupSeparator, NumberGroupSizes)

## Culture based formatting

The [IntegerTextBox](https://www.syncfusion.com/wpf-ui-controls/integer-textbox) provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_Culture) property. The `Culture` property is used to format the number group size and group separator of the `IntegerTextBox` value based on the respective culture.

{%tabs%}
{% highlight xaml %} 

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>

{% endhighlight %}
{% highlight C# %} 

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 1234567;

//Setting Latin culture for integer textbox.
integerTextBox.Culture = new System.Globalization.CultureInfo("bs-Latn");

{% endhighlight %}
{%endtabs%}

By default the US culture uses “,” as the `NumberGroupSeparator` where as the Latin culture uses “.” as the `NumberGroupSeparator`. 

**Default Culture**

![IntegerTextBox with Default Culture](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)

**Latin Culture**

![IntegerTextBox with Latin culture](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)

## NumberFormatInfo based formatting

The number formatting of `IntegerTextBox` can be customized by setting [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NumberFormat) property.

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="en-US"
                           Value="123456789012345" GroupSeperatorEnabled="True" >
    <syncfusion:IntegerTextBox.NumberFormat >
        <numberformat:NumberFormatInfo NumberGroupSeparator="/"/>
    </syncfusion:IntegerTextBox.NumberFormat>
</syncfusion:IntegerTextBox>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.GroupSeperatorEnabled = true;
integerTextBox.Value = 123456789012345;
integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");
integerTextBox.NumberFormat = new System.Globalization.NumberFormatInfo() 
{                                   
NumberGroupSeparator = "/"
};

{% endhighlight %}
{%endtabs%}

![Setting IntegerTextBox number format by NumberFormatInfo](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)

The following code illustrate how to set `NumberGroupSizes` by using the `NumberFormat`property.

{% tabs %}
{% highlight C# %}

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

![Setting IntegerTextBox number group size by NumberFormatInfo](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)

## Formatting with dedicated properties

The number formatting of `IntegerTextBox` can also be customized by setting the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NumberGroupSeparator) property and the [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NumberGroupSizes) property.
You can show the group separator by enable the [GroupSeperatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_GroupSeperatorEnabled) property to `true`.

The following code illustrate how to format using the `NumberGroupSeparator`, `NumberGroupSizes` property of the `IntegerTextBox`.

{% tabs %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 123456789012345;
integerTextBox.NumberGroupSeparator = "/";
integerTextBox.GroupSeperatorEnabled = true;
integerTextBox.NumberGroupSizes = new Int32Collection() { 2, 3, 0 };

{% endhighlight %}
{% endtabs %}

![Setting IntegerTextBox number format by dedicated properties](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img6.png)

N> When you use both the `NumberFormat` and the dedicated properties (`NumberGroupSeparator` and `NumberGroupSizes`) to format the value of `IntegerTextBox`, the `NumberGroupSeparator`and `NumberGroupSizes` properties have higher priority.

N> When you use both `NumberFormat` and  `Culture`, the `NumberFormat` will have a higher priority.
