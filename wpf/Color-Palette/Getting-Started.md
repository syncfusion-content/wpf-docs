---
layout: post
title: Getting Started with WPF SfColorPalette | Syncfusion®
description: Learn how to get started with the Syncfusion WPF SfColorPalette control, its elements, and more details.
platform: wpf
control: SfColorPalette
documentation: ug
---

# Getting Started with WPF Color Palette

This section explains how to create a [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) and explains about its structure and features.


## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfcolorpalette) section to get the list of assemblies or `NuGet` package that needs to be added as a reference to use the control in any application.

Refer to this [documentation](https://help.syncfusion.com/wpf/installation/install-nuget-packages) to find more details about installing nuget packages in a WPF application.

## Creating Application with WPF Color Palette control

In this walk through, user will create a WPF application that contains [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control.

 1. Creating project
 2. Adding  control via designer.
 3. Adding  control manually in XAML.
 4. Adding  control manually in C#.

### Creating project

Below section provides detailed information to create new project in Visual Studio to display [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html).

### Adding control via designer

The [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control can be added to the application by dragging it from Toolbox and dropping it in designer. The required assembly will be added automatically.

* Syncfusion.SfColorPalette.WPF
* Syncfusion.SfShared.WPF

![WPF Color Palette Drag and dropped from ToolBox](getting-started_images/wpf-color-palette-drag-and-drop-from-toolbox.png)

### Adding control manually in XAML

In order to add [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control manually in XAML, do the below steps,

1. Add the below required assembly references to the project,

	  * Syncfusion.SfColorPalette.Wpf

    * Syncfusion.SfShared.Wpf

2. Import Syncfusion<sup>®</sup> WPF schema **http://schemas.syncfusion.com/wpf** or WPF Color Palette namespace [**Syncfusion.Windows.Controls.Media**](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.html) in XAML page.

3. Declare [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control in XAML page.

{% capture codesnippet1 %}
{% tabs %}

{% highlight xaml %}

<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Check_UG"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="Check_UG.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
<Grid>
<syncfusion:SfColorPalette HorizontalAlignment="Left" Margin="90,50,0,0" VerticalAlignment="Top" Height="206" Width="239"/>

</Grid>
</Window>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![WPF Color Palette added by xaml code](getting-started_images/wpf-color-palette-xaml-code.png)

### Adding control manually in C#

In order to add [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control manually in C#, do the below steps,

1. Add the below required assembly references to the project,

	  * Syncfusion.SfColorPalette.Wpf

    * Syncfusion.SfShared.Wpf

2. Import WPF Color Palette namespace **Syncfusion.Windows.Controls.Media** .

{% capture codesnippet2 %}
{% tabs %}

{% highlight c# %}

using Syncfusion.Windows.Controls.Media;

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

3. Create [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control instance and add it to the Page.

{% capture codesnippet3 %}
{% tabs %}
{% highlight c# %}

    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();

            SfColorPalette colorPalette = new SfColorPalette();
            colorPalette.Height = 300;
            colorPalette.Width = 200;

            this.Content = colorPalette;
        }
    }

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet3 | OrderList_Indent_Level_1 }}

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/DataBinding)

## Select a Color

You can select any color by clicking the respective color item in the [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html). You can get the selected color from the [SelectedColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html#Syncfusion_Windows_Controls_Media_SfColorPalette_SelectedColor) property. When you select a color, the color value is also displayed in a tooltip.

![Select a color from the WPF Color Palette](getting-started_images/wpf-color-palette-selected-color.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/DataBinding)

## Binding a selected color

You can bind the selected color of the [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) to any UI element by using the [SelectedColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html#Syncfusion_Windows_Controls_Media_SfColorPalette_SelectedColor) property.

In the example below, the `SelectedColor` of the `WPF Color Palette` is bound to the `Rectangle.Fill` property through a color-to-brush value converter.

{% tabs %}
{% highlight C# %}

//ColorToBrushConverter.cs
public class ColorToSolidColorBrushValueConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        if (null == value)
            return null;
        Color color = (Color)value;
        return new SolidColorBrush(color);
    }
    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        return true;
    }
}

{% endhighlight %}
{% endtabs %}

> The C# converter class above requires the following `using` directives: `System`, `System.Globalization`, `System.Windows.Data`, and `System.Windows.Media`.

{% tabs %}
{% highlight xaml %}

<Grid>
    <Grid.Resources>

    <!--Color to brush converter-->
        <local:ColorToSolidColorBrushValueConverter  x:Key="ColorToSolidColorBrush_ValueConverter"/>
    </Grid.Resources>
    <StackPanel>
        <TextBlock Text="SelectedColor"/>
        <Rectangle Fill="{Binding ElementName=SfColorPalette ,
                                  Path= SelectedColor, 
                                  Converter={StaticResource ColorToSolidColorBrush_ValueConverter}}"/>
        <syncfusion:SfColorPalette x:Name="SfColorPalette" />
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Binding a selected color in WPF Color Palette](getting-started_images/wpf-color-palette-binding.gif)

N>  [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/DataBinding)

## Navigate to the list of swatches

You can navigate to and select different colors from the various swatches by clicking the Swatches button, which is placed on the top-right corner of the [WPF Color Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control.

### List of swatches

![List of swatches in WPF Color Palette](getting-started_images/wpf-color-palette-swatches-list.png)

![Navigate and change the color swatches in WPF Color Palette](getting-started_images/wpf-color-palette-navigate-swatches.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/DataBinding).

## Theme

The WPF Color Palette supports various built-in themes. Refer to the links below to apply themes:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Color Palette](getting-started_images/wpf-color-palette-theme-support.png)
  
N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/Themes).
