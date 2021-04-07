---
layout: post
title: Steps to apply various keyboard focus visual styles for Syncfusion Essential WPF controls
description: Learn here about how to apply various keyboard focus visual styles for Syncfusion Essential WPF controls and framework controls using SfSkinManager
platform: wpf
control: Themes
documentation: ug
---
# FocusVisualKind

The [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) helps to apply various keyboard focus visual styles for both syncfusion and framework controls using [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html#Syncfusion_SfSkinManager_Theme_FocusVisualKind) property which will be available only in [13 themes supported from theme studio](https://help.syncfusion.com/wpf/themes/skin-manager#themes-list).

The [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FocusVisualKind.html) enum has below values,

* `Default` - The default keyboard focus visual style will be applied.
* `HighVisibility` - Reveal focus aka High visibility keyboard visual feedback is an effect that shows a border for focusable elements when user moves keyboard focus to that element. 

N> The `HighVisibility` scrollbar mode is enabled by default in fluent theme. 

![WPF SfSkinManager FocusVisualKind](Skin-Manager_images/WPF-SkinManager-FocusVisualKind.gif)

## Change focus visual style

The keyboard focus visual style can be changed using [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html#Syncfusion_SfSkinManager_Theme_FocusVisualKind) property available in [Themes](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html) class. 

{% tabs %}

{% highlight C# %}

public partial class MainWindow : ChromelessWindow
{
    public MainWindow()
    {
        SfSkinManager.SetTheme(this, new Theme() { ThemeName = "MaterialDark", FocusVisualKind = FocusVisualKind.HighVisibility });
        InitializeComponent();            
    }        
}

{% endhighlight %}

{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/change-focusvisualkind-using-skinmanager).