---
layout: post
title: Steps to explore various settings in Fluent theme for Syncfusion Essential WPF controls
description: Learn here about how to explore various settings in Fluent theme for Syncfusion Essential WPF controls and framework controls using SfSkinManager
platform: wpf
control: Themes
documentation: ug
---
# Fluent Theme

The [FluentTheme](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html) provides an elegant UI with reveal animation for interactive elements and acrylic effect for windows.

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
                             syncfusionskin:SfSkinManager.Theme="{syncfusionskin:SkinManagerExtension ThemeName=FluentDark}">

</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetTheme(this, new FluentTheme("FluentDark"));

{% endhighlight %}

{% endtabs %}

## Reveal animation

The reveal animation for WPF controls can be enabled/disabled using [HoverEffectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html#Syncfusion_SfSkinManager_FluentTheme_HoverEffectMode) and [PressedEffectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html#Syncfusion_SfSkinManager_FluentTheme_PressedEffectMode) properties. 

N> The reveal animation is enabled by default in fluent theme. 

### Hover reveal effect

The reveal animation while hovering the controls can be enabled/disabled using [HoverEffectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html#Syncfusion_SfSkinManager_FluentTheme_HoverEffectMode) property.

The [HoverEffect](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.HoverEffect.html) enum has following values

* `Background` - The hover reveal animation effect will be applied only for control Background.

* `BackgroundAndBorder` - The hover reveal animation effect will be applied for both control Border and Background.

* `Border` - The hover reveal animation effect will be applied only for control Border.

* `None` - The hover reveal animation effect will be disabled.

N> The default value is `HoverEffect.BackgroundAndBorder`. 

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
                             syncfusionskin:SfSkinManager.Theme="{syncfusionskin:SkinManagerExtension ThemeName=FluentDark, FluentHoverEffectMode=Border}">

</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

    SfSkinManager.SetTheme(this, new FluentTheme() { ThemeName = "FluentDark", HoverEffectMode = HoverEffect.Border });

{% endhighlight %}

{% endtabs %}

### Pressed effect

The reveal animation when pressed using mouse/touch on controls can be enabled/disabled using [PressedEffectMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html#Syncfusion_SfSkinManager_FluentTheme_PressedEffectMode) property.

The [PressedEffect](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.PressedEffect.html) enum has following values

* `Glow` - The glow animation effect will be applied when pressed using mouse/touch.
* `Reveal` - The reveal animation effect will be applied when pressed using mouse/touch.
* `None` - The pressed animation effect will be disabled.

N> The default value is `PressedEffect.Reveal`. 

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
                             syncfusionskin:SfSkinManager.Theme="{syncfusionskin:SkinManagerExtension ThemeName=FluentDark, FluentPressedEffectMode=Reveal}">

</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

    SfSkinManager.SetTheme(this, new FluentTheme() { ThemeName = "FluentDark", PressedEffectMode = PressedEffect.Reveal });

{% endhighlight %}

{% endtabs %}

## Acrylic Window Background

The transparent blurred acrylic background can be enabled/disabled for windows using [ShowAcrylicBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FluentTheme.html#Syncfusion_SfSkinManager_FluentTheme_ShowAcrylicBackground) property.

N> The default value is `false`. 

{% tabs %}

{% highlight C# %}

    SfSkinManager.SetTheme(this, new FluentTheme() { ThemeName = "FluentDark", ShowAcrylicBackground = true });

{% endhighlight %}

{% endtabs %}
