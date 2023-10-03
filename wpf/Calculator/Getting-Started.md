---
layout: post
title: Getting Started with WPF Calculator control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Calculator (SfCalculator) control, its elements and more.
platform: WPF
control: SfCalculator
documentation: ug
---

# Getting Started with WPF Calculator (SfCalculator)
This section provides a quick overview for working with the [WPF Calculator](https://www.syncfusion.com/wpf-controls/calculator) (SfCalculator).

## Assembly deployment
Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfcalculator) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link:
[How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages#installing-nuget-packages)

## Creating Application with SfCalculator control
In this walk through, user will create a WPF application that contains [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control.
1. [Creating project](#Creating-the-project)
2. [Adding control via designer](#Adding-control-via-designer)
3. [Adding control manually in XAML](#Adding-control-manually-in-XAML)
4. [Adding control manually in C#](#Adding-control-manually-in-C#)

## Creating project
Below section provides detailed information to create new project in Visual Studio to display [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control. The required [assemblies](https://help.syncfusion.com/wpf/control-dependencies#sfcalculator) will be added automatically.

## Add control via designer

The [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control can be added to an application by dragging it from the toolbox to a designer view. The following assembly references are added automatically:

![WPF Calculator control added by designer](getting-started_images/wpf-calculator-added-by-designer.png)

## Add control manually in XAML

In order to add [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control manually in XAML, do the below steps,

1. Add the below required assembly references to the project,

   * Syncfusion.SfInput.WPF
   * Syncfusion.Shared.WPF

2. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in XAML page.

3. Declare [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) in XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="SfCalculatorSample.MainWindow"
        Title="SfCalculator Sample" Height="350" Width="525">
    <Grid>
        <syncfusion:SfCalculator x:Name="sfCalculator" HorizontalAlignment="Center" VerticalAlignment="Center" Width="100"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

## Add control manually in C#

In order to add [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control manually in C#, do the below steps,

1. Add the below required assembly references to the project,

    * Syncfusion.SfInput.WPF
    * Syncfusion.Shared.WPF

2. Import SfCalculator namespace **Syncfusion.Windows.Controls.Input**.

3. Create SfCalculator control instance and add it to the window.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}
using Syncfusion.Windows.Controls.Input;
namespace SfCalculatorSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of SfCalculator control
            SfCalculator sfCalculator = new SfCalculator();
            //Adding SfCalculator as window content
            this.Content = sfCalculator;
        }
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

![WPF Calculator control added by code](getting-started_images/wpf-calculator-added-by-code.png)

## Setting watermark
You can set watermark for [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control using [DefaultText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html#Syncfusion_Windows_Controls_Input_SfCalculator_DisplayText) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfCalculator HorizontalAlignment="Stretch" DisplayText="Empty value here"  />

{% endhighlight %}
{% highlight C# %}

SfCalculator sfCalculator = new SfCalculator()
{
    HorizontalAlignment = HorizontalAlignment.Stretch,
    DisplayText = "Empty value here"
};

{% endhighlight %}
{% endtabs %}

![Setting WaterMark for Calculator in WPF application](getting-started_images/wpf-calculator-setting-watermark.png)

## Setting value 

You can set the value to be displayed on the [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control using [DefaultValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html#Syncfusion_Windows_Controls_Input_SfCalculator_DefaultValue) property.

N> The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html#Syncfusion_Windows_Controls_Input_SfCalculator_Value) property of [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) is **Read-only** which will allow you to get the value calculated from last expression and will be in decimal format.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfCalculator HorizontalAlignment="Stretch"  DefaultValue="30"  />

{% endhighlight %}
{% highlight C# %}

sfCalculator.DefaultValue = 30;

{% endhighlight %}
{% endtabs %}

![Setting values in WPF Calculator](getting-started_images/wpf-calculator-setting-values.png)

## Theme

The WPF Calculator (SfCalculator) supports various built-in themes. Refer to the below links to apply themes for the SfCalculator,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Calculator](getting-started_images/wpf-calculator-theme.png)