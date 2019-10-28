---
layout: post
title: Getting Started | SfRating | wpf | Syncfusion
description: getting started
platform: wpf
control: SfRating
documentation: ug
---

# Getting Started

This section explains how to configure the SfRating control in a real-time scenario and also provides a walk-through on some of the customization features available in the SfRating control.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfrating) section to get the list of assemblies or NuGet Packages that needs to be added as a reference to use the control in any application. 

You can find more details about installing the NuGet package in a WPF application in the following link: [How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages).

You can create a WPF application with SfRating control using the following steps:

## Create a project

Create a new WPF project in Visual Studio to display the SfRating control with its functionalities, and add the following namespace to the added assemblies.

 Namespace:  Syncfusion.Windows.Controls.Input
 Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

## Add control manually in XAML

To add the control manually in XAML page, follow the given steps:

1. Add the **Syncfusion.SfShared.WPF** assembly reference to the project.
2. Import WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3. Declare the SfRating control in XAML page.

{% tabs %}
{% highlight XAML %}

<Window x:Class="SfRating_GettingStarted.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfRating_GettingStarted"
        mc:Ignorable="d"
        Title="SfRating Application" Height="450" Width="800"
        xmlns:rating="http://schemas.syncfusion.com/wpf">

    <Grid>
        <rating:SfRating ItemsCount="5"></rating:SfRating>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## Add control manually in C#

To add control manually in C#, follow the given steps:

1. Add the **Syncfusion.SfShared.WPF** assembly reference to the project.
2. Import the SfRating namespace using **Syncfusion.Windows.Controls.Input;**.
3. Create an SfRating instance, and add it to the window.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Controls.Input;

namespace SfRating_GettingStarted
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        SfRating rating;
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of SfRating control. 
            rating = new SfRating();
            rating.ItemsCount = 5;
            //Adding SfRating as window content.
            this.Content = rating;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Set number of rating items

The number of rating items to be displayed can be customized in the SfRating control. Users can create a rating application with 5 items as follows. The `ItemsCount` property is used to define the number of rating items. 

N> The default value of ItemsCount is 0.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating ItemsCount="5"></rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
}

{% endhighlight %}

{% endtabs %}

## Set value

The display value can be set in the SfRating control, which is selected among the items. The following code example shows the display value of 3 with 5 rating items. The `Value` property is used to set display value.

N> By default, value of this property is 0.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Value="3"></rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.Value = 3;
}

{% endhighlight %}

{% endtabs %}

## Precision

The SfRating control provides option to rate the items in full, half, and exact value. This can be set using the `Precision` property. By default, the precision mode is `Standard`.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemsCount="5" Precision="Standard" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.Precision = Precision.Standard;
}

{% endhighlight%}

{% endtabs %}

![SfRating Getting Started](images/gettingstarted.jpg)

The complete getting started sample is available in this [documentation](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfRating_GettingStarted480564187.zip).

