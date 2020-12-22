---
layout: post
title: Populating with Data | NavigationDrawer | WPF | Syncfusion
description: This section describes how to set the view of the drawer content in default mode and populate the items in compact and expanded mode in SfNavigationDrawer.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Populating with Data

This section explains how to show the drawer view. 

## Setting Panel content in default mode

The DrawerView is a panel that is the hidden content, brought to the view by manipulations like panning or swiping through the edges. The DrawerView has three sections namely:

   * DrawerHeaderView: Gets or sets the DrawerHeaderView of the DrawerView panel in the SfNavigationDrawer control.
   
   * DrawerContentView: The SfNavigationDrawer control contains the DrawerContentView, a part of the DrawerView panel. The DrawerContentView displays the navigation items that needs to jump to.
   
   * DrawerFooterView: Gets or sets the footer for the DrawerView panel in the SfNavigationDrawer control.  

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
    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DrawerWidth="300">
        <syncfusion:SfNavigationDrawer.ContentView>
            <Grid x:Name="mainContentView" 
                  Background="White">
                <Grid.RowDefinitions>
                    <RowDefinition Height="auto"/>
                    <RowDefinition/>
                </Grid.RowDefinitions>
                <StackPanel Background="#1aa1d6" 
                            Orientation="Horizontal">
                    <Button x:Name="hamburgerButton" 
                            BorderBrush="Transparent" 
                            Height="50" Width="50" 
                            HorizontalAlignment="Left"  
                            FontSize="16" 
                            Background="#1aa1d6" Foreground="White" 
                            Click="HamburgerButton_Click">
                        <Image Source="hamburger_icon.png" 
                               Height="20" 
                               Width="20" 
                               HorizontalAlignment="Center" 
                               VerticalAlignment="Center"/>
                    </Button>
                    <Label x:Name="headerLabel" 
                           Height="50" 
                           HorizontalContentAlignment="Center" 
                           VerticalContentAlignment="Center" 
                           Content="Home" 
                           FontSize="16" 
                           Foreground="White" 
                           Background="#1aa1d6"/>
                </StackPanel>
                <Label Grid.Row="1" 
                       x:Name="contentLabel" 
                       VerticalContentAlignment="Center" 
                       HorizontalContentAlignment="Center" 
                       Content="Content View" 
                       FontSize="14" Foreground="Black"/>
            </Grid>
        </syncfusion:SfNavigationDrawer.ContentView>
        <syncfusion:SfNavigationDrawer.DrawerHeaderView>
            <Grid Background="#31ade9">
                <Label Content="Header View" 
                       FontSize="20" 
                       FontWeight="Bold" 
                       HorizontalContentAlignment="Center" 
                       VerticalContentAlignment="Center"/>
            </Grid>
        </syncfusion:SfNavigationDrawer.DrawerHeaderView>
        <syncfusion:SfNavigationDrawer.DrawerContentView>
            <Grid>
                <ListBox x:Name="list" 
                         ItemsSource="{Binding Contents}">
                    <ListBox.ItemTemplate>
                        <DataTemplate>
                            <TextBlock  Text="{Binding Name}" 
                                        Padding="15" 
                                        TextAlignment="Center" 
                                        FontSize="18" 
                                        Foreground="Black"/>
                        </DataTemplate>
                    </ListBox.ItemTemplate>
                </ListBox>
            </Grid>
        </syncfusion:SfNavigationDrawer.DrawerContentView>
        <syncfusion:SfNavigationDrawer.DrawerFooterView>
            <Grid Background="#31ade9">
                <Label Content="Footer View" 
                       FontSize="20" 
                       FontWeight="Bold" 
                       HorizontalContentAlignment="Center" 
                       VerticalContentAlignment="Center"/>
            </Grid>
        </syncfusion:SfNavigationDrawer.DrawerFooterView>
    </syncfusion:SfNavigationDrawer>
</Window>
    
{% endhighlight %}

{% highlight c# %}

using System.Collections.Generic;
using System.Windows;

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
        }

        private void HamburgerButton_Click(object sender, RoutedEventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }
    }

    public class ViewModel
    {
        public ViewModel()
        {
            Contents = new List<Model>();

            Contents.Add(new Model() { Name = "Home" });
            Contents.Add(new Model() { Name = "Profile" });
            Contents.Add(new Model() { Name = "Inbox" });
            Contents.Add(new Model() { Name = "Outbox" });
            Contents.Add(new Model() { Name = "Sent" });
            Contents.Add(new Model() { Name = "Trash" });
            Contents.Add(new Model() { Name = "Sign Out" });
        }

        public List<Model> Contents { get; set; }
    }

    public class Model
    {
        public string Name { get; set; }
    }
}

{% endhighlight %}

{% endtabs %}

![Drawer View Image](Getting-Started_images/Drawer_View_Image.png)   


## Data Binding

The drawer content view can be populated by ItemsSource property. It can support, bound collection of objects through the ItemsSource. 

### Model

{% tabs %}
{% highlight c# %}

    public class Model
    {
        private string item;
        public string Item
        {
            get { return item; }
            set { item = value; }
        }

        private object icon;
        public object Icon
        {
            get { return icon; }
            set { icon = value; }
        }
    }

{% endhighlight %}
{% endtabs %}

### ViewModel

{% tabs %}
{% highlight c# %}

    public class ViewModel
    {
        public ObservableCollection<Model> Items { get; set; }
        public ViewModel()
        {
            Items = new ObservableCollection<Model>();
            Items.Add(new Model()
            {
                Item = "Explore",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 16,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.0033803,5.705333 L7.0853577,8.4971852 9.9112849,10.241092 8.6573143,7.3392491 z M5.0022244,4.0000064 C5.0918167,4.0004316 5.1818919,4.0249844 5.2623992,4.0744188 L9.3152895,6.5702889 C9.4033003,6.6242869 9.4722991,6.7032812 9.5132833,6.7982774 L11.459255,11.302037 C11.545252,11.502027 11.492244,11.735016 11.327239,11.879006 11.233247,11.959003 11.117252,12.000002 11.00025,12.000002 10.909249,12.000002 10.818278,11.976001 10.737256,11.926004 L6.4163659,9.2601452 C6.3233503,9.2021494 6.252368,9.1161518 6.2133675,9.0151591 L4.5334113,4.6813889 C4.4563866,4.4803993 4.5154063,4.2534102 4.6804113,4.1164165 4.7726429,4.0387974 4.8870345,3.9994598 5.0022244,4.0000064 z M8,1 C4.14,1 1,4.1409999 1,8 1,11.86 4.14,15 8,15 11.859,15 15,11.86 15,8 15,4.1409999 11.859,1 8,1 z M8,0 C12.411,0 16,3.5889999 16,8 16,12.411 12.411,16 8,16 3.589,16 0,12.411 0,8 0,3.5889999 3.589,0 8,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "My music",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 14.7,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M2.5,10.701 C1.6729736,10.701 1,11.373997 1.0000001,12.201 1,13.027996 1.6729736,13.701 2.5,13.701 3.3269958,13.701 4,13.027996 4,12.201 L3.9999866,12.200474 3.9980443,12.123936 C3.9577868,11.332592 3.3011522,10.701 2.5,10.701 z M13.499987,8.7009979 C12.672987,8.7009979 11.999987,9.373998 11.999987,10.200998 11.999987,11.027998 12.672987,11.700998 13.499987,11.700998 14.326986,11.700998 14.999987,11.027998 14.999987,10.200998 14.999987,9.373998 14.326986,8.7009979 13.499987,8.7009979 z M14.515357,1.0003309 C14.481983,0.99951458 14.446487,1.0020571 14.408987,1.0089951 L5.4099865,2.6579952 C5.1719866,2.700995 4.9999866,2.9079952 4.9999866,3.1489954 L4.9999866,4.7396889 14.999987,2.9069619 14.999987,1.5009947 C14.999987,1.2969952 14.886987,1.1729946 14.819986,1.1159945 14.764736,1.0704947 14.659975,1.0038691 14.515357,1.0003309 z M14.477699,0.00021648407 C14.835276,-0.0058488846 15.181299,0.11561966 15.459987,0.3479948 15.802987,0.63499451 15.999987,1.0549946 15.999987,1.5009947 L15.999987,10.200997 C15.999987,11.579998 14.877987,12.700998 13.499987,12.700998 12.120987,12.700998 10.999987,11.579998 10.999987,10.200998 10.999987,8.822998 12.120987,7.7009981 13.499987,7.7009981 14.059799,7.7009981 14.577362,7.8861719 14.994612,8.1984568 L14.999987,8.2026836 14.999987,3.9231343 4.9999866,5.755861 4.9999866,12.200465 5,12.201 C5,13.579998 3.8779907,14.701 2.5,14.701 1.1209717,14.701 0,13.579998 0,12.201 0,10.822994 1.1209717,9.7010002 2.5,9.7010002 3.0598087,9.7010002 3.5773706,9.8861731 3.9946208,10.198457 L3.9999866,10.202677 3.9999866,3.1489954 C3.9999866,2.4249949 4.5169868,1.8049951 5.2289867,1.6749945 L14.228987,0.02499485 C14.312049,0.0098075867 14.395182,0.0016155243 14.477699,0.00021648407 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Recommended",
                Icon = new Path()
                {
                    Width = 14,
                    Height = 14,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M11.5,10 C11.224,10 11,10.225 11,10.5 L11,13 11.5,13 C12.327,13 13,12.327 13,11.5 L13,10 z M1.0000133,9.9999933 L1.0000133,11.499993 C1.0000133,12.327004 1.672987,12.999993 2.5000133,12.999993 L3.0000133,12.999993 3.0000133,10.499993 C3.0000133,10.224999 2.7750072,9.9999933 2.5000133,9.9999933 z M7,0 C10.859,0 14,3.1409998 14,7 L14,9.4999999 14,10 14,11.5 C14,12.879 12.878,14 11.5,14 L10.5,14 C10.224,14 10,13.776 10,13.5 L10,10.5 C10,9.6729999 10.673,8.9999999 11.5,8.9999999 L13,8.9999999 13,7 C13,3.691 10.309,1 7,1 3.691,1 0.99999999,3.691 0.99999993,7 L0.99999993,8.9999934 2.5000133,8.9999934 C3.3270092,8.9999933 4.0000133,9.6729975 4.0000133,10.499993 L4.0000133,13.499993 C4.0000133,13.775994 3.7760143,13.999993 3.5000133,13.999993 L2.5000133,13.999993 C1.120985,13.999993 1.3340759E-05,12.879006 1.335144E-05,11.499993 L1.335144E-05,10 0,7 C1.0681106E-08,3.1409998 3.1400001,0 7,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Recent Playlist",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9990103,3.0000041 L7.9990076,3.0000041 7.9990076,7.270998 11.32401,10.121002 10.674018,10.880004 6.9990103,7.7310042 z M7.5,1 C3.9160001,1 1,3.916 1,7.5 1,11.084 3.9160001,14 7.5,14 11.084,14 14,11.084 14,7.5 14,3.916 11.084,1 7.5,1 z M7.5,0 C11.636,0 15,3.3640001 15,7.5 15,11.636 11.636,15 7.5,15 3.3640001,15 0,11.636 0,7.5 0,3.3640001 3.3640001,0 7.5,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Radio",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 15.4,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M2.5,11.472009 L6.5,11.472009 C6.776,11.472009 7,11.696009 7,11.972009 7,12.248009 6.776,12.472009 6.5,12.472009 L2.5,12.472009 C2.224,12.472009 2,12.248009 2,11.972009 2,11.696009 2.224,11.472009 2.5,11.472009 z M2.5,8.4720092 L6.5,8.4720092 C6.776,8.4720092 7,8.6960092 7,8.9720092 7,9.2480091 6.776,9.4720092 6.5,9.4720092 L2.5,9.4720092 C2.224,9.4720092 2,9.2480091 2,8.9720092 2,8.6960092 2.224,8.4720092 2.5,8.4720092 z M11.000013,8.4720025 C9.8960094,8.4720025 9.0000134,9.3690057 9.0000134,10.472003 9.0000134,11.576006 9.8960094,12.472003 11.000013,12.472003 12.10301,12.472003 13.000013,11.576006 13.000013,10.472003 13.000013,9.3690057 12.10301,8.4720025 11.000013,8.4720025 z M11.000013,7.4720025 C12.654005,7.4720025 14.000013,8.8180108 14.000013,10.472003 14.000013,12.126009 12.654005,13.472003 11.000013,13.472003 9.3459911,13.472003 8.0000134,12.126009 8.0000134,10.472003 8.0000134,8.8180108 9.3459911,7.4720025 11.000013,7.4720025 z M1.5,6.4720092 C1.2290001,6.4720091 1,6.6560091 1,6.872009 L1,14.073009 C1,14.289009 1.2290001,14.472009 1.5,14.472009 L14.5,14.472009 C14.771,14.472009 15,14.289009 15,14.073009 L15,6.872009 C15,6.6560091 14.771,6.4720091 14.5,6.4720092 z M12.877348,0.00054502487 C13.071978,-0.0085949898 13.261545,0.097710133 13.351547,0.28444672 13.47155,0.53342915 13.365548,0.83140802 13.116541,0.9513998 L3.6977077,5.4720092 14.5,5.4720092 C15.327,5.4720092 16,6.1000091 16,6.872009 L16,14.073009 C16,14.844009 15.327,15.472009 14.5,15.472009 L1.5,15.472009 C0.67299986,15.472009 0,14.844009 0,14.073009 L0,6.872009 C0,6.148259 0.59150362,5.5510716 1.346869,5.4792504 L1.3769317,5.4771099 12.684531,0.049463272 C12.747032,0.019465446 12.812471,0.0035915375 12.877348,0.00054502487 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    <syncfusion:SfNavigationDrawer
            x:Name="navigationDrawer"
            DisplayMemberPath="Item"
            DisplayMode="Compact"
            IconMemberPath="Icon"
            ItemsSource="{Binding Items}">
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

            ViewModel viewModel = new ViewModel();
            this.DataContext = viewModel;
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.DisplayMemberPath = "Item";
            navigationDrawer.IconMemberPath = "Icon";
            navigationDrawer.ItemsSource = viewModel.Items;
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

## Hierarchical Data Binding

The control populates the items using the ItemsSource, also it allows the sub items. It can be achieved by using the DisplayMemberPath, IconMemberPath and ItemsContainerStyle. 

                                   
### Model

{% tabs %}
{% highlight c# %}

    public class Model
    {
        public ObservableCollection<Model> SubItems { get; set; }

        private string item;
        public string Item
        {
            get { return item; }
            set { item = value; }
        }

        private object icon;
        public object Icon
        {
            get { return icon; }
            set { icon = value; }
        }
    }

{% endhighlight %}
{% endtabs %}

### ViewModel

{% tabs %}
{% highlight c# %}

     public class ViewModel
    {
        public ObservableCollection<Model> Items { get; set; }
        ObservableCollection<Model> SubItems = new ObservableCollection<Model>();
      
        public ViewModel()
        {
            Items = new ObservableCollection<Model>();
            SubItems.Add(new Model()
            {
                Item = "Item1",
            });
            SubItems.Add(new Model()
            {
                Item = "Item2",
            }); SubItems.Add(new Model()
            {
                Item = "Item3",
            });
            Items.Add(new Model()
            {
                Item = "Explore",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 16,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.0033803,5.705333 L7.0853577,8.4971852 9.9112849,10.241092 8.6573143,7.3392491 z M5.0022244,4.0000064 C5.0918167,4.0004316 5.1818919,4.0249844 5.2623992,4.0744188 L9.3152895,6.5702889 C9.4033003,6.6242869 9.4722991,6.7032812 9.5132833,6.7982774 L11.459255,11.302037 C11.545252,11.502027 11.492244,11.735016 11.327239,11.879006 11.233247,11.959003 11.117252,12.000002 11.00025,12.000002 10.909249,12.000002 10.818278,11.976001 10.737256,11.926004 L6.4163659,9.2601452 C6.3233503,9.2021494 6.252368,9.1161518 6.2133675,9.0151591 L4.5334113,4.6813889 C4.4563866,4.4803993 4.5154063,4.2534102 4.6804113,4.1164165 4.7726429,4.0387974 4.8870345,3.9994598 5.0022244,4.0000064 z M8,1 C4.14,1 1,4.1409999 1,8 1,11.86 4.14,15 8,15 11.859,15 15,11.86 15,8 15,4.1409999 11.859,1 8,1 z M8,0 C12.411,0 16,3.5889999 16,8 16,12.411 12.411,16 8,16 3.589,16 0,12.411 0,8 0,3.5889999 3.589,0 8,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                },
                SubItems=SubItems
            });
            Items.Add(new Model()
            {
                Item = "My music",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 14.7,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M2.5,10.701 C1.6729736,10.701 1,11.373997 1.0000001,12.201 1,13.027996 1.6729736,13.701 2.5,13.701 3.3269958,13.701 4,13.027996 4,12.201 L3.9999866,12.200474 3.9980443,12.123936 C3.9577868,11.332592 3.3011522,10.701 2.5,10.701 z M13.499987,8.7009979 C12.672987,8.7009979 11.999987,9.373998 11.999987,10.200998 11.999987,11.027998 12.672987,11.700998 13.499987,11.700998 14.326986,11.700998 14.999987,11.027998 14.999987,10.200998 14.999987,9.373998 14.326986,8.7009979 13.499987,8.7009979 z M14.515357,1.0003309 C14.481983,0.99951458 14.446487,1.0020571 14.408987,1.0089951 L5.4099865,2.6579952 C5.1719866,2.700995 4.9999866,2.9079952 4.9999866,3.1489954 L4.9999866,4.7396889 14.999987,2.9069619 14.999987,1.5009947 C14.999987,1.2969952 14.886987,1.1729946 14.819986,1.1159945 14.764736,1.0704947 14.659975,1.0038691 14.515357,1.0003309 z M14.477699,0.00021648407 C14.835276,-0.0058488846 15.181299,0.11561966 15.459987,0.3479948 15.802987,0.63499451 15.999987,1.0549946 15.999987,1.5009947 L15.999987,10.200997 C15.999987,11.579998 14.877987,12.700998 13.499987,12.700998 12.120987,12.700998 10.999987,11.579998 10.999987,10.200998 10.999987,8.822998 12.120987,7.7009981 13.499987,7.7009981 14.059799,7.7009981 14.577362,7.8861719 14.994612,8.1984568 L14.999987,8.2026836 14.999987,3.9231343 4.9999866,5.755861 4.9999866,12.200465 5,12.201 C5,13.579998 3.8779907,14.701 2.5,14.701 1.1209717,14.701 0,13.579998 0,12.201 0,10.822994 1.1209717,9.7010002 2.5,9.7010002 3.0598087,9.7010002 3.5773706,9.8861731 3.9946208,10.198457 L3.9999866,10.202677 3.9999866,3.1489954 C3.9999866,2.4249949 4.5169868,1.8049951 5.2289867,1.6749945 L14.228987,0.02499485 C14.312049,0.0098075867 14.395182,0.0016155243 14.477699,0.00021648407 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Recommended",
                Icon = new Path()
                {
                    Width = 14,
                    Height = 14,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M11.5,10 C11.224,10 11,10.225 11,10.5 L11,13 11.5,13 C12.327,13 13,12.327 13,11.5 L13,10 z M1.0000133,9.9999933 L1.0000133,11.499993 C1.0000133,12.327004 1.672987,12.999993 2.5000133,12.999993 L3.0000133,12.999993 3.0000133,10.499993 C3.0000133,10.224999 2.7750072,9.9999933 2.5000133,9.9999933 z M7,0 C10.859,0 14,3.1409998 14,7 L14,9.4999999 14,10 14,11.5 C14,12.879 12.878,14 11.5,14 L10.5,14 C10.224,14 10,13.776 10,13.5 L10,10.5 C10,9.6729999 10.673,8.9999999 11.5,8.9999999 L13,8.9999999 13,7 C13,3.691 10.309,1 7,1 3.691,1 0.99999999,3.691 0.99999993,7 L0.99999993,8.9999934 2.5000133,8.9999934 C3.3270092,8.9999933 4.0000133,9.6729975 4.0000133,10.499993 L4.0000133,13.499993 C4.0000133,13.775994 3.7760143,13.999993 3.5000133,13.999993 L2.5000133,13.999993 C1.120985,13.999993 1.3340759E-05,12.879006 1.335144E-05,11.499993 L1.335144E-05,10 0,7 C1.0681106E-08,3.1409998 3.1400001,0 7,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Recent Playlist",
                Icon = new Path()
                {
                    Width = 15,
                    Height = 15,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M6.9990103,3.0000041 L7.9990076,3.0000041 7.9990076,7.270998 11.32401,10.121002 10.674018,10.880004 6.9990103,7.7310042 z M7.5,1 C3.9160001,1 1,3.916 1,7.5 1,11.084 3.9160001,14 7.5,14 11.084,14 14,11.084 14,7.5 14,3.916 11.084,1 7.5,1 z M7.5,0 C11.636,0 15,3.3640001 15,7.5 15,11.636 11.636,15 7.5,15 3.3640001,15 0,11.636 0,7.5 0,3.3640001 3.3640001,0 7.5,0 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
            Items.Add(new Model()
            {
                Item = "Radio",
                Icon = new Path()
                {
                    Width = 16,
                    Height = 15.4,
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center,
                    Data = Geometry.Parse("M2.5,11.472009 L6.5,11.472009 C6.776,11.472009 7,11.696009 7,11.972009 7,12.248009 6.776,12.472009 6.5,12.472009 L2.5,12.472009 C2.224,12.472009 2,12.248009 2,11.972009 2,11.696009 2.224,11.472009 2.5,11.472009 z M2.5,8.4720092 L6.5,8.4720092 C6.776,8.4720092 7,8.6960092 7,8.9720092 7,9.2480091 6.776,9.4720092 6.5,9.4720092 L2.5,9.4720092 C2.224,9.4720092 2,9.2480091 2,8.9720092 2,8.6960092 2.224,8.4720092 2.5,8.4720092 z M11.000013,8.4720025 C9.8960094,8.4720025 9.0000134,9.3690057 9.0000134,10.472003 9.0000134,11.576006 9.8960094,12.472003 11.000013,12.472003 12.10301,12.472003 13.000013,11.576006 13.000013,10.472003 13.000013,9.3690057 12.10301,8.4720025 11.000013,8.4720025 z M11.000013,7.4720025 C12.654005,7.4720025 14.000013,8.8180108 14.000013,10.472003 14.000013,12.126009 12.654005,13.472003 11.000013,13.472003 9.3459911,13.472003 8.0000134,12.126009 8.0000134,10.472003 8.0000134,8.8180108 9.3459911,7.4720025 11.000013,7.4720025 z M1.5,6.4720092 C1.2290001,6.4720091 1,6.6560091 1,6.872009 L1,14.073009 C1,14.289009 1.2290001,14.472009 1.5,14.472009 L14.5,14.472009 C14.771,14.472009 15,14.289009 15,14.073009 L15,6.872009 C15,6.6560091 14.771,6.4720091 14.5,6.4720092 z M12.877348,0.00054502487 C13.071978,-0.0085949898 13.261545,0.097710133 13.351547,0.28444672 13.47155,0.53342915 13.365548,0.83140802 13.116541,0.9513998 L3.6977077,5.4720092 14.5,5.4720092 C15.327,5.4720092 16,6.1000091 16,6.872009 L16,14.073009 C16,14.844009 15.327,15.472009 14.5,15.472009 L1.5,15.472009 C0.67299986,15.472009 0,14.844009 0,14.073009 L0,6.872009 C0,6.148259 0.59150362,5.5510716 1.346869,5.4792504 L1.3769317,5.4771099 12.684531,0.049463272 C12.747032,0.019465446 12.812471,0.0035915375 12.877348,0.00054502487 z"),
                    Fill = new SolidColorBrush(Colors.Black),
                    Stretch = Stretch.Fill,
                }
            });
        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <Window.Resources>
        <Style x:Key="ItemStyle" TargetType="syncfusion:NavigationItem">
            <Setter Property="Icon" Value="{Binding Icon}" />
            <Setter Property="DisplayMemberPath" Value="Item" />
            <Setter Property="ItemsSource" Value="{Binding SubItems}" />
        </Style>
    </Window.Resources>
    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMemberPath="Item"
        DisplayMode="Expanded"
        ItemContainerStyle="{StaticResource ItemStyle}"
        ItemsSource="{Binding Items}">
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


## IndentationWidth

This property used to change the horizontal position of sub items. Left margin of the sub items depends on the IndentationWidth property.
