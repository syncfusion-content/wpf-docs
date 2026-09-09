---
layout: post
title: Appearance in WPF ColorPickerPalette | Syncfusion®
description: Customize the look and feel of the Syncfusion WPF ColorPickerPalette control using built-in themes, custom templates, and styling options.
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# Appearance in WPF Color Picker Palette

This section explains different UI customization, styling, theming options available in [WPF Color Picker Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ColorPickerPalette.html) control.

## Change flow direction

You can change the flow direction of the `WPF Color Picker Palette` layout to right-to-left by setting the `FlowDirection` property to `RightToLeft`. The default value of `FlowDirection` is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette FlowDirection="RightToLeft"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.FlowDirection = FlowDirection.RightToLeft;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with Right To Left flow direction](Appearance_images/rtl.png)

## Theme

The WPF Color Picker Palette supports various built-in themes. Refer to the links below to apply themes,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

 ![Setting theme to WPF ColorPickerPalette](Getting-Started_images/wpf-color-picker-palette-with-standard-theme.png)
