---
layout: post
title: Customization in WPF ColorPicker | Syncfusion®
description: Customize the Syncfusion WPF ColorPicker control with layout properties such as FlowDirection, ColorPalette visibility, and display mode.
platform: wpf
control: ColorPicker
documentation: ug
---



# Customization in WPF ColorPicker

[WPF ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) has a built-in color palette to select a solid color easily. This can be enabled using the [IsColorPaletteVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_IsColorPaletteVisible) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorEdit x:Name="colorEdit" IsColorPaletteVisible="True"/>

{% endhighlight %}

{% highlight C# %}

colorEdit.IsColorPaletteVisible = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker with color palette enabled](ScRGB-Color_images/ColorPicker_ColorPalleteEnabled.png)

## Gradient brush display mode

The brush representation of `WPF ColorPicker` can be customized using the [GradientBrushDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_GradientBrushDisplayMode) property. The default value of `GradientBrushDisplayMode` is `Default`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" GradientBrushDisplayMode="Extended"/>

{% endhighlight %}

{% highlight C# %}

colorPicker.GradientBrushDisplayMode = Syncfusion.Windows.Tools.GradientBrushDisplayMode.Extended;

{% endhighlight %}
{% endtabs %}

![ColorPicker with Extended gradient display mode](New-User-Interface-Support_images/GradientDisplayMode_Default.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" GradientBrushDisplayMode="Default"/>

{% endhighlight %}

{% highlight C# %}

colorPicker.GradientBrushDisplayMode = Syncfusion.Windows.Tools.GradientBrushDisplayMode.Default;

{% endhighlight %}
{% endtabs %}

![ColorPicker with Default gradient display mode](New-User-Interface-Support_images/GradientDisplayMode_Extended.png)

## Inverted Color

[ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html) provides a way to get the inverted color of the selected color using the [InvertColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_InvertColor) property. This is useful for generating a contrast color for the current selection.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorEdit x:Name="colorEdit"/>
<TextBlock Name="textBlock" Text="a" TextAlignment="Center" FontSize="70"
           Background="{Binding ElementName=colorEdit, Path=Brush, UpdateSourceTrigger=PropertyChanged}"
           HorizontalAlignment="Center" VerticalAlignment="Center" Height="110" Width="110">
    <TextBlock.Foreground>
        <SolidColorBrush Color="{Binding ElementName=colorEdit, Path=InvertColor, UpdateSourceTrigger=PropertyChanged}"/>
    </TextBlock.Foreground>
</TextBlock>

{% endhighlight %}

{% highlight C# %}

textBlock.Background = colorEdit.Brush;
textBlock.Foreground = new SolidColorBrush(colorEdit.InvertColor);

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker InvertColor](ScRGB-Color_images/ColorPicker_InvertColor.png)

## ScRGB-Color

ScRGB is a wide-gamut color space that allows color values outside the sRGB range (such as those beyond 1.0 or below 0.0). To enable ScRGB color editing in `ColorEdit`, set the [IsScRGBColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_IsScRGBColor) property to `true`. The default value of `IsScRGBColor` is `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorEdit x:Name="colorEdit" IsScRGBColor="True"/>

{% endhighlight %}

{% highlight C# %}

colorEdit.IsScRGBColor = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker with ScRGB color editing](ScRGB-Color_images/ColorPicker_IsScRGBColor.png)

N> `IsScRGBColor` is a `ColorEdit`-only property and is not available in the `WPF ColorPicker`.