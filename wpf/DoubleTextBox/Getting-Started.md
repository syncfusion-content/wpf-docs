---
layout: post
title: Getting Started | DoubleTextBox | WPF | Syncfusion
description: The DoubleTextBox control restricts textbox input to only double values with support for data binding, Watermark, Null Value, Blendability, and Culture support.
platform: WPF
control: DoubleTextBox
documentation: ug
---

# Getting Started

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#doubletextbox) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Create a simple application with DoubleTextBox

You can create a WPF application with the DoubleTextBox control using the following steps:

## Create a project

Create a new WPF project in Visual Studio to display the DoubleTextBox with functionalities.

## Add control through designer

The DoubleTextBox control can be added to an application by dragging it from the toolbox to a designer view. The Syncfusion.Shared.WPF assembly reference will be added automatically.

![wpf double text box control added by designer](Getting-Started_images/wpf-double-text-box-control-added-by-designer.png)

## Add control manually in XAML

To add the control manually in XAML, follow the given steps:

1.	Add the **Syncfusion.Shared.WPF** assembly reference to the project.
2.	Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3.	Declare the DoubleTextBox control in the XAML page.

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="DoubleTextBoxSample.MainWindow"
        Title="DoubleTextBox Sample" Height="350" Width="525">
    <Grid>
        <!--Adding DoubleTextBox control -->
        <syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="100" VerticalAlignment="Center" HorizontalAlignment="Center"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

## Add control manually in C\#

To add the control manually in C#, follow the given steps:

1.	Add the **Syncfusion.Shared.WPF** assembly reference to the project. 
2.	Import DoubleTextBox namespace **using Syncfusion.Windows.Shared;**.
3.	Create a DoubleTextBox instance, and add it to the window.

{% tabs %}
{% highlight C# %}
using Syncfusion.Windows.Shared;
namespace DoubleTextBoxSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of DoubleTextBox control
            DoubleTextBox doubleTextBox = new DoubleTextBox();
            //Adding DoubleTextBox as window content
            this.Content = doubleTextBox;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![wpf double text box control added by code](Getting-Started_images/wpf-double-text-box-control-added-manually.png)

## Bind value

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). You can bind data to the DoubleTextBox using the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. Refer to the [Data binding](https://help.syncfusion.com/wpf/doubletextbox/dealing-with-doubletextbox#binding-value) section for more details.

{% tabs %}
{% highlight XAML %}
<StackPanel>
<syncfusion:DoubleTextBox x:Name="doubleTextBox1" Grid.Row="1" Height="25" Width="100"/>
<syncfusion:DoubleTextBox x:Name="doubleTextBox2" Grid.Row="3" Width="100" Height="25" Value="{Binding ElementName=doubleTextBox1,Path=Value,Mode=TwoWay}" />
</StackPanel>
{% endhighlight %}
{% endtabs %}

![wpf double text box control value binding](Getting-Started_images/wpf-double-text-box-value-binding.png)

## Set the minimum and maximum values

You can define the minimum and maximum values by setting the [MinVal](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) and [MaxVal](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) properties of the DoubleTextBox.

{% tabs %}
{% highlight XAML %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" Value="100" MaxValue="999.99" MinValue="-999.99"/>
{% endhighlight %}
{% highlight C# %}
//Setting minimum value
doubleTextBox.MinValue = -999.99;
//Setting maximum value
doubleTextBox.MaxValue = 999.99;
{% endhighlight %}
{% endtabs %}

## Number format

You can customize the number format by either setting the [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NumberFormat.html) property or the [NumberGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSeparator.html), [NumberGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberGroupSizes.html), [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalDigits.html), and [NumberDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NumberDecimalSeparator.html) properties of DoubleTextBox.

{% tabs %}
{% highlight XAML %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="200" Value="123456789012345">
    <syncfusion:DoubleTextBox.NumberFormat>
        <numberformat:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4" NumberDecimalSeparator="*"/>
    </syncfusion:DoubleTextBox.NumberFormat>
</syncfusion:DoubleTextBox>
{% endhighlight %}
{% highlight C# %}
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.NumberFormat = new NumberFormatInfo()
{
    NumberGroupSeparator = "/",
    NumberDecimalDigits = 4,
    NumberDecimalSeparator = "*"
};
{% endhighlight %}
{% endtabs %}

![wpf double text box control number format](Getting-Started_images/wpf-double-text-box-number-format.png)
