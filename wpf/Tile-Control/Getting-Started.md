---
layout: post
title: Getting Started with WPF Tile Control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF Tile Control, its elements and more.
platform: wpf
control: SfHubTile
documentation: ug
---

# Getting Started with WPF Tile Control

This section gives an overview for working with the Hub Tile and Pulsing Tile controls.

## Assembly deployment

Refer [Hub Tile](https://help.syncfusion.com/wpf/control-dependencies#sfhubtile) and [Pulsing Tile](https://help.syncfusion.com/wpf/control-dependencies#sfpulsingtile) control dependencies section to get the list of assemblies or [NuGet package](https://help.syncfusion.com/wpf/installation/install-nuget-packages) needs to be added as reference to use the Hub Tile and Pulsing Tile control in any application.

## Creating a simple application with Hub Tile and Pulsing Tile

In this walkthrough, a WPF application that contains Hub Tile and Pulsing Tile controls can be created. The controls can be added in the following ways:

1. [Adding control via Designer](#adding-control-via-designer)
2. [Adding control manually in XAML](#adding-control-manually-in-xaml)
3. [Adding control manually in C#](#adding-control-manually-in-c)

### Adding control via Designer

Hub Tile and Pulsing Tile controls can be added to the application by dragging SfHubTile and SfPulsingTile from toolbox and dropping it in designer view. After dropping the controls in designer view, the assemblies such as **Syncfusion.SfHubTile.WPF** and **Syncfusion.SfShared.WPF** get added into the project automatically. The following code snippets will also be added to XAML.

{% tabs %}
{% highlight XAML %}
<!--For Hub Tile-->
<syncfusion:SfHubTile Content="SfHubTile" HorizontalAlignment="Left" VerticalAlignment="Top"/>
<!--For Pulsing Tile-->
<syncfusion:SfPulsingTile Content="SfPulsingTile" HorizontalAlignment="Left" VerticalAlignment="Top"/>
{% endhighlight %}
{% endtabs %}

N> `syncfusion` in XAML is an auto-generated namespace.

![wpf hub tile control added by designer](Getting-Started_images/Hubtile.png)

![wpf pulsing tile control added by designer](Getting-Started_images/Pulsingtile.png)
	
### Adding control manually in XAML

To add the control manually in XAML, follow these steps:

1. Add the following required assembly references to the project.
	* Syncfusion.SfHubTile.WPF
	* Syncfusion.SfShared.WPF
2. Import the Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or the tile control namespace `Syncfusion.Windows.Controls.Notification` in the XAML page.
3. Declare `SfHubTile` and `SfPulsingTile` controls in the XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
			xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
			xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
			x:Class="WpfApplication1.MainWindow"
			Title="MainWindow" Height="350" Width="525">
	 <Grid x:Name="grid">
    	<!--Hub Tile-->
    	<syncfusion:SfHubTile Content="This is a Hub Tile" HorizontalAlignment="Left"/>
    	<!--Pulsing Tile-->
    	<syncfusion:SfPulsingTile Content="This is a Pulsing Tile" HorizontalAlignment="Right"/>
	</Grid>
</Window>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

### Adding control manually in C#

To add the control manually in C#, follow these steps:

1. Add the following required assembly references to the project.
	* Syncfusion.SfHubTile.WPF
	* Syncfusion.SfShared.WPF
2. Import the `Syncfusion.Windows.Controls.Notification` namespace.
3. Create instances of `SfHubTile` and `SfPulsingTile` and add them to the window.

{% capture codesnippet2 %}
{% highlight C# %}

using Syncfusion.Windows.Controls.Notification;
namespace WpfApplication1
{	
	public partial class MainWindow : Window
	{
		public MainWindow()
		{          
			InitializeComponent();
			// Hub Tile
			SfHubTile hubTile = new SfHubTile();
			hubTile.Content="This is a Hub Tile";
			hubTile.HorizontalAlignment = HorizontalAlignment.Left;
			grid.Children.Add(hubTile);

			//Pulsing Tile
			SfPulsingTile pulseTile = new SfPulsingTile();
			pulseTile.Content="This is a Pulsing Tile";
			pulseTile.HorizontalAlignment = HorizontalAlignment.Right;
			grid.Children.Add(pulseTile);
		}
	}
}

{% endhighlight %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

## Setting Title, Header, and Image in the Tile

The title, header and image for the tile can be set by using [Title](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_Title), [Header](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.HeaderedContentControl.html#Syncfusion_Windows_Primitives_HeaderedContentControl_Header) and [ImageSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.HubTileBase.html#Syncfusion_Windows_Controls_Notification_HubTileBase_ImageSource) properties respectively.

![wpf hub tile structure](Getting-Started_images/wpf-hubtile.png)

Hub Tile
{:.caption}

![wpf pulsing tile structure](Getting-Started_images/pulsingtile-image.png)

Pulsing Tile
{:.caption}

N> The title is displayed at the top of the tile, the header is displayed at the bottom of the tile, and the image is displayed at the center of the tile.

## Theme

Hub Tile and Pulsing Tile controls support various built-in themes. Refer to the following links to apply themes to the Hub Tile and Pulsing Tile:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Hub Tile and Pulsing Tile controls](Getting-Started_images/Theme.png)
