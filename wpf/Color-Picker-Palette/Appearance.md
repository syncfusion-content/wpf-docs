---
layout: post
title: Appearance of the WPF ColorPickerPalette control | Syncfusion
description: Learn about UI customization, styling, theme support in Syncfusion WPF ColorPickerPalette control and more details about the control features.
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# Appearance in WPF ColorPickerPalette

This section explains different UI customization, styling, theming options available in [ColorPickerPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette.html) control.

## Change flow direction

We can change the flow direction of the `ColorPickerPalette` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The Default value of `FlowDirection` property is `LeftToRight`.

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
colorPickerPalette.Height = 60;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with Right To Left flow direction](Appearance_images/rtl.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/Apperance) to download the sample that showcases the styling and RTL supports.

## Theme

We can customize the appearance of the `ColorPickerPalette` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinmanager.Wpf~Syncfusion.SfSkinmanager.SfSkinmanager~SetVisualStyle.html) method. The following are the various built-in visual styles for `ColorPickerPalette` control.

* Blend
* Lime
* MaterialDark
* MaterialDarkBlue
* MaterialLight
* MaterialLightBlue
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office365
* Saffron
* VisualStudio2013
* VisualStudio2015

{% tabs %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
SfSkinManager.SetVisualStyle(colorPickerPalette, VisualStyles.Blend);
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 60;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with Blend visual style](Appearance_images/blend.png)

Here, the `Blend` style is applied to the `ColorPickerPalette`.

Click [here]() to download the sample that showcases the appearance customization and  different theming supports.


