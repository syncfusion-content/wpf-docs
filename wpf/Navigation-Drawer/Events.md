---
layout: post
title: Events and Methods | NavigationDrawer | WPF | Syncfusion
description: This section describes the events used in SfNavigationDrawer and how these events can be triggered in both Xaml and code behind. 
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Events

The SfNavigationDrawer exposes the following events:
 
* Opening event
* Opened event
* Closing event
* Closed event

## Opening event

You can perform an operation before opening the DrawerView panel using the `Opening` event. This `Opening` event get triggered before the DrawerView panel is opened in SfNavigationDrawer.

To restrict the opening of DrawerView panel, you can set e.Cancel to true.

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
                                   Opening="NavigationDrawer_Opening">
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

            navigationDrawer.Opening += NavigationDrawer_Opening;

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

        private void NavigationDrawer_Opening(object sender, System.ComponentModel.CancelEventArgs e)
        {
            // To restrict drawer opening, you can set e.Cancel to true.
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Opened event

You can perform an operation after opening the DrawerView panel using the `Opened` event. This `Opened` event get triggered after the DrawerView panel is opened in SfNavigationDrawer.

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
                                   Opened="NavigationDrawer_Opened">
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

            navigationDrawer.Opened += NavigationDrawer_Opened;

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

        private void NavigationDrawer_Opened(object sender, System.EventArgs e)
        {
            // you can perform the action here
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Closing event

You can perform an operation before closing the DrawerView panel using the `Closing` event. This `Closing` event get triggered before the DrawerView panel is closed in SfNavigationDrawer.

To restrict the closing of DrawerView panel, you can set e.Cancel to true.

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
                                   Closing="NavigationDrawer_Closing">
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

            navigationDrawer.Closing += NavigationDrawer_Closing;

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

        private void NavigationDrawer_Closing(object sender, System.ComponentModel.CancelEventArgs e)
        {
           // To restrict drawer closing, you can set e.Cancel to true.
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Closed event

You can perform an operation after closing the DrawerView panel using the `Closed` event. This `Closed` event get triggered after the DrawerView panel is Closed in SfNavigationDrawer.

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
                                   Closed="NavigationDrawer_Closed">
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

            navigationDrawer.Closed += NavigationDrawer_Closed;

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

        private void NavigationDrawer_Closed(object sender, System.EventArgs e)
        {
            // you can perform the action here
        }
    }
}
	
{% endhighlight %}

{% endtabs %}
