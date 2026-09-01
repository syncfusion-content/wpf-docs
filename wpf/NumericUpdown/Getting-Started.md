---
layout: post
title: Getting Started with WPF UpDown | Syncfusion®
description: Learn how to get started with the Syncfusion WPF UpDown control. Explore setup, features, examples, and customization options.
platform: wpf
control: UpDown
documentation: ug
---
# Getting Started with WPF Numeric UpDown

This section explains how to create the [WPF Numeric UpDown](https://www.syncfusion.com/wpf-controls/numericupdown) control and describes its structure.

## Structure of WPF Numeric UpDown

![WPF UpDown Control](gettingstarted-images/wpf-updown-structure.jpeg)

The following are the elements of the WPF Numeric UpDown control:

* **Text area** - The area where the numeric values are displayed.
* **Increment button** - A repeat button that can be clicked to increment the current value.
* **Decrement button** - A repeat button that can be clicked to decrement the current value.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#updown) section to get the list of assemblies or NuGet packages that need to be added as a reference to use the control in any application.

[Click_here](https://help.syncfusion.com/wpf/installation/install-nuget-packages) to find more details on how to install nuget packages in WPF application.

## Adding WPF Numeric UpDown control via designer

The [WPF Numeric UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control can be added to an application by dragging it from the toolbox onto a view in the designer. The following dependent assembly will be added automatically:

* Syncfusion.Shared.WPF

![Dragging WPF UpDown from Toolbox to Designer Page](gettingstarted-images/wpf-updown-toolbox.png)

## Adding WPF Numeric UpDown control via XAML

To add the [WPF Numeric UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio.

2. Add the following required assembly reference to the project:

    * Syncfusion.Shared.WPF

3. Import the Syncfusion<sup>®</sup> WPF schema **http://schemas.syncfusion.com/wpf** and declare the `WPF Numeric UpDown` control on the XAML page.

{% capture codesnippet1 %}
{% tabs %}

{% highlight XAML %}

<Window x:Class="NumericUpDownSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        Title="MainWindow" Height="350" Width="525">
    <Grid x:Name="grid">
        <syncfusion:UpDown x:Name="upDown" Width="100" Height="23"/>
    </Grid>
</Window>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![WPF UpDown Control](gettingstarted-images/wpf-updown-designer.jpeg)

## Adding WPF Numeric UpDown control via C#

To add the `WPF Numeric UpDown` control manually in C#, follow these steps:

1. Create a new WPF application in Visual Studio.

2. Add the following required assembly reference to the project:

    * Syncfusion.Shared.WPF

3. Include the required namespace and create an instance of `WPF Numeric UpDown`.

{% capture codesnippet2 %}
{% tabs %}

{% highlight C# %}

// Required usings:
// using Syncfusion.Windows.Shared;

UpDown updown = new UpDown();
updown.Width = 100;
updown.Height = 23;
grid.Children.Add(updown);

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

![WPF UpDown Control](gettingstarted-images/wpf-updown-code.jpeg)

## Value

The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_Value) property is used to set the value of the `WPF Numeric UpDown` control. The default value is `0` (or `null` if `UseNullOption` is enabled).

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="23" Value="10" Width="85"/>

{% endhighlight %}

{% highlight C# %}

updown.Value = 10;

{% endhighlight %}

{% endtabs %}

![Applying Value to WPF UpDown](gettingstarted-images/wpf-updown-value.png)

## Step Value

The [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_Step) property is used to specify the interval applied to the value when the spin or repeat buttons are pressed. The default value of `Step` is `1`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Value="10" Step="5" Width="90" />

{% endhighlight %}

{% highlight C# %}

updown.Value = 10;
updown.Step = 5;

{% endhighlight %}

{% endtabs %}

![Changing Step Value in WPF UpDown by clicking Spinbutton](gettingstarted-images/wpf-updown-stepvalue.gif)

## Number formatting

The number formatting of WPF Numeric UpDown control can be customized by setting [UpDown.NumberFormatInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NumberFormatInfo) property by specifying the culture-specific group separator, decimal separator, and the number of decimal digits. You can show the group separator by enable the [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_GroupSeperatorEnabled) property.

{% tabs %}

{% highlight XAML %}

<Window x:Class="NumericUpDownSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:globalization="clr-namespace:System.Globalization"
        Title="MainWindow" Height="350" Width="525">

    <syncfusion:UpDown x:Name="upDown" Height="25" Width="90" Value="100000" GroupSeperatorEnabled="True">
        <syncfusion:UpDown.NumberFormatInfo>
            <globalization:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="3" NumberDecimalSeparator="*"/>
        </syncfusion:UpDown.NumberFormatInfo>
    </syncfusion:UpDown>

</Window>

{% endhighlight %}

{% highlight C# %}

updown.Value = 100000;
updown.GroupSeperatorEnabled = true;

//Initialize numberformatinfo
NumberFormatInfo numberFormatInfo = new NumberFormatInfo();
numberFormatInfo.NumberGroupSeparator = "/";
numberFormatInfo.NumberDecimalDigits = 3;
numberFormatInfo.NumberDecimalSeparator = "*";
updown.NumberFormatInfo = numberFormatInfo;

{% endhighlight %}

{% endtabs %}

![WPF UpDown with Number Format](gettingstarted-images/wpf-updown-number-format.png)

For more number formatting in `UpDown`, you can use the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_Culture) property. The `Culture` property is used to format the values based on the selected culture.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="100000" Culture="bs-Latn" GroupSeperatorEnabled="True"/>

{% endhighlight %}

{% highlight C# %}

CultureInfo cultureInfo = new CultureInfo("bs-Latn");
updown.Culture = cultureInfo;

{% endhighlight %}

{% endtabs %}

![WPF UpDown with Latin Culture](gettingstarted-images/wpf-updown-culture.png)

## Theme

The WPF Numeric UpDown supports various built-in themes. Refer to the links below to apply themes,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Applying Theme to WPF UpDown Control](gettingstarted-images/wpf-updown-theme.png)