---
layout: post
title: Keyboard Focus Visual in WPF Skin Manager | Syncfusion®
description: The Skin Manager applies high visibility keyboard focus visual feedback to focusable elements in WPF and Syncfusion® controls.
platform: wpf
control: Themes
documentation: ug
---

# Keyboard Focus Visual in WPF Skin Manager

The [WPF Skin Manager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) allows you to apply various keyboard focus visual styles for both Syncfusion<sup>&reg;</sup> and Framework controls using the [FocusVisualKind](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.Theme.html#Syncfusion_SfSkinManager_Theme_FocusVisualKind) property. 

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


