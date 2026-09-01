---
layout: post
title: Appearance in WPF Radial Slider | Syncfusion®
description: Customize the appearance of the WPF Radial Slider using foreground, background, flow direction, and theme settings.
platform: wpf
control: SfRadialSlider
documentation: ug
---

# Appearance in WPF Radial Slider (SfRadialSlider)

This section explains different styling, theming options available in [WPF Radial Slider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfRadialSlider.html) control.

## Setting the foreground

You can change the foreground color of the `WPF Radial Slider` by using the `Foreground` property. The default value of `Foreground` property is `Black`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Foreground="Red" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Foreground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![WPF Radial Slider with red foreground](Appearance_images/Foreground.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Setting the background

You can change the background color of the `WPF Radial Slider` by using the `Background` property. The default value of `Background` property is `White`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Background="Yellow"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Background = Brushes.Yellow;

{% endhighlight %}
{% endtabs %}

![WPF Radial Slider with yellow background](Appearance_images/Background.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change flow direction

You can change the flow direction of the `WPF Radial Slider` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider FlowDirection="RightToLeft"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![WPF Radial Slider with right to left flow direction](Appearance_images/rtl.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Theme

The WPF Radial Slider supports various built-in themes. Refer to the below links to apply themes for the WPF Radial Slider,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Radial Slider](getting-started_images/wpf-radial-slider-theme-setting.png)
