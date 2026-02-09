---
layout: post
title: Getting Started with WPF Step ProgressBar control | Syncfusion
description: Learn here about getting started with Syncfusion<sup>&reg;</sup>; WPF Step ProgressBar (SfStepProgressBar) control, its elements and more.
platform: wpf
control: SfStepProgressBar
documentation: ug
---

# Getting Started with WPF Step ProgressBar (SfStepProgressBar)

You can create a WPF application with the SfStepProgressBar control using the following steps:

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: [How to install NuGet packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages)

## Adding control through designer

The SfStepProgressBar control can be added to a WPF application by dragging it from the toolbox to a designer view. The following assembly reference will be added automatically:

* Syncfusion.SfProgressBar.WPF 

![wpf SfStepProgressBar control added through designer](Getting-Started_images/wpf-StepProgressBar-control-added-through-designer.png)

## Adding control manually in XAML

To add control manually in the XAML, follow the given steps:

1.	Add the following required assembly reference to the project:
    * Syncfusion.SfProgressBar.WPF     
2.	Import the Syncfusion&reg; WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3.	Declare the SfStepProgressBar control in the XAML page.

## Select item using Selected Index
You can change the index of the last active (selected) item where items before this index will move to the active status by using the [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfStepProgressBar_SelectedIndex) property. 

{% tabs %}
{% highlight XAML %}
<Grid x:Name="grid">
    <syncfusion:SfStepProgressBar SelectedIndex="3">
        <syncfusion:StepViewItem Content="Ordered" />
        <syncfusion:StepViewItem Content="Shipped" />
        <syncfusion:StepViewItem Content="Packed" />
        <syncfusion:StepViewItem Content="Delivered" />
    </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% highlight C# %}
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
{% endhighlight %}
{% endtabs %}

![Selected index image](Getting-Started_images/wpf-StepProgressBar-control-added-manually.png)

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

{% capture codesnippet1 %}
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
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}


Download demo from [GitHub](https://github.com/SyncfusionExamples/WPF-StepProgressBar-Demos/tree/master/Samples/GettingStarted).

## Theme

SfStepProgressBar supports various built-in themes. Refer to the below links to apply themes for the SfStepProgressBar,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfStepProgressBar](Getting-Started_images/wpf-StepProgressBar-control-Theme.png)