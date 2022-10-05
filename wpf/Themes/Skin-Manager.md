---
layout: post
title: WPF Skin Manager | Apply Themes for Syncfusion WPF controls
description: Learn about how to apply the themes for Syncfusion WPF controls and Framework controls using the skin manager.
platform: wpf
control: Themes
documentation: ug
---
# Getting Started with WPF Skin Manager

The [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) helps you to apply the themes for both Syncfusion and Framework controls. There are 27 built-in themes that can be applied using the `SfSkinManager` for a rich user interface experience. Some of the built-in themes color derivations can be customized using [WPF Theme Studio](https://help.syncfusion.com/wpf/themes/theme-studio).

N> Theme Studio-based themes provide improved consistency and uniqueness among various controls when compared to other themes. It is preferable to use Theme Studio-based themes in the application over other themes. 

## Themes list

The following table lists the available themes as well as the assembly or NuGet reference to be used in the application. 

<table>
<tr>
<th>
Styles</th><th>
Assembly</th><th>
NuGet package</th></tr>
<tr>
<td>
FluentLight</td><td>
Syncfusion.Themes.FluentLight.Wpf.dll</td><td>
{{'[Syncfusion.Themes.FluentLight.WPF](https://www.nuget.org/packages/Syncfusion.Themes.FluentLight.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
FluentDark</td><td>
Syncfusion.Themes.FluentDark.Wpf.dll</td><td>
{{'[Syncfusion.Themes.FluentDark.WPF](https://www.nuget.org/packages/Syncfusion.Themes.FluentDark.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialLight</td><td>
Syncfusion.Themes.MaterialLight.Wpf.dll</td><td>
{{'[Syncfusion.Themes.MaterialLight.WPF](https://www.nuget.org/packages/Syncfusion.Themes.MaterialLight.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialDark</td><td>
Syncfusion.Themes.MaterialDark.Wpf.dll</td><td>
{{'[Syncfusion.Themes.MaterialDark.WPF](https://www.nuget.org/packages/Syncfusion.Themes.MaterialDark.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialLightBlue</td><td>
Syncfusion.Themes.MaterialLightBlue.Wpf.dll</td><td>
{{'[Syncfusion.Themes.MaterialLightBlue.WPF](https://www.nuget.org/packages/Syncfusion.Themes.MaterialLightBlue.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialDarkBlue</td><td>
Syncfusion.Themes.MaterialDarkBlue.Wpf.dll</td><td>
{{'[Syncfusion.Themes.MaterialDarkBlue.WPF](https://www.nuget.org/packages/Syncfusion.Themes.MaterialDarkBlue.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019Colorful</td><td>
Syncfusion.Themes.Office2019Colorful.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019Colorful.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019Colorful.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019Black</td><td>
Syncfusion.Themes.Office2019Black.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019Black.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019Black.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019White</td><td>
Syncfusion.Themes.Office2019White.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019White.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019White.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019DarkGray</td><td>
Syncfusion.Themes.Office2019DarkGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019DarkGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019DarkGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019HighContrast</td><td>
Syncfusion.Themes.Office2019HighContrast.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019HighContrast.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019HighContrast.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019HighContrastWhite</td><td>
Syncfusion.Themes.Office2019HighContrastWhite.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2019HighContrastWhite.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2019HighContrastWhite.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
SystemTheme</td><td>
Syncfusion.Themes.SystemTheme.Wpf.dll</td><td>
{{'[Syncfusion.Themes.SystemTheme.WPF](https://www.nuget.org/packages/Syncfusion.Themes.SystemTheme.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Metro</td><td>
Syncfusion.Themes.Metro.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Metro.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Metro.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Lime</td><td>
Syncfusion.Themes.Lime.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Lime.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Lime.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Saffron</td><td>
Syncfusion.Themes.Saffron.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Saffron.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Saffron.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Blend</td><td>
Syncfusion.Themes.Blend.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Blend.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Blend.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013White</td><td>
Syncfusion.Themes.Office2013White.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013White.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013White.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013LightGray</td><td>
Syncfusion.Themes.Office2013LightGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013LightGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013LightGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013DarkGray</td><td>
Syncfusion.Themes.Office2013DarkGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013DarkGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013DarkGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
VisualStudio2013</td><td>
Syncfusion.Themes.VisualStudio2013.Wpf.dll</td><td>
{{'[Syncfusion.Themes.VisualStudio2013.WPF](https://www.nuget.org/packages/Syncfusion.Themes.VisualStudio2013.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Black</td><td>
Syncfusion.Themes.Office2010Black.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Black.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Black.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Blue</td><td>
Syncfusion.Themes.Office2010Blue.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Blue.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Blue.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Silver</td><td>
Syncfusion.Themes.Office2010Silver.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Silver.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Silver.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office365</td><td>
Syncfusion.Themes.Office365.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office365.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office365.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016Colorful</td><td>
Syncfusion.Themes.Office2016Colorful.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016Colorful.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016Colorful.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016White</td><td>
Syncfusion.Themes.Office2016White.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016White.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016White.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016DarkGray</td><td>
Syncfusion.Themes.Office2016DarkGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016DarkGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016DarkGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
VisualStudio2015</td><td>
Syncfusion.Themes.VisualStudio2015.Wpf.dll</td><td>
{{'[Syncfusion.Themes.VisualStudio2015.WPF](https://www.nuget.org/packages/Syncfusion.Themes.VisualStudio2015.WPF/)'| markdownify }}
</td></tr>
</table>

The following table lists the available themes supported in theme studio and alternative themes suggestions to be used in the application. 

<table>
<tr>
<th>
Styles</th><th>
Supported in ThemeStudio</th><th>
Alternative theme suggestion to use</th></tr>
<tr>
<td>
FluentLight</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
FluentDark</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
MaterialLight</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
MaterialDark</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
MaterialLightBlue</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
MaterialDarkBlue</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019Colorful</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019Black</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019White</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019DarkGray</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019HighContrast</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Office2019HighContrastWhite</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
SystemTheme</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Metro</td><td>
-</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Lime</td><td>
-</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Saffron</td><td>
-</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Blend</td><td>
-</td><td>
FluentDark, MaterialDark, Office2019Black</td></tr>
<tr>
<td>
Office2013White</td><td>
-</td><td>
Office2019White</td></tr>
<tr>
<td>
Office2013LightGray</td><td>
-</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2013DarkGray</td><td>
-</td><td>
Office2019DarkGray</td></tr>
<tr>
<td>
VisualStudio2013</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Office2010Black</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Office2010Blue</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Office2010Silver</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Office365</td><td>
-</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2016Colorful</td><td>
-</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2016White</td><td>
-</td><td>
Office2019White</td></tr>
<tr>
<td>
Office2016DarkGray</td><td>
-</td><td>
Office2019DarkGray</td></tr>
<tr>
<td>
VisualStudio2015</td><td>
-</td><td>
-</td></tr>
</table>

## Apply a theme to a control

### Add SkinManager reference

There are several ways for including the Syncfusion [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) reference in the Visual Studio WPF project. The following steps will help you to add by `XAML` Code:

1) Add a reference to the `Syncfusion.SfSkinManager.WPF` assembly or [Syncfusion.SfSkinManager.WPF nuget package](https://www.nuget.org/packages/Syncfusion.SfSkinManager.WPF/) to the project.
2) Import Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or the assembly namespace `Syncfusion.SfSkinManager` into a XAML page.

![Add SfSkinManager Reference](Skin-Manager_images/WPF-SkinManager-Reference.png)

{% tabs %}

{% highlight XAML %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" />

{% endhighlight %}

{% endtabs %}

### Add a theme assembly reference

The [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) supports to apply themes listed in [themes list](https://help.syncfusion.com/wpf/themes/skin-manager#themes-list). To use a theme in the application, add Reference to the corresponding theme assembly. For example, to apply `MaterialDark` theme, attach `Syncfusion.Themes.MaterialDark.Wpf` assembly or [NuGet](https://www.nuget.org/packages/Syncfusion.Themes.MaterialDark.WPF/) reference to the project. While applying a theme to a Window, SkinManager inherits the same theme to all the elements inside the Window.

![Add theme assembly reference](Skin-Manager_images/Add-MaterialDark-Theme-Assembly-Reference.png)


### Set theme

Themes will be applied to both Syncfusion and Framework controls by using [Theme](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html#Syncfusion_SfSkinManager_SfSkinManager_ThemeProperty) attached property of the [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html). The theme assemblies have resource dictionaries with styles of controls. Thus, when the `Theme` property is set, the skin manager merges the theme resource dictionaries of an element to which the theme is applied and its descendants into the resource dictionary of the element to which the theme is applied or `Application.Current.Resource`.

N> While applying the theme to a Window or any element, `SkinManager` inherits the same theme to all its descendants.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="DataGrid_Themes.MainWindow"
                             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                             xmlns:local="clr-namespace:DataGrid_Themes"
                             xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
							 xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
                             Icon="App.ico"
                             Title="Getting Started"
                             WindowStartupLocation="CenterScreen"
                             syncfusionskin:SfSkinManager.Theme="{syncfusionskin:SkinManagerExtension ThemeName=MaterialDark}">

    <Grid DataContext="{StaticResource viewmodel}">
        <syncfusion:SfDataGrid Name="sfgrid" Margin="5"
                                       AutoGenerateColumns="False"
                                       AllowDraggingColumns="True"
                                       AllowEditing="True"
                                       LiveDataUpdateMode="AllowDataShaping"
                                       AllowFiltering="True"
                                       HeaderRowHeight="26"
                                       SelectionMode="Extended"
                                       ColumnSizer="Auto"
                                       ItemsSource="{Binding EmployeeDetails}">
        </syncfusion:SfDataGrid>
    </Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetTheme(this, new Theme("MaterialDark"));

{% endhighlight %}

{% endtabs %}

![Applied skinmanager theme for WPF ChromelessWindow and SfDataGrid control](Skin-Manager_images/Applied-SkinManager-Theme-WPF-ChromelessWindow-DataGrid.jpg)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/wpf-themes-demo-using-skinmanager).

## Apply a theme globally in the application

By default, [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) merges the required resource files from the theme assembly to the element to which the theme is applied. To apply a theme globally in an application, set the `ApplyStylesOnApplication` property to `True`. It merges all the theme resource files to `Application.Current.Resources`.

N> The `SfSkinManager.ApplyStylesOnApplication` static property should be set before `InitializeComponent` of the window or during application start up, when applying for multiple windows. 

{% tabs %}

{% highlight C# %}

SfSkinManager.ApplyStylesOnApplication = true;

{% endhighlight %}

{% endtabs %}

## Customize theme colors and fonts in the application

To customize the theme colors and fonts in the application, call [RegisterThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html#Syncfusion_SfSkinManager_SfSkinManager_RegisterThemeSettings_System_String_Syncfusion_SfSkinManager_IThemeSetting_) method and pass the theme name and respective theme setting instance as parameters.

Each theme supported by the theme studio has its own theme settings class, which begins with the prefix of the themes' name. For example, if the theme name is `MaterialDark`, then there will be theme settings class called `MaterialDarkThemeSettings`. 

N> Need to register theme settings before setting respective theme for window or control.

Please find the complete list of theme names, respective theme settings class, and supported palette.

<table>
<tr>
<th>
Styles/Theme name</th><th>
Respective theme settings class to customize</th>
<th>Supported palette</th>
</tr>
<tr>
<td>
FluentLight</td><td>
{{'[FluentLightThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.FluentLight.WPF.FluentLightThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[FluentPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.FluentLight.WPF.FluentPalette.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
FluentDark</td><td>
{{'[FluentDarkThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.FluentDark.WPF.FluentDarkThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[FluentPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.FluentDark.WPF.FluentPalette.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
MaterialLight</td><td>
{{'[MaterialLightThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialLight.WPF.MaterialLightThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[MaterialPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialLight.WPF.MaterialPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialDark</td><td>
{{'[MaterialDarkThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialDark.WPF.MaterialDarkThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[MaterialPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialDark.WPF.MaterialPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialLightBlue</td><td>
{{'[MaterialLightBlueThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialLightBlue.WPF.MaterialLightBlueThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[MaterialPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialLightBlue.WPF.MaterialPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
MaterialDarkBlue</td><td>
{{'[MaterialDarkBlueThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialDarkBlue.WPF.MaterialDarkBlueThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[MaterialPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.MaterialDarkBlue.WPF.MaterialPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019Colorful</td><td>
{{'[Office2019ColorfulThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019Colorful.WPF.Office2019ColorfulThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[Office2019Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019Colorful.WPF.Office2019Palette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019Black</td><td>
{{'[Office2019BlackThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019Black.WPF.Office2019BlackThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[Office2019Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019Black.WPF.Office2019Palette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019White</td><td>
{{'[Office2019WhiteThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019White.WPF.Office2019WhiteThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[Office2019Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019White.WPF.Office2019Palette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019DarkGray</td><td>
{{'[Office2019DarkGrayThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019DarkGray.WPF.Office2019DarkGrayThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[Office2019Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019DarkGray.WPF.Office2019Palette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019HighContrast</td><td>
{{'[Office2019HighContrastThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019HighContrast.WPF.Office2019HighContrastThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[HighContrastPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019HighContrast.WPF.HighContrastPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
Office2019HighContrastWhite</td><td>
{{'[Office2019HighContrastWhiteThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019HighContrastWhite.WPF.Office2019HighContrastWhiteThemeSettings.html)'| markdownify }}
</td>
<td>
{{'[HighContrastPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.Office2019HighContrastWhite.WPF.HighContrastPalette.html)'| markdownify }}
</td></tr>
<tr>
<td>
SystemTheme</td><td>
{{'[SystemThemeThemeSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.Themes.SystemTheme.WPF.SystemThemeThemeSettings.html)'| markdownify }}
</td>
<td>-</td>
</tr>
</table>

Customize theme colors and fonts in the application

{% tabs %}

{% highlight C# %}

FluentDarkThemeSettings themeSettings = new FluentDarkThemeSettings();
themeSettings.PrimaryBackground = new SolidColorBrush(Colors.Red);
themeSettings.PrimaryForeground = new SolidColorBrush(Colors.AntiqueWhite); 
themeSettings.BodyFontSize = 15;
themeSettings.HeaderFontSize = 18;
themeSettings.SubHeaderFontSize = 17;
themeSettings.TitleFontSize = 17;
themeSettings.SubTitleFontSize = 16;
themeSettings.BodyAltFontSize = 15;
themeSettings.FontFamily = new FontFamily("Callibri");
SfSkinManager.RegisterThemeSettings("FluentDark", themeSettings);

{% endhighlight %}

{% endtabs %}

![Applied custom theme for WPF ChromelessWindow and SfDataGrid control](Skin-Manager_images/Custom-Theme-WPF-ChromelessWindow-DataGrid.png)

Customize theme colors using the predefined palette

{% tabs %}

{% highlight C# %}

FluentDarkThemeSettings themeSettings = new FluentDarkThemeSettings();
themeSettings.Palette = FluentPalette.PinkRed;
SfSkinManager.RegisterThemeSettings("FluentDark", themeSettings);

{% endhighlight %}

{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/customize-themes-using-theme-settings).

## Apply themes to the specific controls 

To apply themes for specific controls in application and exclude some of the controls in window visual tree, provide control names list parameter in constructor of [Theme](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html) class.

This controls list option enables to merge the specific controls theme resource dictionary xaml files to window resources or application resources immediately instead of traversing the window visual tree and applying the theme for those controls in visual tree only.

N> For framework controls, theme will be applied by default on setting the  `Theme` property and cannot be skipped by using above option.

For example, we have skipped applying style for `ComboBoxAdv` in below snippet by providing control names `ButtonAdv` and `ChromelessWindow` only in control names list parameter of `Theme` class.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="SkinManagerApplication.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SkinManagerApplication"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="350" Width="500">
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
        <syncfusion:ButtonAdv Label="Syncfusion Button" SmallIcon="{x:Null}"  Margin="0,0,0,0" Width="150" Height="24"/>
        <syncfusion:ComboBoxAdv Width="150" Height="24" Margin="0,20,0,0" SelectedIndex="0">
            <syncfusion:ComboBoxItemAdv Content="Combo 1"/>
            <syncfusion:ComboBoxItemAdv Content="Combo 2"/>
        </syncfusion:ComboBoxAdv>
    </StackPanel>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

public partial class MainWindow : ChromelessWindow
{
    public MainWindow()
    {
        SfSkinManager.SetTheme(this, new Theme("MaterialDark", new string[] { "ButtonAdv", "ChromelessWindow" }));
        InitializeComponent();
    }
}

{% endhighlight %}

{% endtabs %}

![Applied theme specific for WPF ChromelessWindow and ButtonAdv control](Skin-Manager_images/Theme-WPF-ChromelessWindow-ButtonAdv.png)

## Apply themes to the controls derived from Syncfusion controls

To apply themes to the derived control using `SfSkinManager`, call [SetResourceReference](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.setresourcereference) method and, pass the `StyleProperty` and derived control type as parameters. 

{% tabs %}

{% highlight XAML %}

 <local:SfDataGridExt x:Name="grid"
                             AllowGrouping="True"
                             AutoGenerateColumns="False"
                             ItemsSource="{Binding EmployeeDetails}"
                             ShowGroupDropArea="True">
            <local:SfDataGridExt.Resources>
                <ResourceDictionary>
                    <ResourceDictionary.MergedDictionaries>
                        <ResourceDictionary Source="/Syncfusion.SfGrid.WPF;component/Styles/Styles.xaml" />
                    </ResourceDictionary.MergedDictionaries>
                </ResourceDictionary>
            </local:SfDataGridExt.Resources>
            <local:SfDataGridExt.Columns>
                <syncfusion:GridNumericColumn MappingName="EmployeeAge" />
                <syncfusion:GridTextColumn MappingName="EmployeeName" />
                <syncfusion:GridTextColumn MappingName="EmployeeGender" />
                <syncfusion:GridTextColumn AllowEditing="True" MappingName="Country" />
                <syncfusion:GridNumericColumn MappingName="EmployeeSalary" />
            </local:SfDataGridExt.Columns>
</local:SfDataGridExt>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 public class SfDataGridExt : SfDataGrid
    {
        public SfDataGridExt()
        {
            SetResourceReference(StyleProperty, typeof(SfDataGrid));
        }
    }

{% endhighlight %}

{% endtabs %}

## Clearing SkinManager instance in an application

The `SfSkinManager` will hold some instances to use it further when applying the theme. However, this can be cleared using the function named `Dispose(object)`, which must be called when the theme applied by `SfSkinManager` is to be cleared, as shown in the following code. **Object** refers to the element whose instance needs to be cleared.


{% tabs %}

{% highlight C# %}

private void Window_Closed(object sender, EventArgs e) 
{ 
   SfSkinManager.Dispose(this); 
} 

{% endhighlight %}

{% endtabs %}

## How to

### Apply custom theme in the application

To apply a custom theme in the application, export the custom theme project from ThemeStudio using [this reference](https://help.syncfusion.com/wpf/themes/theme-studio#exporting-theme-project).

For demonstration purposes, the exported theme name has been used as `MaterialDarkYellow` and assembly name as `Syncfusion.Themes.MaterialDarkYellow.WPF`.

Now, for the control used in the application, set the `SfSkinManager` attached property `Theme` to `MaterialDarkYellow;MaterialDark`. Since, custom theme name should be updated in the following format: `CustomTheme1;BaseThemeName`, where `CustomTheme1` denotes the custom theme name and `BaseThemeName` denotes the theme name from which it is derived. For example, `MaterialDarkYellow;MaterialDark`.

{% tabs %}

{% highlight C# %}

SfSkinManager.SetTheme(this, new Theme("MaterialDarkYellow;MaterialDark"));

{% endhighlight %}

{% endtabs %}

### Override syncfusion themes in the application

All Syncfusion themes are [supported in theme studio](https://help.syncfusion.com/wpf/themes/skin-manager#themes-list). A common naming convention can be used to override control styles. A unique key is given to every style so that the styles can be overridden using the `BasedOn` property.

The naming convention of a control style will be like `Syncfusion-ControlName-Style`. For example, `MaterialDarkButtonAdvStyle`.

The following steps explain how to override the Syncfusion themes:

**Step1:**

Add respective resource dictionary from the themes assembly to the application.

The resource dictionary will be in this format: `/Syncfusion.Themes.<ThemeName>.WPF;component/<ControlName>/<ControlName>.xaml`, where `ThemeName` denotes the theme name for which overridden style is going to be applied and `ControlName` denotes the control name. For example, `/Syncfusion.Themes.MaterialDark.WPF;component/ButtonAdv/ButtonAdv.xaml`.

{% tabs %}

{% highlight XAML %}

<ResourceDictionary>
<ResourceDictionary.MergedDictionaries>
<ResourceDictionary Source="/Syncfusion.Themes.MaterialDark.WPF;component/ButtonAdv/ButtonAdv.xaml"/>
</ResourceDictionary.MergedDictionaries>
</ResourceDictionary>

{% endhighlight %}

{% endtabs %}

**Step2:**

Define the new style using the `BasedOn` property.

The following code sample overrides the Syncfusion style for the `ButtonAdv` Control.

{% tabs %}

{% highlight XAML %}

<Grid>
        <Grid.Resources>
            <Style x:Key="CustomButtonAdvStyle" TargetType="syncfusion:ButtonAdv" BasedOn="{StaticResource SyncfusionButtonAdvStyle}" >
                <Setter Property="Foreground" Value="Red"/>
            </Style>
        </Grid.Resources>
        <syncfusion:ButtonAdv Name="buttonAdv" Content="Testing" Width="150" Height="30" SmallIcon="{x:Null}" Style="{StaticResource CustomButtonAdvStyle}"></syncfusion:ButtonAdv>   
</Grid>

{% endhighlight %}

{% endtabs %}

![Overridden foreground style applied for WPF ButtonAdv control](Skin-Manager_images/WPF-ButtonAdv-Overridden-foreground-style.png)




## Switching Syncfusion theme at runtime
Whenever we need to switch themes we have to call setTheme() separately.

### Step 1: In the Xaml file, Added two RadioButton for light and dark themes. 

{% tabs %}

{% highlight XAML %}

  

        <RadioButton Content="Light"
                     Grid.Row="0"
                     Grid.Column="0"
                     Margin="20"
                     GroupName="themeSwitch"
                     Click="Switch_Theme"
                     HorizontalAlignment="Center"
                     VerticalAlignment="Center" />
        <RadioButton Content="Dark"
                     Margin="20"
                     Grid.Row="0"
                     Grid.Column="1"
                     Click="Switch_Theme"
                     GroupName="themeSwitch"
                     HorizontalAlignment="Center"
                     VerticalAlignment="Center" />
       
        <TextBlock Text="Framework Controls"
                   Grid.Row="1"
                   Grid.Column="0"
                   Margin="20"
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center" />
        <TextBlock Text="Syncfusion Controls"
                   Margin="20"
                   Grid.Row="1"
                   Grid.Column="1"
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center" />

        

        <Button Content="MS Button"
                Grid.Row="2"
                Grid.Column="0"
                Margin="20"
                Height="30"
                Width="100"
                HorizontalAlignment="Center"
                VerticalAlignment="Center" />
        <syncfusion:ButtonAdv Label="SF Button"
                              Grid.Row="2"
                              Grid.Column="1"
                              Margin="20"
                              Height="30"
                              Width="100"
                              HorizontalAlignment="Center"
                              VerticalAlignment="Center" />

        

        <ComboBox  Grid.Row="3"
                   Grid.Column="0"
                   Margin="20"
                   Height="30"
                   Width="100"
                   SelectedIndex="0"
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center">
            <ComboBoxItem Content="Orange" />
            <ComboBoxItem Content="Orange" />
            <ComboBoxItem Content="Orange" />
            <ComboBoxItem Content="Orange" />
        </ComboBox>
        <syncfusion:ComboBoxAdv Grid.Row="3"
                                Grid.Column="1"
                                Margin="20"
                                Height="30"
                                Width="100"
                                SelectedIndex="0"
                                HorizontalAlignment="Center"
                                VerticalAlignment="Center">
            <syncfusion:ComboBoxItemAdv Content="Orange" />
            <syncfusion:ComboBoxItemAdv Content="Orange" />
            <syncfusion:ComboBoxItemAdv Content="Orange" />
            <syncfusion:ComboBoxItemAdv Content="Orange" />
        </syncfusion:ComboBoxAdv>

    

       

{% endhighlight %}

{% endtabs %}

Step 2: In the code behind the file, Added SetTheme() for both light and dark themes based on condition.

{% tabs %}

{% highlight C# %}


    private void Switch_Theme(object sender, RoutedEventArgs e)
        {
            if ((sender as RadioButton).Content.ToString() == "Light")
            SfSkinManager.SetTheme(this, new Theme("MaterialLight"));
            else
            SfSkinManager.SetTheme(this, new Theme("MaterialDark"));
        }

{% endhighlight %}

{% endtabs %}

### Output ScreenShots

Light Theme

![Apply syncfusion theme at runtime - Light theme](Skin-Manager_images/Switch-theme-Light-Theme.jpg)

Dark Theme

![Apply syncfusion theme at runtime - Dark theme](Skin-Manager_images/Swith-theme-Dark-theme.jpg)

## Overriding style while Switching Syncfusion theme at runtime

**Step 1**: Add the above steps in Switching Syncfusion theme at runtime.

**Step 2**: Add resource dictionaries in merge dictionary.

{% tabs %}

{% highlight XAML %}
    
     <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="/Syncfusion.Themes.MaterialLight.WPF;component/ButtonAdv/ButtonAdv.xaml" />
                <ResourceDictionary Source="/Syncfusion.Themes.MaterialDark.WPF;component/MSControl/Button.xaml" />
            </ResourceDictionary.MergedDictionaries>
            <Style BasedOn="{StaticResource WPFButtonStyle}"
                   TargetType="{x:Type Button}">
                <Setter Property="Background"
                        Value="Magenta" />
            </Style>
            <Style BasedOn="{StaticResource SyncfusionButtonAdvStyle}"
                   TargetType="{x:Type syncfusion:ButtonAdv}">
                <Setter Property="Background"
                        Value="Magenta" />
            </Style>
        </ResourceDictionary>
    </Window.Resources>
  

{% endhighlight %}

{% endtabs %}

### Output ScreenShots

Light Theme

![Apply syncfusion theme at runtime - Light theme](Skin-Manager_images/override-theme-light-theme.png)

Dark Theme

![Apply syncfusion theme at runtime - Dark theme](Skin-Manager_images/override-theme-dark-theme.png)



## Change visual style at runtime

Themes for application can be changed at runtime by changing `VisualStyle` property. Make sure that the new theme assembly is attached as reference in the application when applying theme.

![Added references for WPF SkinManager and visual style](Skin-Manager_images/WPF-SkinManager-References.jpg)

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="DataGrid_Themes.MainWindow"
                             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                             xmlns:local="clr-namespace:DataGrid_Themes"
                             xmlns:system="clr-namespace:System;assembly=mscorlib"
                             xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
							 xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
							 syncfusionskin:SfSkinManager.VisualStyle="{Binding ElementName=comboVisualStyle, Path=SelectedValue, Mode=OneWay, UpdateSourceTrigger=PropertyChanged}">

    <syncfusion:ChromelessWindow.Resources>
        <ObjectDataProvider
            x:Key="Themes"
            MethodName="GetValues"
            ObjectType="{x:Type system:Enum}">
            <ObjectDataProvider.MethodParameters>
                <x:Type TypeName="syncfusionskin:VisualStyles" />
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>
    </syncfusion:ChromelessWindow.Resources>

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="40"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <ComboBox
                x:Name="comboVisualStyle"
                Grid.Row="0"
                Width="250"
                Margin="5"
                ItemsSource="{Binding Source={StaticResource Themes}}"
                SelectedIndex="18" />
                
        <Grid Grid.Row="1" DataContext="{StaticResource viewmodel}">
            <syncfusion:SfDataGrid Name="sfgrid" Margin="5"
                                       AutoGenerateColumns="False"
                                       AllowDraggingColumns="True"
                                       AllowEditing="True"
                                       LiveDataUpdateMode="AllowDataShaping"
                                       AllowFiltering="True"
                                       HeaderRowHeight="26"
                                       SelectionMode="Extended"
                                       ColumnSizer="Auto"
                                       ItemsSource="{Binding EmployeeDetails}">
             
            </syncfusion:SfDataGrid>
        </Grid>
    </Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/change-themes-at-runtime-using-skinmanager).
