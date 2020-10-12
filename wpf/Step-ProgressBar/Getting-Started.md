---
layout: post
title: Getting started with WPF Step ProgressBar control | Syncfusion
description: Learn about getting started with the Syncfusion WPF Step ProgressBar (SfStepProgressBar) control and more details.
platform: WPF
control: SfStepProgressBar
documentation: ug
---

# Creating a simple application with Step ProgressBar

You can create a WPF application with the SfStepProgressBar control using the following steps:

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: [How to install NuGet packages](https://help.syncfusion.com/wpf/nuget-packages)

## Adding control through designer

The SfStepProgressBar control can be added to a WPF application by dragging it from the toolbox to a designer view. The following assembly reference will be added automatically:

* Syncfusion.SfProgressBar.WPF 

![wpf SfStepProgressBar control added through designer](Getting-Started_images/wpf-StepProgressBar-control-added-through-designer.png)

## Adding control manually in XAML

To add control manually in the XAML, follow the given steps:

1.	Add the following required assembly reference to the project:
    * Syncfusion.SfProgressBar.WPF     
2.	Import the Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3.	Declare the SfStepProgressBar control in the XAML page.

{% tabs %}
{% highlight XAML %}
<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp4"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf" x:Class="StepProgressBar.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
        <Grid x:Name="grid">
            <Syncfusion:SfStepProgressBar SelectedIndex="3">
                <Syncfusion:StepViewItem Content="Ordered" />
                <Syncfusion:StepViewItem Content="Shipped" />
                <Syncfusion:StepViewItem Content="Packed" />
                <Syncfusion:StepViewItem Content="Delivered" />
            </Syncfusion:SfStepProgressBar>       
        </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

## Adding control through code behind

To add control manually using the code behind, follow the given steps:

1.	Add the following required assembly reference to the project:
   * Syncfusion.SfProgressBar.WPF
2.	Import the ProgressBar namespace
    **using Syncfusion.UI.Xaml.ProgressBar;**
3.	Create a Step Progressbar instance, and add it to the window.

![WPF SfStepProgressBar control added through code](Getting-Started_images/wpf-StepProgressBar-control-added-manually.png)

{% tabs %}
{% highlight C# %}
using Syncfusion.UI.Xaml.ProgressBar;
namespace SfProgressBar
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {                  
        public MainWindow()
        {
            InitializeComponent();
            SfStepProgressBar stepProgressBar = new SfStepProgressBar();
            StepViewItem orderedStepViewItem = new StepViewItem();
            StepViewItem shippedStepViewItem = new StepViewItem();
            StepViewItem packedStepViewItem = new StepViewItem();
            StepViewItem deliveredStepViewItem = new StepViewItem();

            orderedStepViewItem.Content = "Ordered";
            shippedStepViewItem.Content = "Shipped";
            packedStepViewItem.Content = "Packed";
            deliveredStepViewItem.Content = "Delivered";

            stepProgressBar.Items.Add(orderedStepViewItem);
            stepProgressBar.Items.Add(shippedStepViewItem);
            stepProgressBar.Items.Add(packedStepViewItem);
            stepProgressBar.Items.Add(deliveredStepViewItem);

            stepProgressBar.SelectedIndex = 3;

            grid.Children.Add(stepProgressBar);
        }      
    }
}
{% endhighlight %}
{% endtabs %}

The sample project for displaying PDF files using the PDF Viewer is available in the [GitHub](https://github.com/SyncfusionExamples/WPF-StepProgressBar-Demos/tree/master/GettingStarted-Demo).