---
layout: post
title: About WPF SfColorPalette Control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF SfColorPalette control and more details about the control features.
platform: wpf
control: SfColorPalette
documentation: ug
---

# Appearance in WPF ColorPalette (SfColorPalette)

This section explains different UI customization options available in [ColorPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Media.SfColorPalette.html) control.

## Setting the Foreground

You can change the foreground color for `ColorPalette` by setting the `Foreground` property. The default color value of `Foreground` property is `Gray`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfColorPalette Foreground="Red"
                           Name="sfColorPalette"/>

{% endhighlight %}
{% highlight C# %}

SfColorPalette sfColorPalette = new SfColorPalette();
sfColorPalette.Foreground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![ColorPalette with Red foreground](Appearance_images/Appearance_Foreground.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/Appearance) in GitHub

## Setting the Background

You can change the background color for `ColorPalette` by setting the `Background` property. The default color value of `Background` property is `Snow`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfColorPalette Background="Red"
                           Name="sfColorPalette"/>

{% endhighlight %}
{% highlight C# %}

SfColorPalette sfColorPalette = new SfColorPalette();
sfColorPalette.Background = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![ColorPalette with Red background](Appearance_images/Appearance_Background.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/Appearance) in GitHub

## Change flow direction

You can change the flow direction of the `ColorPalette` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The Default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfColorPalette FlowDirection="RightToLeft"
                           Name="sfColorPalette"/>

{% endhighlight %}
{% highlight C# %}

SfColorPalette sfColorPalette = new SfColorPalette();
sfColorPalette.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![ColorPalette with RightToLeft flow direction](Appearance_images/FlowDirection_RightToLeft.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/Appearance) in GitHub

## Theme

You can customize the appearance of the `ColorPalette` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinmanager.SfSkinmanager.html#Syncfusion_SfSkinManager_SfSkinManager_SetVisualStyle_System_Windows_DependencyObject_Syncfusion_SfSkinManager_VisualStyles_) method. The following are the various built-in visual styles for `ColorPalette` control.

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
* Office2019Black
* Office2019Colorful
* Office365
* Saffron
* VisualStudio2013
* VisualStudio2015

{% tabs %}
{% highlight xaml %}

<Window
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF">
    <Grid>
        <syncfusion:SfColorPalette syncfusionskin:SfSkinManager.VisualStyle="Blend" 
                                   Name="sfColorPalette" />
    </Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

SfColorPalette sfColorPalette = new SfColorPalette();
SfSkinManager.SetVisualStyle(sfColorPalette, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![ColorPalette with Blend visual style](Appearance_images/theme.png)

Here, the `Blend` style is applied to the `ColorPalette`.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-sfcolorpalette-examples/tree/master/Samples/Themes)
