---
layout: post
title: Swipe gesture | NavigationDrawer | WPF | Syncfusion
description: This section describes how to open or close the drawer panel using the SfNavigationDrawer Swipe Gesture.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Swipe Gesture and Sensitivity

The NavigationDrawer supports swipe gesture for opening and closing the drawer. 

## Enabling swipe gesture

It can be enabled or disabled using the `EnableSwipeGesture` property.

{% tabs %}

{% highlight xaml %}

<Window x:Class="NavigationDrawerWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:NavigationDrawerWPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" 
                                   EnableSwipeGesture="True">
        <syncfusion:SfNavigationDrawer.DrawerHeaderView>
            <Grid Background="#31ade9">
                <Label Content="Header View" 
                       FontSize="20" 
                       FontWeight="Bold" 
                       HorizontalContentAlignment="Center" 
                       VerticalContentAlignment="Center"/>
            </Grid>
        </syncfusion:SfNavigationDrawer.DrawerHeaderView>
    </syncfusion:SfNavigationDrawer>
</Window>

{% endhighlight %}	
	
{% highlight c# %} 

using Syncfusion.UI.Xaml.NavigationDrawer;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Media;

namespace NavigationDrawerWPF
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer()
            {
                EnableSwipeGesture = true
            };

            Grid grid = new Grid()
            {
                Background = new SolidColorBrush((Color)ColorConverter.ConvertFromString("#31ade9"))
            };

            Label label = new Label()
            {
                Content = "Header View",
                FontSize = 20,
                FontWeight = FontWeights.Bold,
                HorizontalContentAlignment = HorizontalAlignment.Center,
                VerticalContentAlignment = VerticalAlignment.Center
            };

            grid.Children.Add(label);
            navigationDrawer.DrawerHeaderView = grid;

            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Swipe sensitivity

In smaller screens, users may find it difficult to swipe the drawer from the edge, in such cases you can increase the swipe region using the `TouchThreshold` property. It can be set as below:

{% tabs %}

{% highlight xaml %}

<Window x:Class="NavigationDrawerWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:NavigationDrawerWPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" 
                                   EnableSwipeGesture="True"
                                   TouchThreshold="70">
        <syncfusion:SfNavigationDrawer.DrawerHeaderView>
            <Grid Background="#31ade9">
                <Label Content="Header View" 
                       FontSize="20" 
                       FontWeight="Bold" 
                       HorizontalContentAlignment="Center" 
                       VerticalContentAlignment="Center"/>
            </Grid>
        </syncfusion:SfNavigationDrawer.DrawerHeaderView>
    </syncfusion:SfNavigationDrawer>
</Window>

{% endhighlight %}	
	
{% highlight c# %} 

using Syncfusion.UI.Xaml.NavigationDrawer;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Media;

namespace NavigationDrawerWPF
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer()
            {
                EnableSwipeGesture = true,
                TouchThreshold = 70
            };

            Grid grid = new Grid()
            {
                Background = new SolidColorBrush((Color)ColorConverter.ConvertFromString("#31ade9"))
            };

            Label label = new Label()
            {
                Content = "Header View",
                FontSize = 20,
                FontWeight = FontWeights.Bold,
                HorizontalContentAlignment = HorizontalAlignment.Center,
                VerticalContentAlignment = VerticalAlignment.Center
            };

            grid.Children.Add(label);
            navigationDrawer.DrawerHeaderView = grid;

            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}
                   

