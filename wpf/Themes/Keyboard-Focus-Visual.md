---
layout: post
title: Getting Started with Keyboard Focus Visual | Syncfusion WPF Controls
description: This article explains how to apply high visibility keyboard visual feedback followed in fluent design for WPF controls and Syncfusion controls.
platform: wpf
control: Themes
documentation: ug
---

# Getting Started with Keyboard Focus Visual for WPF Controls

The [WPF Skin Manager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) allows you to apply various keyboard focus visual styles for both Syncfusion and Framework controls using the [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html#Syncfusion_SfSkinManager_Theme_FocusVisualKind) property. 

The [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.FocusVisualKind.html) enum contains the following values:

* `Default` - The default keyboard focus visual style will be applied.
* `HighVisibility` - High visibility keyboard visual feedback is an effect that shows a border for focusable elements when the user moves the keyboard focus to that element. 

N> The `HighVisibility` keyboard focus visual is enabled by default in the Fluent theme.

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

![High Visibility Keyboard Visual Effect in WPF](Skin-Manager_images/WPF-SkinManager-FocusVisualKind.gif)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/change-focusvisualkind-using-skinmanager).


