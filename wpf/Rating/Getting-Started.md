---
layout: post
title: Getting Started with WPF SfRating | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF SfRating control. Explore setup, features, examples, and customization options.
platform: wpf
control: SfRating
documentation: ug
---

# Getting Started with WPF SfRating

This section explains how to get started with the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control and demonstrates some of its basic customization features.

## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfrating) section for the list of assemblies and NuGet packages required to use the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control in a WPF application.

For more information about installing NuGet packages in a WPF application, refer to the following article:
[How to install nuget packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)

## Creating Application with SfRating control
In this walkthrough, you will create a WPF application that hosts the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control.

1. [Creating the project](#creating-the-project)
2. [Adding the control via the designer](#adding-the-control-via-the-designer)
3. [Adding the control manually in XAML](#adding-the-control-manually-in-xaml)
4. [Adding the control manually in C#](#adding-the-control-manually-in-c)

## Creating the project

The following steps describe how to create a WPF project in Visual Studio and add the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control to it.

1. Open Visual Studio and click **File → New → Project**.
2. Select **WPF App (.NET Framework)** or **WPF Application (.NET)** depending on your target framework.
3. Name the project **SfRatingSample** and click **Create**.

## Adding the control via the designer
You can add the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control to your application by dragging it from the **Toolbox** and dropping it onto the designer surface. The required assembly references are added automatically.

1. If the Toolbox is not visible, open it from **View → Toolbox**.
2. In the Toolbox search box, type **SfRating** and locate the control under the **Syncfusion WPF** tab.
3. Drag **SfRating** onto the designer surface of `MainWindow.xaml`.

![Adding WPF SfRating Control via Designer](getting-started-images/wpf-rating-add-control-designer.png)

## Adding the control manually in XAML

To add the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control manually in XAML, follow these steps:

1. Add the required assembly references to the project:

   * Syncfusion.SfInput.WPF
   * Syncfusion.SfShared.WPF
   
2. Import the Syncfusion WPF namespace `http://schemas.syncfusion.com/wpf` in the XAML page.

3. Add the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control to the XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight XAML %}

<Window x:Class="SfRatingSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfRatingSample"
        mc:Ignorable="d"
        Title="SfRating Application" Height="450" Width="800"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <Grid>
        <syncfusion:SfRating ItemsCount="5" Width="150"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

## Adding the control manually in C#

To add the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control manually in C#, follow these steps:

1. Add the required assembly references to the project:

    * Syncfusion.SfShared.WPF
    * Syncfusion.SfInput.WPF

2. Import the SfRating namespace `Syncfusion.Windows.Controls.Input`.

3. Create an instance of the SfRating control and add it to the window.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}

using System.Windows;
using Syncfusion.Windows.Controls.Input;

namespace SfRatingSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of the SfRating control.
            SfRating rating = new SfRating()
            {
                ItemsCount = 5,
                Width = 150
            };
            //Adding SfRating as the window content.
            this.Content = rating;
        }
    }
}

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

## Customizing the number of rating items

Use the [ItemsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html#Syncfusion_Windows_Controls_Input_SfRating_ItemsCount) property to specify the number of rating items displayed in the [SfRating](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html) control.

N> The default value of `ItemsCount` is `0`, so no items render until you set this property to a positive integer.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRating ItemsCount="5" Width="150"/>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating = new SfRating()
{
    ItemsCount = 5,
    Width = 150
};

{% endhighlight %}

{% endtabs %}

## Setting the value

Use the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html#Syncfusion_Windows_Controls_Input_SfRating_Value) property to specify the currently selected rating. The valid range is from 0 to the value specified by _ItemsCount_.

N> By default, the value of this property is `0`.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRating ItemsCount="5" Value="3" Width="150"/>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating = new SfRating()
{
    ItemsCount = 5,
    Width = 150,
    Value = 3
};

{% endhighlight %}

{% endtabs %}

## Setting the selection precision

Use the [Precision](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRating.html#Syncfusion_Windows_Controls_Input_SfRating_Precision) property to control whether users can select full, half, or exact rating values.

N> By default, the value of the `Precision` property is `Standard`.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRating ItemsCount="5" Value="3" Precision="Exact" Width="150"/>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating = new SfRating()
{
    ItemsCount = 5,
    Width = 150,
	Value = 3,
    Precision = Syncfusion.Windows.Primitives.Precision.Exact
};

{% endhighlight %}

{% endtabs %}

![WPF SfRating Control](images/gettingstarted.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/SfRating-getting-started)

## Theme

SfRating supports a variety of built-in themes. Refer to the following articles to learn how to apply themes:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting Theme in WPF Rating](getting-started-images/wpf-rating-setting-theme.png)
