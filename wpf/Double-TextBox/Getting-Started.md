---
layout: post
title: Getting started with WPF DoubleTextBox control | Syncfusion
description: Learn here about getting started with Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: WPF
control: DoubleTextBox
documentation: ug
---

# Getting started with WPF DoubleTextBox

This section explains how to create a WPF `DoubleTextBox` control and its features.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#doubletextbox) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Adding WPF DoubleTextBox via designer

You can add the [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) control to an application by dragging it from the toolbox to a view of the designer. The following dependent assembly will be added automatically:

* Syncfusion.Shared.WPF

![DoubleTextBox Control added by designer](Getting-Started_images/wpf-double-text-box-control-added-by-designer.png)

## Adding WPF DoubleTextBox via XAML

To add the DoubleTextBox control manually in XAML, follow these steps:
1. Create a new WPF project in Visual Studio.

2. Add the **Syncfusion.Shared.WPF** assembly references to the project.
 
3. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** and declare the `DoubleTextBox` control in XAML page.

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="DoubleTextBoxSample.MainWindow"
        Title="DoubleTextBox Sample" Height="350" Width="525">
    <Grid>
        <!--Adding DoubleTextBox control -->
        <syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" VerticalAlignment="Center" HorizontalAlignment="Center"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

## Adding WPF DoubleTextBox via C\#

To add the DoubleTextBox control manually in C#, follow these steps:

1. Create a new WPF application via Visual Studio.

2. Add the **Syncfusion.Shared.WPF** assembly references to the project.

3. Include the required namespace.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

{% endhighlight %}
{% endtabs %}

4. Create an instance of DoubleTextBox and add it to the window.

{% tabs %}
{% highlight C# %}

//Creating an instance of DoubleTextBox control

DoubleTextBox doubleTextBox = new DoubleTextBox();

// Setting height and width to DoubleTextBox

doubleTextBox.Height = 25;
doubleTextBox.Width = 100;

//Adding DoubleTextBox as window content

this.Content = doubleTextBox;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox control added to Window by code](Getting-Started_images/wpf-double-text-box-control-added-manually.png)

## Setting Value

The value of the `DoubleTextBox` can be set by using the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="23" Value="100"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 23;
doubleTextBox.Value = 100;

{% endhighlight %}
{% endtabs %}

![Set the value for DoubleTextBox](Getting-Started_images/Getting-Started-img3.jpeg)

N> Do not use the [Text](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textbox.text?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_TextBox_Text) property to set the value for the DoubleTextBox. Use only the `Value` property.

### Binding Value

Data binding is the method of forming a connection between the application  UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). You can bind data to the `DoubleTextBox` using the `Value` Property.

The following code snippets illustrate the value binding from one `DoubleTextBox` to another.

{% tabs %}
{% highlight XAML %}

<StackPanel>
<syncfusion:DoubleTextBox x:Name="doubleTextBox1" Height="25" Width="100" Value="{Binding myValue,UpdateSourceTrigger=PropertyChanged}"/>
<syncfusion:DoubleTextBox x:Name="doubleTextBox2" Width="100" Height="25" Value="{Binding myValue,UpdateSourceTrigger=PropertyChanged}" />
</StackPanel>

{% endhighlight %}
{% endtabs %}

ViewModel.cs

{% tabs %}
{% highlight C# %}

class ViewModel : NotificationObject
{
    private double myValue;
    public double MyValue
    {
        get
        {
            return myValue;
        }
        set
        {
            myValue = value;
            RaisePropertyChanged("MyValue");
        }
    }
}

{% endhighlight %}
{% endtabs %}

![DoubleTextBox value binding](Getting-Started_images/wpf-double-text-box-value-binding.png)

## Value Changed Notification

The `DoubleTextbox` control can notifies the value changes through the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html) event. You can get old value and new Value from `OldValue` and `NewValue` properties in `ValueChanged` event.

{%tabs%}
{% highlight xaml %} 

<syncfusion:DoubleTextBox ValueChanged="DoubleTextBox_ValueChanged"/>

{% endhighlight %}
{% highlight C# %} 

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValueChanged += new PropertyChangedCallback(DoubleTextBox_ValueChanged);

{% endhighlight %}
{%endtabs%}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void DoubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Min Max Value Restriction

The `Value` of `DoubleTextBox` can be restricted within maximum and minimum limit. You can define the minimum and maximum values by setting the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MinValue) and [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_MaxValue) properties. It allows the user to enter the value between `MinValue` and `MaxValue`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" Value="100" MaxValue="999.99" MinValue="-999.99"/>
{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
//Setting minimum value
doubleTextBox.MinValue = -999.99;
//Setting maximum value
doubleTextBox.MaxValue = 999.99;
doubleTextBox.Value = 100;

{% endhighlight %}
{% endtabs %}

![Restrict the value of DoubleTextBox by the minimum and maximum values](Getting-Started_images/Getting-Started-img3.jpeg)

## Step Interval to increase or decrease the value

The `DoubleTextBox` control allows to increase or decrease the value by pressing up and down arrow keys in keyboard or mouse wheel over the control. The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_ScrollInterval) property is used to specify the increment or decrement intervals. The default value of `ScrollInterval` is 1.

{% tabs %}
{% highlight xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25" Value="8" 
                          IsScrollingOnCircle="True" ScrollInterval="4"/>

{% endhighlight %}

{% highlight C# %}
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 8;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 4;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox value increment or decrement interval](Getting-Started_images/Step-Interval.png)

## Formatting the value

You can customize the number format by either setting the [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NumberFormat) property or the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NumberGroupSeparator), [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NumberGroupSizes), [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NumberDecimalDigits), and [NumberDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NumberDecimalSeparator) properties of `DoubleTextBox`.

{% tabs %}
{% highlight XAML %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="200" Value="123456789012345">
    <syncfusion:DoubleTextBox.NumberFormat >
        <numberformat:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4" NumberDecimalSeparator="*"/>
    </syncfusion:DoubleTextBox.NumberFormat>
</syncfusion:DoubleTextBox>
{% endhighlight %}
{% highlight C# %}
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 200;
doubleTextBox.Height = 25;
doubleTextBox.Value = 123456789012345;
doubleTextBox.NumberFormat = new NumberFormatInfo()
{
    NumberGroupSeparator = "/",
    NumberDecimalDigits = 4,
    NumberDecimalSeparator = "*"
};
{% endhighlight %}
{% endtabs %}

![Setting DoubleTextBox Number Format](Getting-Started_images/wpf-double-text-box-number-format.png)

## Setting the Culture

The `DoubleTextBox` provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_Culture) property. The `Culture` is used to format the decimal separator and group separator of the `DoubleTextBox` value based on the respective culture.

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

![Setting DoubleTextBox Culture](Getting-Started_images/Getting-Started_img4.png)

N> When you use both `NumberFormat` and  `Culture`, the `NumberFormat` will have a higher priority.

## Theme

DoubleTextBox supports various built-in themes. Refer to the below links to apply themes for the DoubleTextBox,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Set theme to WPF DoubleTextBox](Getting-Started_images/wpf-double-text-box-theme-support.png)