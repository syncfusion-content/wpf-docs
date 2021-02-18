---
layout: post
title: Appearance of the WPF SfRadialSlider control | Syncfusion
description: Learn about styling, theme support in Syncfusion WPF SfRadialSlider control and more details about the control features.
platform: wpf
control: SfRadialSlider
documentation: ug
---

# Appearance in WPF SfRadialSlider

This section explains different styling, theming options available in [SfRadialSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfRadialSlider.html) control.

## Setting the foreground

You can change the foreground color of the `SfRadialSlider` by using the `Foreground` property. The default value of `Foreground` property is `Black`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Foreground="Red" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Foreground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with red foreground](Appearance_images/Foreground.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Setting the background

You can change the background color of the `SfRadialSlider` by using the `Background` property. The default value of `Background` property is `White`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Background="Yellow"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Background = Brushes.Yellow;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with yellow background](Appearance_images/Background.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change flow direction

You can change the flow direction of the `SfRadialSlider` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider FlowDirection="RightToLeft"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with right to left flow direction](Appearance_images/rtl.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Theme

SfRadialSlider supports various built-in themes. Refer to the below links to apply themes for the SfRadialSlider,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfRadialSlider](GettingStarted_images/Theme.png)