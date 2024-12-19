---
layout: post
title: Getting Started with WPF Circular ProgressBar control | Syncfusion&reg;
description: Learn here about getting started with Syncfusion&reg; WPF Circular ProgressBar (SfCircularProgressBar) control, its elements and more details.
platform: wpf
control: SfCircularProgressBar
documentation: ug
---

# Getting Started with WPF Circular ProgressBar (SfCircularProgressBar)

You can create a WPF application with the SfCircularProgressBar control using the following steps:

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: [How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages)

## Adding control through designer

The SfCircularProgressBar control can be added to a WPF application by dragging it from the toolbox to a designer view. The following assembly reference will be added automatically:

* Syncfusion.SfProgressBar.WPF 

![WPF SfCircularProgressBar control added through designer](Getting-Started_images/wpf-SfCircularProgressBar-control-added-through-designer.png)

## Adding control manually in XAML

To add control manually in XAML, follow the given steps:

1. Add the following required assembly references to the project:
    * Syncfusion.SfProgressBar.WPF     
2. Import Syncfusion&reg; WPF schema **http://schemas.syncfusion.com/wpf** the in XAML page.
3. Declare the SfCircularProgressBar control in the XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight XAML %}
<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp4"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApp4.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
     <Grid x:Name="grid">       
       <Syncfusion:SfCircularProgressBar  Progress="50"  Width="347"/>
      </Syncfusion:SfCircularProgressBar>
        </Grid>
</Window>
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}


## Adding  control through code behind

To add control manually through code behind, follow the given steps:

1. Add the following required assembly references to the project:
    * Syncfusion.SfProgressBar.WPF
2. Import the Circular ProgressBar namespace **using Syncfusion.UI.Xaml.ProgressBar;**.
3. Create an Circular ProgressBar instance, and add it to the window.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}
using Syncfusion.UI.Xaml.ProgressBar;
namespace SfProgressBar
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {                  
        public MainWindow()
        {
            InitializeComponent();      
                
            SfCircularProgressBar circular = new SfCircularProgressBar();
            circular.Progress = 50; 
            circular.Width = 347; 
            grid.Children.Add(circular);

        }      
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}


![wpf Circular ProgressBar control added through code](Getting-Started_images/wpf-SfCircularProgressBar-control-added-manually.png)

The complete source for this demo can be downloaded [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/CircularProgressbarSample-990574246)

## Theme

Circular ProgressBar supports various built-in themes. Refer to the below links to apply themes for the Circular ProgressBar,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to wpf Circular ProgressBar control](Getting-Started_images/wpf-SfCircularProgressBar-theme-support.png)