---
layout: post
title: Toggling drawer | NavigationDrawer | WPF | Syncfusion
description: This section describes that what are the ways to toggle the drawer view panel in SfNavigationDrawer.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Toggling Drawer

Drawer can be toggled using:

*	IsOpen property

*	ToggleDrawer method

*	Swipe gesture

## Opening Drawer Programmatically

The `IsOpen` property and ToggleDrawer method can be used to open or close the drawer programmatically.

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
                                   IsOpen="True">
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
                IsOpen = true
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

Using `ToggleDrawer` method,

{% highlight c# %} 

navigationDrawer.ToggleDrawer();

{% endhighlight %}

Toggling drawer using swipe gesture is explained in the `Swipe Gesture and Sensitivity` section.
                   

