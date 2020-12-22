---
layout: post
title: Commands and events | NavigationDrawer | WPF | Syncfusion
description: This section describes how to performs the events, command and command parameter in NavigationDrawer.
platform: WPF
control: NavigationDrawer
documentation: ug
---

#  Commands and events in SfNavigationDrawer

This section describes how to performs the events, command and command parameter in NavigationDrawer.

## Opening event

This `Opening` event get triggered before the DrawerView panel is opened in SfNavigationDrawer. It can perform an operation before opening the DrawerView panel using the `Opening` event. 

To restrict the opening of DrawerView panel, by setting the e.Cancel value to true.

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
            // To restrict drawer opening, by setting the e.Cancel value true.
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Opened event

This `Opened` event get triggered after the DrawerView panel is opened in SfNavigationDrawer. It can perform an operation after opening the DrawerView panel using the `Opened` event. 

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
            //Necessary action perform here
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Closing event

This `Closing` event get triggered before the DrawerView panel is closed in SfNavigationDrawer. It can perform an operation before closing the DrawerView panel using the `Closing` event. 

To restrict the closing of DrawerView panel, by setting the e.Cancel value to true.

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
           // To restrict drawer closing, by setting the e.Cancel value to true.
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

## Closed event

This `Closed` event get triggered after the DrawerView panel is Closed in SfNavigationDrawer. It can perform an operation after closing the DrawerView panel using the `Closed` event. 

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
            // Necessary action perform here
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

N> The above events Opening, Opened, Closing and Closed only applicable for default display mode.

## ItemClicked event

ItemClicked event occurs when the NavigationItem clicked on each time. NavigationItemClickedEventArgs has the following members which provide information for the ItemClicked event.

* Item - Gets the clicked NavigationItem

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Compact" ItemClicked="NavigationDrawer_ItemClicked">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>


{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.ItemClicked += NavigationDrawer_ItemClicked;
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

{% tabs %}
{% highlight c# %}

        private void NavigationDrawer_ItemClicked(object sender, NavigationItemClickedEventArgs e)
        {
            var clickedItem = e.Item;
        }

{% endhighlight %}
{% endtabs %}

## ItemCollapsed event

‘ItemCollapsed’ event occurs when the sub ‘NavigationItem‘ gets collapsed. NavigationItemCollapsedEventArgs has the following members which provide information for the ‘ItemCollapsed‘ event.

* Item - Gets the collapsed NavigationItem

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Compact"
        ItemCollapsed="NavigationDrawer_ItemCollapsed">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="15"
                        Height="15"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M9.5189972,7.3780194C8.3389893,7.3780194,7.3779907,8.339018,7.3779907,9.5190097L7.3779907,22.499019C7.3779907,23.680017,8.3389893,24.641015,9.5189972,24.641015L18.442001,24.641015 21.362,27.78399 24.506989,24.641015 27.718002,24.641015C28.899002,24.641015,29.858994,23.680017,29.858994,22.499019L29.858994,9.5190097C29.858994,8.339018,28.899002,7.3780194,27.718002,7.3780194z M9.5189972,5.2380052L27.718002,5.2380052C30.082993,5.2380052,32,7.1540204,32,9.5190097L32,22.499019C32,24.864007,30.082993,26.780999,27.718002,26.780999L25.987991,26.780999 21.562988,31.264001 17.138992,26.780999 9.5189972,26.780999C7.1539917,26.780999,5.2369995,24.864007,5.2369995,22.499019L5.2369995,9.5190097C5.2369995,7.1540204,7.1539917,5.2380052,9.5189972,5.2380052z M4.2819977,0L22.65799,0C24.315994,-8.5328793E-08,25.748993,0.94302335,26.46199,2.3189999L4.5499878,2.3189999C3.2200012,2.3189996,2.1409912,3.3970023,2.1409912,4.7290026L2.1409912,21.010005C0.86199951,20.270015,0,18.891017,0,17.307002L0,4.2820121C0,1.9170222,1.9169922,-8.5328793E-08,4.2819977,0z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="15"
                        Height="15"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M22.133972,14.194015C17.582977,14.194015,13.821991,17.641011,13.323975,22.060998L30.944,22.060998C30.445984,17.641011,26.682983,14.194015,22.133972,14.194015z M22.133972,13.194014C27.582977,13.194014,32,17.61101,32,23.061L12.266998,23.061C12.266998,17.61101,16.68399,13.194014,22.133972,13.194014z M9.8659973,13.194014C5.3149719,13.194014,1.5529785,16.642016,1.0549927,21.060996L9.2409973,21.060996C9.8039856,18.306996 11.25,15.792009 13.338989,13.909012 12.242981,13.438002 11.063995,13.194014 9.8659973,13.194014z M9.8659973,12.194014C10.109119,12.194014,10.350148,12.202967,10.588797,12.220533L10.887621,12.248026 10.969,12.248026 10.969,12.256401 11.297313,12.298732C12.698914,12.50545 14.004478,13.010009 15.151978,13.738998 12.440979,15.646013 10.548981,18.628011 10.084991,22.060998L0,22.060998C0,16.61101,4.4169922,12.194014,9.8659973,12.194014z M22.133972,2.6329984C19.823975,2.6329986 17.944977,4.5130056 17.944977,6.8219985 17.944977,9.1330051 19.823975,11.012006 22.133972,11.012006 24.444,11.012006 26.322998,9.1330051 26.322998,6.8219985 26.322998,4.5130056 24.444,2.6329986 22.133972,2.6329984z M22.133972,1.6329975C25,1.6329974 27.322998,3.9570052 27.322998,6.8219985 27.322998,9.6879987 25,12.012007 22.133972,12.012007 19.266998,12.012007 16.944977,9.6879987 16.944977,6.8219985 16.944977,3.9570052 19.266998,1.6329974 22.133972,1.6329975z M9.8649902,1.0000009C7.5539856,1.0000012 5.6759949,2.8790011 5.6759949,5.189001 5.6759949,7.4990009 7.5539856,9.3780011 9.8649902,9.3780011 12.174988,9.3780011 14.052979,7.4990009 14.052979,5.189001 14.052979,2.8790011 12.174988,1.0000012 9.8649902,1.0000009z M9.8649902,0C12.730988,8.6762157E-08 15.052979,2.3230006 15.052979,5.189001 15.052979,8.0560083 12.730988,10.378002 9.8649902,10.378002 6.9989929,10.378002 4.6759949,8.0560083 4.6759949,5.189001 4.6759949,2.3230006 6.9989929,8.6762157E-08 9.8649902,0z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="15"
                        Height="15"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M9.4614787,7.2521966C8.897512,7.2521966 8.3335462,7.4671911 7.9035716,7.8961795 7.0456223,8.7541569 7.0456223,10.15112 7.9035716,11.010097 8.7355218,11.842075 10.186436,11.842075 11.018386,11.010097 11.876336,10.15112 11.876336,8.7541569 11.018386,7.8961795 10.588412,7.4671911 10.024445,7.2521966 9.4614787,7.2521966z M9.4617286,5.2529996C10.537916,5.2529991 11.613851,5.6627386 12.432303,6.4822172 14.069206,8.1201742 14.069206,10.786103 12.432303,12.424061 11.639349,13.217039 10.583413,13.655028 9.4614787,13.655028 8.3395457,13.655028 7.283608,13.217039 6.4896555,12.424061 4.8527527,10.786103 4.8527527,8.1201742 6.4896555,6.4822172 7.3091063,5.6627386 8.3855424,5.2529991 9.4617286,5.2529996z M12.752985,2.0839849L3.0529771,3.0440679 2.0839834,12.737062 18.512992,29.166996 29.173999,18.505007z M13.497004,0L32.002,18.505007 18.512992,31.994999 0,13.481081 1.2249749,1.2160647z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.ItemCollapsed += NavigationDrawer_ItemCollapsed;
            NavigationItemsCollection navigationSubItems = new NavigationItemsCollection();
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Primary",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M9.5189972,7.3780194C8.3389893,7.3780194,7.3779907,8.339018,7.3779907,9.5190097L7.3779907,22.499019C7.3779907,23.680017,8.3389893,24.641015,9.5189972,24.641015L18.442001,24.641015 21.362,27.78399 24.506989,24.641015 27.718002,24.641015C28.899002,24.641015,29.858994,23.680017,29.858994,22.499019L29.858994,9.5190097C29.858994,8.339018,28.899002,7.3780194,27.718002,7.3780194z M9.5189972,5.2380052L27.718002,5.2380052C30.082993,5.2380052,32,7.1540204,32,9.5190097L32,22.499019C32,24.864007,30.082993,26.780999,27.718002,26.780999L25.987991,26.780999 21.562988,31.264001 17.138992,26.780999 9.5189972,26.780999C7.1539917,26.780999,5.2369995,24.864007,5.2369995,22.499019L5.2369995,9.5190097C5.2369995,7.1540204,7.1539917,5.2380052,9.5189972,5.2380052z M4.2819977,0L22.65799,0C24.315994,-8.5328793E-08,25.748993,0.94302335,26.46199,2.3189999L4.5499878,2.3189999C3.2200012,2.3189996,2.1409912,3.3970023,2.1409912,4.7290026L2.1409912,21.010005C0.86199951,20.270015,0,18.891017,0,17.307002L0,4.2820121C0,1.9170222,1.9169922,-8.5328793E-08,4.2819977,0z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Social",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M22.133972,14.194015C17.582977,14.194015,13.821991,17.641011,13.323975,22.060998L30.944,22.060998C30.445984,17.641011,26.682983,14.194015,22.133972,14.194015z M22.133972,13.194014C27.582977,13.194014,32,17.61101,32,23.061L12.266998,23.061C12.266998,17.61101,16.68399,13.194014,22.133972,13.194014z M9.8659973,13.194014C5.3149719,13.194014,1.5529785,16.642016,1.0549927,21.060996L9.2409973,21.060996C9.8039856,18.306996 11.25,15.792009 13.338989,13.909012 12.242981,13.438002 11.063995,13.194014 9.8659973,13.194014z M9.8659973,12.194014C10.109119,12.194014,10.350148,12.202967,10.588797,12.220533L10.887621,12.248026 10.969,12.248026 10.969,12.256401 11.297313,12.298732C12.698914,12.50545 14.004478,13.010009 15.151978,13.738998 12.440979,15.646013 10.548981,18.628011 10.084991,22.060998L0,22.060998C0,16.61101,4.4169922,12.194014,9.8659973,12.194014z M22.133972,2.6329984C19.823975,2.6329986 17.944977,4.5130056 17.944977,6.8219985 17.944977,9.1330051 19.823975,11.012006 22.133972,11.012006 24.444,11.012006 26.322998,9.1330051 26.322998,6.8219985 26.322998,4.5130056 24.444,2.6329986 22.133972,2.6329984z M22.133972,1.6329975C25,1.6329974 27.322998,3.9570052 27.322998,6.8219985 27.322998,9.6879987 25,12.012007 22.133972,12.012007 19.266998,12.012007 16.944977,9.6879987 16.944977,6.8219985 16.944977,3.9570052 19.266998,1.6329974 22.133972,1.6329975z M9.8649902,1.0000009C7.5539856,1.0000012 5.6759949,2.8790011 5.6759949,5.189001 5.6759949,7.4990009 7.5539856,9.3780011 9.8649902,9.3780011 12.174988,9.3780011 14.052979,7.4990009 14.052979,5.189001 14.052979,2.8790011 12.174988,1.0000012 9.8649902,1.0000009z M9.8649902,0C12.730988,8.6762157E-08 15.052979,2.3230006 15.052979,5.189001 15.052979,8.0560083 12.730988,10.378002 9.8649902,10.378002 6.9989929,10.378002 4.6759949,8.0560083 4.6759949,5.189001 4.6759949,2.3230006 6.9989929,8.6762157E-08 9.8649902,0z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Promotions",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M9.4614787,7.2521966C8.897512,7.2521966 8.3335462,7.4671911 7.9035716,7.8961795 7.0456223,8.7541569 7.0456223,10.15112 7.9035716,11.010097 8.7355218,11.842075 10.186436,11.842075 11.018386,11.010097 11.876336,10.15112 11.876336,8.7541569 11.018386,7.8961795 10.588412,7.4671911 10.024445,7.2521966 9.4614787,7.2521966z M9.4617286,5.2529996C10.537916,5.2529991 11.613851,5.6627386 12.432303,6.4822172 14.069206,8.1201742 14.069206,10.786103 12.432303,12.424061 11.639349,13.217039 10.583413,13.655028 9.4614787,13.655028 8.3395457,13.655028 7.283608,13.217039 6.4896555,12.424061 4.8527527,10.786103 4.8527527,8.1201742 6.4896555,6.4822172 7.3091063,5.6627386 8.3855424,5.2529991 9.4617286,5.2529996z M12.752985,2.0839849L3.0529771,3.0440679 2.0839834,12.737062 18.512992,29.166996 29.173999,18.505007z M13.497004,0L32.002,18.505007 18.512992,31.994999 0,13.481081 1.2249749,1.2160647z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },
                Items= navigationSubItems
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

{% tabs %}
{% highlight c# %}

        private void NavigationDrawer_ItemCollapsed(object sender, NavigationItemCollapsedEventArgs e)
        {
            var collapsedItem = e.Item;
        }

{% endhighlight %}
{% endtabs %}

## ItemExpanded event

‘ItemExpanded’ event occurs when the sub ‘NavigationItem‘ gets expanded. NavigationItemExpandedEventArgs has the following members which provide information for the ‘ItemExpanded‘ event.

* Item - Gets the expanded NavigationItem

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Compact"
        ItemExpanded="NavigationDrawer_ItemExpanded">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="16"
                        Height="16"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M9.5189972,7.3780194C8.3389893,7.3780194,7.3779907,8.339018,7.3779907,9.5190097L7.3779907,22.499019C7.3779907,23.680017,8.3389893,24.641015,9.5189972,24.641015L18.442001,24.641015 21.362,27.78399 24.506989,24.641015 27.718002,24.641015C28.899002,24.641015,29.858994,23.680017,29.858994,22.499019L29.858994,9.5190097C29.858994,8.339018,28.899002,7.3780194,27.718002,7.3780194z M9.5189972,5.2380052L27.718002,5.2380052C30.082993,5.2380052,32,7.1540204,32,9.5190097L32,22.499019C32,24.864007,30.082993,26.780999,27.718002,26.780999L25.987991,26.780999 21.562988,31.264001 17.138992,26.780999 9.5189972,26.780999C7.1539917,26.780999,5.2369995,24.864007,5.2369995,22.499019L5.2369995,9.5190097C5.2369995,7.1540204,7.1539917,5.2380052,9.5189972,5.2380052z M4.2819977,0L22.65799,0C24.315994,-8.5328793E-08,25.748993,0.94302335,26.46199,2.3189999L4.5499878,2.3189999C3.2200012,2.3189996,2.1409912,3.3970023,2.1409912,4.7290026L2.1409912,21.010005C0.86199951,20.270015,0,18.891017,0,17.307002L0,4.2820121C0,1.9170222,1.9169922,-8.5328793E-08,4.2819977,0z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="16"
                        Height="16"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M22.133972,14.194015C17.582977,14.194015,13.821991,17.641011,13.323975,22.060998L30.944,22.060998C30.445984,17.641011,26.682983,14.194015,22.133972,14.194015z M22.133972,13.194014C27.582977,13.194014,32,17.61101,32,23.061L12.266998,23.061C12.266998,17.61101,16.68399,13.194014,22.133972,13.194014z M9.8659973,13.194014C5.3149719,13.194014,1.5529785,16.642016,1.0549927,21.060996L9.2409973,21.060996C9.8039856,18.306996 11.25,15.792009 13.338989,13.909012 12.242981,13.438002 11.063995,13.194014 9.8659973,13.194014z M9.8659973,12.194014C10.109119,12.194014,10.350148,12.202967,10.588797,12.220533L10.887621,12.248026 10.969,12.248026 10.969,12.256401 11.297313,12.298732C12.698914,12.50545 14.004478,13.010009 15.151978,13.738998 12.440979,15.646013 10.548981,18.628011 10.084991,22.060998L0,22.060998C0,16.61101,4.4169922,12.194014,9.8659973,12.194014z M22.133972,2.6329984C19.823975,2.6329986 17.944977,4.5130056 17.944977,6.8219985 17.944977,9.1330051 19.823975,11.012006 22.133972,11.012006 24.444,11.012006 26.322998,9.1330051 26.322998,6.8219985 26.322998,4.5130056 24.444,2.6329986 22.133972,2.6329984z M22.133972,1.6329975C25,1.6329974 27.322998,3.9570052 27.322998,6.8219985 27.322998,9.6879987 25,12.012007 22.133972,12.012007 19.266998,12.012007 16.944977,9.6879987 16.944977,6.8219985 16.944977,3.9570052 19.266998,1.6329974 22.133972,1.6329975z M9.8649902,1.0000009C7.5539856,1.0000012 5.6759949,2.8790011 5.6759949,5.189001 5.6759949,7.4990009 7.5539856,9.3780011 9.8649902,9.3780011 12.174988,9.3780011 14.052979,7.4990009 14.052979,5.189001 14.052979,2.8790011 12.174988,1.0000012 9.8649902,1.0000009z M9.8649902,0C12.730988,8.6762157E-08 15.052979,2.3230006 15.052979,5.189001 15.052979,8.0560083 12.730988,10.378002 9.8649902,10.378002 6.9989929,10.378002 4.6759949,8.0560083 4.6759949,5.189001 4.6759949,2.3230006 6.9989929,8.6762157E-08 9.8649902,0z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="16"
                        Height="16"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M9.4614787,7.2521966C8.897512,7.2521966 8.3335462,7.4671911 7.9035716,7.8961795 7.0456223,8.7541569 7.0456223,10.15112 7.9035716,11.010097 8.7355218,11.842075 10.186436,11.842075 11.018386,11.010097 11.876336,10.15112 11.876336,8.7541569 11.018386,7.8961795 10.588412,7.4671911 10.024445,7.2521966 9.4614787,7.2521966z M9.4617286,5.2529996C10.537916,5.2529991 11.613851,5.6627386 12.432303,6.4822172 14.069206,8.1201742 14.069206,10.786103 12.432303,12.424061 11.639349,13.217039 10.583413,13.655028 9.4614787,13.655028 8.3395457,13.655028 7.283608,13.217039 6.4896555,12.424061 4.8527527,10.786103 4.8527527,8.1201742 6.4896555,6.4822172 7.3091063,5.6627386 8.3855424,5.2529991 9.4617286,5.2529996z M12.752985,2.0839849L3.0529771,3.0440679 2.0839834,12.737062 18.512992,29.166996 29.173999,18.505007z M13.497004,0L32.002,18.505007 18.512992,31.994999 0,13.481081 1.2249749,1.2160647z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.ItemExpanded += NavigationDrawer_ItemExpanded;
            NavigationItemsCollection navigationSubItems = new NavigationItemsCollection();
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Primary",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M9.5189972,7.3780194C8.3389893,7.3780194,7.3779907,8.339018,7.3779907,9.5190097L7.3779907,22.499019C7.3779907,23.680017,8.3389893,24.641015,9.5189972,24.641015L18.442001,24.641015 21.362,27.78399 24.506989,24.641015 27.718002,24.641015C28.899002,24.641015,29.858994,23.680017,29.858994,22.499019L29.858994,9.5190097C29.858994,8.339018,28.899002,7.3780194,27.718002,7.3780194z M9.5189972,5.2380052L27.718002,5.2380052C30.082993,5.2380052,32,7.1540204,32,9.5190097L32,22.499019C32,24.864007,30.082993,26.780999,27.718002,26.780999L25.987991,26.780999 21.562988,31.264001 17.138992,26.780999 9.5189972,26.780999C7.1539917,26.780999,5.2369995,24.864007,5.2369995,22.499019L5.2369995,9.5190097C5.2369995,7.1540204,7.1539917,5.2380052,9.5189972,5.2380052z M4.2819977,0L22.65799,0C24.315994,-8.5328793E-08,25.748993,0.94302335,26.46199,2.3189999L4.5499878,2.3189999C3.2200012,2.3189996,2.1409912,3.3970023,2.1409912,4.7290026L2.1409912,21.010005C0.86199951,20.270015,0,18.891017,0,17.307002L0,4.2820121C0,1.9170222,1.9169922,-8.5328793E-08,4.2819977,0z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Social",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M22.133972,14.194015C17.582977,14.194015,13.821991,17.641011,13.323975,22.060998L30.944,22.060998C30.445984,17.641011,26.682983,14.194015,22.133972,14.194015z M22.133972,13.194014C27.582977,13.194014,32,17.61101,32,23.061L12.266998,23.061C12.266998,17.61101,16.68399,13.194014,22.133972,13.194014z M9.8659973,13.194014C5.3149719,13.194014,1.5529785,16.642016,1.0549927,21.060996L9.2409973,21.060996C9.8039856,18.306996 11.25,15.792009 13.338989,13.909012 12.242981,13.438002 11.063995,13.194014 9.8659973,13.194014z M9.8659973,12.194014C10.109119,12.194014,10.350148,12.202967,10.588797,12.220533L10.887621,12.248026 10.969,12.248026 10.969,12.256401 11.297313,12.298732C12.698914,12.50545 14.004478,13.010009 15.151978,13.738998 12.440979,15.646013 10.548981,18.628011 10.084991,22.060998L0,22.060998C0,16.61101,4.4169922,12.194014,9.8659973,12.194014z M22.133972,2.6329984C19.823975,2.6329986 17.944977,4.5130056 17.944977,6.8219985 17.944977,9.1330051 19.823975,11.012006 22.133972,11.012006 24.444,11.012006 26.322998,9.1330051 26.322998,6.8219985 26.322998,4.5130056 24.444,2.6329986 22.133972,2.6329984z M22.133972,1.6329975C25,1.6329974 27.322998,3.9570052 27.322998,6.8219985 27.322998,9.6879987 25,12.012007 22.133972,12.012007 19.266998,12.012007 16.944977,9.6879987 16.944977,6.8219985 16.944977,3.9570052 19.266998,1.6329974 22.133972,1.6329975z M9.8649902,1.0000009C7.5539856,1.0000012 5.6759949,2.8790011 5.6759949,5.189001 5.6759949,7.4990009 7.5539856,9.3780011 9.8649902,9.3780011 12.174988,9.3780011 14.052979,7.4990009 14.052979,5.189001 14.052979,2.8790011 12.174988,1.0000012 9.8649902,1.0000009z M9.8649902,0C12.730988,8.6762157E-08 15.052979,2.3230006 15.052979,5.189001 15.052979,8.0560083 12.730988,10.378002 9.8649902,10.378002 6.9989929,10.378002 4.6759949,8.0560083 4.6759949,5.189001 4.6759949,2.3230006 6.9989929,8.6762157E-08 9.8649902,0z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Promotions",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M9.4614787,7.2521966C8.897512,7.2521966 8.3335462,7.4671911 7.9035716,7.8961795 7.0456223,8.7541569 7.0456223,10.15112 7.9035716,11.010097 8.7355218,11.842075 10.186436,11.842075 11.018386,11.010097 11.876336,10.15112 11.876336,8.7541569 11.018386,7.8961795 10.588412,7.4671911 10.024445,7.2521966 9.4614787,7.2521966z M9.4617286,5.2529996C10.537916,5.2529991 11.613851,5.6627386 12.432303,6.4822172 14.069206,8.1201742 14.069206,10.786103 12.432303,12.424061 11.639349,13.217039 10.583413,13.655028 9.4614787,13.655028 8.3395457,13.655028 7.283608,13.217039 6.4896555,12.424061 4.8527527,10.786103 4.8527527,8.1201742 6.4896555,6.4822172 7.3091063,5.6627386 8.3855424,5.2529991 9.4617286,5.2529996z M12.752985,2.0839849L3.0529771,3.0440679 2.0839834,12.737062 18.512992,29.166996 29.173999,18.505007z M13.497004,0L32.002,18.505007 18.512992,31.994999 0,13.481081 1.2249749,1.2160647z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },

            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },
                Items= navigationSubItems
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

{% tabs %}
{% highlight c# %}

        private void NavigationDrawer_ItemExpanded(object sender, NavigationItemExpandedEventArgs e)
        {
            var expandedItem = e.Item;
        }

{% endhighlight %}
{% endtabs %}


## Commands

The command binds into NavigationItem, it will execute while items has been clicked.  NavigationDrawer have four NavigationItemType. In this only Tab and Button types supports the Command. CommandParameter is user defined data value that can be passed to the Command when it is executed.

### DelegateCommand class

public class DelegateCommand<T> : ICommand
    {
        private Predicate<T> _canExecute;
        private Action<T> _method;
        bool _canExecuteCache = true;

        /// <summary>
        /// Initializes a new instance of the <see cref="DelegateCommand"/> class.
        /// </summary>
        /// <param name="method">The method.</param>
        public DelegateCommand(Action<T> method)
            : this(method, null)
        {
        }

        /// <summary>
        /// Initializes a new instance of the <see cref="DelegateCommand"/> class.
        /// </summary>
        /// <param name="method">The method.</param>
        /// <param name="canExecute">The can execute.</param>
        public DelegateCommand(Action<T> method, Predicate<T> canExecute)
        {
            _method = method;
            _canExecute = canExecute;
        }

        /// <summary>
        /// Defines the method that determines whether the command can execute in its current state.
        /// </summary>
        /// <param name="parameter">Data used by the command.  If the command does not require data to be passed, this object can be set to null.</param>
        /// <returns>
        /// true if this command can be executed; otherwise, false.
        /// </returns>
        public bool CanExecute(object parameter)
        {
            if (_canExecute != null)
            {
                bool tempCanExecute = _canExecute((T)parameter);

                if (_canExecuteCache != tempCanExecute)
                {
                    _canExecuteCache = tempCanExecute;
                    this.RaiseCanExecuteChanged();
                }
            }

            return _canExecuteCache;
        }

        /// <summary>
        /// Raises CanExecuteChanged event to notify changes in command status.
        /// </summary>
        public void RaiseCanExecuteChanged()
        {
            if (CanExecuteChanged != null)
            {
                CanExecuteChanged(this, new EventArgs());
            }
        }

        /// <summary>
        /// Defines the method to be called when the command is invoked.
        /// </summary>
        /// <param name="parameter">Data used by the command.  If the command does not require data to be passed, this object can be set to null.</param>
        public void Execute(object parameter)
        {
            if (_method != null)
                _method.Invoke((T)parameter);
        }

        #region ICommand Members

        /// <summary>
        /// 
        /// </summary>
        public event EventHandler CanExecuteChanged;

        #endregion
    }


### ViewModel

{% tabs %}
{% highlight c# %}

    public class ViewModel:INotifyPropertyChanged
    {
        private bool _canperformaction = true;
        public event PropertyChangedEventHandler PropertyChanged;
        public void OnPropertyChanged(string name)
        {
            PropertyChangedEventHandler handler = PropertyChanged;
            if (handler != null)
            {
                handler(this, new PropertyChangedEventArgs(name));
            }
        }
        public ViewModel()
        {
            ClickCommand = new DelegateCommand<object>(ClickAction, CanPerformClickAction);
        }
        public bool CanPerformAction
        {
            get
            {
                return _canperformaction;
            }
            set
            {
                _canperformaction = value;
                this.ClickCommand.RaiseCanExecuteChanged();
                this.OnPropertyChanged("CanPerformAction");
            }
        }

        private bool CanPerformClickAction(object parameter)
        {
            return CanPerformAction;
        }

        public DelegateCommand<object> ClickCommand { get; set; }

        private void ClickAction(object parameter)
        {
            MessageBox.Show(parameter.ToString() + " item has been clicked");
        }

    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Compact">
        <syncfusion:NavigationItem
            Command="{Binding ClickCommand}"
            CommandParameter="Inbox"
            Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,43.798z M40.380997,5.6460154 L4.6410007,23.1 17.108567,28.918443z M47.383005,0 L25.364002,48.443 16.582001,30.878999 0,23.141z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Width="15"
                    Height="15"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M6.9999996,48.353 L19,48.353 19,50.353 6.9999996,50.353z M6.9999996,42.353 L32,42.353 32,44.353 6.9999996,44.353z M6.9999996,36.353 L32,36.353 32,38.353 6.9999996,38.353z M6.4999996,30.353 L31.5,30.353 31.5,32.353 6.4999996,32.353z M25.523109,22.610376 L24.94,25.014999 27.461736,24.549429z M0,15.853 L23,15.853 23,17.853 1.9999989,17.853 1.9999989,54.853 37,54.853 37,21.853 39,21.853 39,56.853 0,56.853z M40.953857,5.9638548 L26.382576,20.641725 29.510826,23.770661 44.083183,9.0931849z M44.058998,2.8360004 L42.362705,4.5447035 45.492099,7.6741037 47.184002,5.9699993 z M44.055,0 L50.004001,5.9659996 30.003,26.115 22.271,27.542999 24.065,20.137z"
                    Fill="#FF262626"
                    Stretch="Fill" />
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.FooterItems>
            <syncfusion:NavigationItem
                Command="{Binding ClickCommand}"
                CommandParameter="LogOut"
                Header="LogOut"
                ItemType="Button">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Width="16"
                        Height="16"
                        HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Data="M13.999999,3.9500002 L13.999999,6.1740026 C6.9100033,9.6210015 1.9999996,16.870002 1.9999994,25.263 1.9999996,36.973998 11.537993,46.500999 23.261992,46.500999 34.984984,46.500999 44.522002,36.973998 44.522002,25.263 44.522002,17.057998 39.834014,9.9390023 32.999999,6.4029992 L32.999999,4.1650004 C40.975005,7.8540032 46.522002,15.920997 46.522002,25.263 46.522002,38.076003 36.088011,48.500999 23.261992,48.500999 10.436004,48.500999 -2.0709092E-07,38.076003 0,25.263 -2.0709092E-07,15.735 5.7700039,7.5329964 13.999999,3.9500002z M21.999999,0 L23.999999,0 23.999999,22.999999 21.999999,22.999999z"
                        Fill="Black"
                        Stretch="Fill" />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:SfNavigationDrawer.FooterItems>

        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% endtabs %}

![Commands](Command_image/Command.png)

N> ItemClicked, ItemCollapsed, ItemExpanded events and Commands only applicable for compact and expanded display mode.