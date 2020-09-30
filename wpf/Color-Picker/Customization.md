---
layout: post
title: Customization | ColorPicker | wpf | Syncfusion
description: This section explains about layout related properties such as FlowDirection, ColorPalette enabled and display mode etc.
platform: wpf
control: ColorPicker
documentation: ug
---



## Color Palette

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) has build-in color palette to select solid color easily. This can be enabled using [IsColorPaletteVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_IsColorPaletteVisible) property.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"   IsColorPaletteVisible="True"/>
{% endhighlight %}

{% highlight C# %}

 IsColorPaletteVisible.IsColorPaletteVisible = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsColorPaletteVisible](ScRGB-Color_images/ColorPicker_ColorPalleteEnabled.png)


## Gradient brush display mode

Brush representation of ColorPicker can be customized using [GradientBrushDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_GradientBrushDisplayMode) property.

{% tabs %}
{% highlight xaml %}

<sync:ColorPicker  GradientBrushDisplayMode = "Extended"/>

{% endhighlight %}

{% highlight C# %}

colorPicker1.GradientBrushDisplayMode = Syncfusion.Windows.Tools.GradientBrushDisplayMode.Extended;

{% endhighlight %}
{% endtabs %}

![ColorPicker-HeaderTemplate-WPF](New-User-Interface-Support_images/GradientDisplayMode_Default.png)

{% tabs %}
{% highlight xaml %}

<sync:ColorPicker  GradientBrushDisplayMode = "Default"/>

{% endhighlight %}

{% highlight C# %}

colorPicker1.GradientBrushDisplayMode = Syncfusion.Windows.Tools.GradientBrushDisplayMode.Default;

{% endhighlight %}
{% endtabs %}

![ColorPicker-HeaderTemplate-WPF](New-User-Interface-Support_images/GradientDisplayMode_Extended.png)

## Inverted Color 

[ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html) has option to get the contrast/inverted color of the selected color using [InvertColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_InvertColor) property.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"    />
   <TextBlock  Name="textblock2" Text="a"  TextAlignment="Center"  FontSize="70"  Background="{Binding ElementName=ColorEdit2, Path=Brush,UpdateSourceTrigger=PropertyChanged}" HorizontalAlignment="Center" VerticalAlignment="Center" Height="110" Width="110">
     <TextBlock.Foreground>
       <SolidColorBrush Color="{Binding ElementName=ColorEdit2,Path=InvertColor,UpdateSourceTrigger=PropertyChanged}"/>
     </TextBlock.Foreground>
 </TextBlock>
{% endhighlight %}

{% highlight C# %}

textblock2.Background = ColorEdit2.Brush;

textblock2.Foreground = new SolidColorBrush(ColorEdit3.InvertColor);

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker InvertColor](ScRGB-Color_images/ColorPicker_InvertColor.png)

## ScRGB-Color

ScRGB color can be obtained by setting [IsScRGBColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_IsScRGBColor) property in ColorEdit.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"   IsScRGBColor="True"/>
{% endhighlight %}

{% highlight C# %}

 ColorEdit2.IsScRGBColor = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsAlphaVisible](ScRGB-Color_images/ColorPicker_IsScRGBColor.png)