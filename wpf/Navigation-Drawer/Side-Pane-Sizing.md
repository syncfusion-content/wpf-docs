---
layout: post
title: Sizing of drawer | NavigationDrawer | WPF | Syncfusion
description: This section describes how to set drawer height and drawer width to the DrawerView panel of SfNavigationDrawer.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Side Pane Sizing

The size of side pane can be adjusted using the `DrawerHeight` and `DrawerWidth` properties.

## DrawerHeight

The `DrawerHeight` property is used to change the height of side pane when the Position is Top or Bottom.

{% tabs %}
{% highlight xml %}

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
                                   DrawerHeight="200" 
                                   Position="Top">
        <syncfusion:SfNavigationDrawer.DrawerHeaderView>
            <Grid Background="#31ade9">
                <Label Content="This is a very short content used to demonstrate the DrawerHeight property "/>
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
                DrawerHeight = 200,
                Position = Position.Top
            };

            Grid grid = new Grid()
            {
                Background = new SolidColorBrush((Color)ColorConverter.ConvertFromString("#31ade9"))
            };

            Label label = new Label()
            {
                Content = "This is a very short content used to demonstrate the DrawerHeight property "
            };

            grid.Children.Add(label);
            navigationDrawer.DrawerHeaderView = grid;

            this.Content = navigationDrawer;
        }
    }
}
	
{% endhighlight %}

{% endtabs %}


## DrawerWidth

The `DrawerWidth` property is used to change the width of side pane when the Position is Left or Right.

{% tabs %}
{% highlight xml %}

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
                                   DrawerWidth="200" 
                                   Position="Left">
        <syncfusion:SfNavigationDrawer.DrawerHeaderView>
            <Grid Background="#31ade9">
                <TextBlock Text="This is a very short content used to demonstrate the DrawerHeight property "
                           TextWrapping="Wrap"/>
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
                DrawerWidth = 200,
                Position = Position.Left,
                IsOpen = true
            };

            Grid grid = new Grid()
            {
                Background = new SolidColorBrush((Color)ColorConverter.ConvertFromString("#31ade9"))
            };

            TextBlock label = new TextBlock()
            {
                Text = "This is a very short content used to demonstrate the DrawerHeight property",
                TextWrapping = TextWrapping.Wrap
            };

            grid.Children.Add(label);
            navigationDrawer.DrawerHeaderView = grid;

            this.Content = navigationDrawer;
        }
    }
}
	
{% endhighlight %}

{% endtabs %}                                
