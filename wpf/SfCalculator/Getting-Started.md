---
layout: post
title: Getting Started | SfCalculator | WPF | Syncfusion
description: This section describes how to add calculator control into wpf application.
platform: WPF
control: SfCalculator
documentation: ug
---

# Getting Started

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfcalculator) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Creating a simple application with SfCalculator

You can create a WPF application with the SfCalculator control using the following steps:

## Create a project

Create a new WPF project in Visual Studio to display the SfCalculator with functionalities.

## Add control through designer

The SfCalculator control can be added to an application by dragging it from the toolbox to a designer view. The following assembly references are added automatically:

    * Syncfusion.SfInput.WPF 
    * Syncfusion.SfShared.WPF 

![wpf SfCalculator control added by designer](Getting-Started_images/wpf-sfcalculator-control-added-by-designer.png)

## Add control manually in XAML

To add control manually in XAML, follow the given steps:

1.	Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF
    * Syncfusion.SfShared.WPF
2.	Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** the in XAML page.
3.	Declare the SfCalculator control in the XAML page.

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="SfCalculatorSample.MainWindow"
        Title="SfCalculator Sample" Height="350" Width="525">
    <Grid>
        <!-- Adding SfCalculator control -->
        <syncfusion:SfCalculator x:Name="sfCalculator" HorizontalAlignment="Center" VerticalAlignment="Center" Width="100"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

## Add control manually in C\#

To add control manually in C#, follow the given steps:

1.	Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF 
    * Syncfusion.SfShared.WPF 
2.	Import the SfCalculator namespace **using Syncfusion.Windows.Controls.Input;**.
3.	Create an SfCalculator instance, and add it to the window.

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

![wpf SfCalculator control added by code](Getting-Started_images/wpf-sfcalculator-control-added-manually.png)

