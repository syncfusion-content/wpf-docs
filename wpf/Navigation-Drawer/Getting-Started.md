---
layout: post
title: Getting Started with WPF Navigation Drawer Control | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF Navigation Drawer (SfNavigationDrawer) control, including its elements and more details.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Getting Started with WPF Navigation Drawer (SfNavigationDrawer)

This section will guide you through building your application with the SfNavigationDrawer.

## Assembly Deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfnavigationdrawer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.
Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfnavigationdrawer) section to get the list of assemblies or NuGet packages that need to be referenced to use the control in any application.

For more details on installing NuGet packages in a WPF application, refer to the linked documentation.
## Creating a Simple Application with SfNavigationDrawer

- Creating the Project
- Adding SfNavigationDrawer from Toolbox
- Adding SfNavigationDrawer Control via XAML
- Adding Control Manually in C#
- Adding Content to the Control
- Adding Sidebar Menu Items

### Creating the Project

Create a new WPF Project in Visual Studio to display SfNavigationDrawer with data objects.

### Adding SfNavigationDrawer from Toolbox

Drag and drop the SfNavigationDrawer control from the Toolbox into your application.

![WPF NavigationDrawer in Toolbox](getting-started_images/wpf-navigation-drawer-toolbox.png)

This action adds the Syncfusion<sup>®</sup> Controls for UWP XAML reference to the application and generates the xmlns namespace code in MainWindow.xaml as shown below.

![WPF NavigationDrawer Reference Display](getting-started_images/wpf-navigation-drawer-reference.png)

![WPF NavigationDrawer with Namespace](getting-started_images/wpf-navigation-drawer-namespace.png)

### Adding Control Manually in XAML

To manually add the control via XAML, perform the following steps:
1. Add the required assembly references to the project:
   - Syncfusion.SfNavigationDrawer.WPF
2. Import the Syncfusion<sup>®</sup> WPF schema **http://schemas.syncfusion.com/wpf** into the XAML page.
3. Declare the SfNavigationDrawer control in the XAML page.

{% capture codesnippet1 %}
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
    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer"/>
</Window>
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

### Adding Control Manually in C#

To manually add the control via C#, perform the following steps:
1. Add the required assembly references to the project:
   - Syncfusion.SfNavigationDrawer.WPF
2. Import the SfTreeView namespace **Syncfusion.UI.Xaml.NavigationDrawer**.
3. Create an SfNavigationDrawer control instance and add it to the Page.

{% capture codesnippet2 %}
{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.NavigationDrawer;
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
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            this.Content = navigationDrawer;
        }
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

## Adding Content to the Control

{% tabs %}

{% highlight xml %}

	<syncfusion:SfNavigationDrawer>
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

## Adding Sidebar Menu Items

The sidebar menu can be populated using built-in items. The items will be of type [NavigationItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.NavigationItem.html), offering various properties for customization.

For more information, see the [Different Display Modes](https://help.syncfusion.com/wpf/navigation-drawer/different-display-modes) topic in SfNavigationDrawer.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Expanded">
        <syncfusion:NavigationItem
                Header="Inbox"
                IsExpanded="True"
                IsSelected="True">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M32.032381, 16.445429 L25.410999, ... />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.5189972,7.3780194C8.3389893,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M22.133972,14.194015C17.582977,... />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.4614787,7.2521966C8.897512,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M42.128046,6.7269681 L18.53705,..../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Important">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,...../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M6.9999996,48.353 L19,48.353 19,..../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem ItemType="Separator" />
        <syncfusion:NavigationItem Header="All Labels" ItemType="Header" />
        <syncfusion:NavigationItem Header="Starred">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="All mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M12,32.999999 L26,32.999999 26,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Trash">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M17,12 L19,12 19,42 17,42z M10.998,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Spam">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M33.671003,29.293001 L39.214003,.../>
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
            navigationDrawer.DisplayMode = DisplayMode.Expanded;
            NavigationItemsCollection navigationSubItems = new NavigationItemsCollection();
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Primary",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.5189972,7.3780194C8.3389893,...),
                    ......
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Social",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M22.133972,14.194015C17.582977,....),
                    .....
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Promotions",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.4614787,7.2521966C8.897512,....),
                    .....
                },

            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, ....),
                    ......
                },
                Items = navigationSubItems,
                IsExpanded = true,
                IsSelected=true
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.9999996,48.353 L19,....),
                    ....
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                ItemType = ItemType.Separator
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                ItemType = ItemType.Header,
                Header= "All Labels"
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Starred",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M25.085007,5.9780004 L20.577011,....),
                    .....
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "All mail",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M12,32.999999 L26,32.999999 26,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Trash",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M17,12 L19,12 19,42 17,42z M10.998,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Spam",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M33.671003,29.293001 L39.214003,....),
                    .........
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

![WPF NavigationDrawer](getting-started_images/wpf-navigation-drawer.png)
                   
> **Note:** View [sample on GitHub](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Getting_Started).
