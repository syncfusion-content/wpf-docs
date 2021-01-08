---
layout: post
title: Create a Diagram Ribbon to interact with the SfDiagram | Syncfusion.
description: A walk through the usage of the Diagram ribbon and the items present in a Diagram ribbon to interact with the diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

# WPF Diagram Ribbon (SfDiagramRibbon) in the WPF Diagram (SfDiagram)

The diagram ribbon control is a user interface that hosts a Quick Access Toolbar, Application Menu, and Tabs to provide the most common features and settings for the WPF Diagram. The diagram ribbon control contains the UI elements that allow end-users to load and save diagrams, add diagram items to the canvas, format text within the diagram items, rearrange and recolor shapes, change the canvas size and orientation, and perform a copy and paste operations.

![DiagramRibbon](Diagram-Ribbon_images/DiagramRibbon.png)

The following table lists actions that end-users can perform using the Diagram Ribbon.

| Ribbon Tab | Ribbon Bar | Actions |
|---|---|---|
| Home | Clipboard | Cut, Copy, and Paste operations. |
|  | Font | Change the font settings of the selected shape. |
|  | Alignment | Realign the text within the selected shape. |
|  | Tools | Select a tool. |
|  | Shape Styles | Change the background and border colors for the currently selected shape using a palette of predefined patterns or by selecting the colors individually using color pickers. |
|  | Arrange | Change the position or alignment of the selected shapes and move the selected shapes in and out in the Z-order.
|  | Select | Select all the diagram items or by specific type. |
| Insert | Diagram Parts | Allows you to add an image item or connection line to the canvas. |
| Design | Page Setup | Toggle between portrait and landscape page orientation, set the page size. |
|  | Background | Apply a background style to the page. |
|  | Connectors | Change the appearance of the connection lines in the canvas. |
| View | Show | Toggle the visibility of the Zoom Pan window, Rulers, Gridlines, and Page Breaks. |
|  | Zoom | Zoom the diagram so that the entire page either fits the window or is as wide as the window. |

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#diagram-ribbon) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link:
[How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages)

## Adding Diagram Ribbon

The following section helps you to add the SfDiagramRibbon in your application with the SfDiagram.

The SfDiagramRibbon control can be added to the application by dragging it from the toolbox and dropping it in the designer view. The required assembly references will be added automatically.

![DiagramRibbonfromToolbox](Diagram-Ribbon_images/DiagramRibbonToolbox.png)

Steps to add the Diagram ribbon control manually is given below with its code example.

1. Add the following required assembly reference to the project `Syncfusion.SfDiagramRibbon.WPF`.

2. Import the Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or the SfDiagramRibbon control namespace `Syncfusion.UI.Xaml.DiagramRibbon` in your application.

3. Declare the SfDiagramRibbon control in your application.

{% tabs %}

{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfDiagram_WPF"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        x:Class="SfDiagram_WPF.MainWindow"
        mc:Ignorable="d" Title="MainWindow" Height="350" Width="525">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>        
        <syncfusion:SfDiagramRibbon DataContext="{Binding ElementName=Diagram}" Grid.Row="0"/>
        <syncfusion:SfDiagram x:Name="Diagram" Grid.Row="1">
            <syncfusion:SfDiagram.Theme>
                <syncfusion:OfficeTheme/>
            </syncfusion:SfDiagram.Theme>
            <syncfusion:SfDiagram.Nodes>
                <syncfusion:NodeCollection/>
            </syncfusion:SfDiagram.Nodes>
            <syncfusion:SfDiagram.Connectors>
                <syncfusion:ConnectorCollection/>
            </syncfusion:SfDiagram.Connectors>            
        </syncfusion:SfDiagram>
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Diagram;
using Syncfusion.UI.Xaml.Diagram.Theming;
using Syncfusion.UI.Xaml.DiagramRibbon;

namespace SfDiagram_WPF
{   
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();

            // Initialize, arrange and add a diagram and Diagram ribbon in the application
            
            SfDiagram Sfdiagram = new SfDiagram() { Theme = new OfficeTheme(), Nodes = new NodeCollection(), Connectors = new ConnectorCollection() };
            SfDiagramRibbon sfDiagramRibbon = new SfDiagramRibbon() { DataContext = Sfdiagram };

            Sfdiagram.SetValue(Grid.RowProperty, 1);
            sfDiagramRibbon.SetValue(Grid.RowProperty, 0);

            Root_Grid.Children.Add(Sfdiagram);
            Root_Grid.Children.Add(sfDiagramRibbon);
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Simple Diagram Designer

This section describes how to build a simple diagram designer application with diagram ribbon, and diagram control.

N> You have to set the diagram as DataContext for the Diagram ribbon control, which will help the users to interact with the diagram by using the Diagram ribbon control.

{% tabs %}

{% highlight xaml %}

<Grid>

    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>

    <syncfusion:SfDiagramRibbon x:Name="DiagramRibbon" Grid.Row="0" DataContext="{Binding ElementName=Diagram}"/>
    <syncfusion:SfDiagram x:Name="Diagram" Grid.Row="1" Constraints="Undoable,Default">
        <syncfusion:SfDiagram.Theme>
            <syncfusion:OfficeTheme/>                
        </syncfusion:SfDiagram.Theme>
        <syncfusion:SfDiagram.Nodes>
            <syncfusion:NodeCollection/>
        </syncfusion:SfDiagram.Nodes>
        <syncfusion:SfDiagram.Connectors>
            <syncfusion:ConnectorCollection/>
        </syncfusion:SfDiagram.Connectors>
        <syncfusion:SfDiagram.Groups>
            <syncfusion:GroupCollection/>
        </syncfusion:SfDiagram.Groups>
        <syncfusion:SfDiagram.SnapSettings>
            <syncfusion:SnapSettings SnapConstraints="All"/>
        </syncfusion:SfDiagram.SnapSettings>
        <syncfusion:SfDiagram.HorizontalRuler>
            <syncfusion:Ruler Orientation="Horizontal"/>
        </syncfusion:SfDiagram.HorizontalRuler>
        <syncfusion:SfDiagram.VerticalRuler>
            <syncfusion:Ruler Orientation="Vertical"/>
        </syncfusion:SfDiagram.VerticalRuler>
    </syncfusion:SfDiagram>
    
</Grid>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetTheme(this, new Syncfusion.SfSkinManager.Theme() { ThemeName = "Office2019Colorful" });

// Initialize, arrange and add a diagram and Diagram ribbon in the application

SfDiagram Sfdiagram = new SfDiagram()
{
    Theme = new OfficeTheme(),
    Nodes = new NodeCollection(),
    Connectors = new ConnectorCollection(),
    Groups = new GroupCollection(),
    Constraints = GraphConstraints.Default | GraphConstraints.Undoable,
    SnapSettings = new SnapSettings() { SnapConstraints = SnapConstraints.All },
    HorizontalRuler = new Syncfusion.UI.Xaml.Diagram.Controls.Ruler() { Orientation = Orientation.Horizontal },
    VerticalRuler = new Syncfusion.UI.Xaml.Diagram.Controls.Ruler() { Orientation = Orientation.Vertical },
};

SfDiagramRibbon sfDiagramRibbon = new SfDiagramRibbon() { DataContext = Sfdiagram };

Sfdiagram.SetValue(Grid.RowProperty, 1);
sfDiagramRibbon.SetValue(Grid.RowProperty, 0);

Root_Grid.Children.Add(Sfdiagram);
Root_Grid.Children.Add(sfDiagramRibbon);
    
{% endhighlight %}

{% endtabs %}

![DiagramRibbonfromToolbox](Diagram-Ribbon_images/DiagramDesigner.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Diagram%20Ribbon)

## Ribbon Customization

The Ribbon customization can be done in two ways.

### Using Control Template

An user can customize the ribbon items by overriding the template of the [SfDiagramRibbon](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.DiagramRibbon.SfDiagramRibbon.html).

### Using Tabs property in Events

By invoking the SfDiagramRibbon loaded event, a user can add or delete the ribbon tabs, and ribbon items with the help of [Tabs Property](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.DiagramRibbon.SfDiagramRibbon.html#Syncfusion_UI_Xaml_DiagramRibbon_SfDiagramRibbon_Tabs) in the `SfDiagramRibbon`.

#### Adding RibbonTab

To add a custom ribbon tab with the default tabs in the `SfDiagramRibbon`.

{% tabs %}

{% highlight C# %}

DiagramRibbon.Loaded += DiagramRibbon_Loaded;

private void DiagramRibbon_Loaded(object sender, RoutedEventArgs e)
{
    // Add a new Ribbon tab.
    RibbonTab FormatTab = new RibbonTab() { Caption = "Format" };
    (sender as SfDiagramRibbon).Tabs.Add(FormatTab);
}

{% endhighlight %}

{% endtabs %}

#### Removing Ribbon Tab

To remove a ribbon tab from the default tabs in `SfDiagramRibbon`.

{% tabs %}

{% highlight C# %}

DiagramRibbon.Loaded += DiagramRibbon_Loaded;

private void DiagramRibbon_Loaded(object sender, RoutedEventArgs e)
{
    // Remove the Insert tab.
    (sender as SfDiagramRibbon).Tabs.RemoveAt(1);
}

{% endhighlight %}

{% endtabs %}

#### Adding RibbonItems

To add a custom ribbon item with the default items in an already existing ribbon tab.

{% tabs %}

{% highlight C# %}

DiagramRibbon.Loaded += DiagramRibbon_Loaded;

private void DiagramRibbon_Loaded(object sender, RoutedEventArgs e)
{
    // Add new Ribbon Item.
    RibbonTab InsertTab = (sender as SfDiagramRibbon).Tabs.ElementAt(1);
    InsertTab.Items.Add(new RibbonBar() { Header = "Links" });
}

{% endhighlight %}

{% endtabs %}

#### Removing Ribbon Tab

To remove an already existing ribbon item from the ribbon tab.

{% tabs %}

{% highlight C# %}

DiagramRibbon.Loaded += DiagramRibbon_Loaded;

private void DiagramRibbon_Loaded(object sender, RoutedEventArgs e)
{
    // Remove the alignment bar from the Home Tab.
    RibbonTab HomeTab = (sender as SfDiagramRibbon).Tabs.ElementAt(0);
    HomeTab.Items.RemoveAt(2);
}

{% endhighlight %}

{% endtabs %}