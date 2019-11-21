---
layout: post
title: Customization | ColorPicker | wpf | Syncfusion
description: This section explains about layout related properties such as FlowDirection, ColorPalette enabled and display mode etc.
platform: wpf
control: ColorPicker
documentation: ug
---

## Setting flow direction

Flow Direction of the ColorPicker and ColorEdit controls is set by using the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.flowdirection?view=netframework-4.8) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker FlowDirection="RightToLeft" Name="colorPicker"/>

{% endhighlight %}

{% highlight C# %}

colorPicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![ColorPicker RightToLeft](Layout-Related-Features_images/ColorPicker_RightToLeft.png)

## Color Palette

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) has build-in color palette to select solid color easily. This can be enabled using [IsColorPaletteVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~IsColorPaletteVisible.html) property.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"   IsColorPaletteVisible="True"/>
{% endhighlight %}

{% highlight C# %}

 IsColorPaletteVisible.IsColorPaletteVisible = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsColorPaletteVisible](ScRGB-Color_images/ColorPicker_ColorPalleteEnabled.png)

## Alpha Visibility

Alpha/Opacity parameter of the color can be altered using delicate slider which handle alpha visibility. This can be disabled by [IsAlphaVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~IsAlphaVisible.html) property.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"   IsAlphaVisible="False"/>
{% endhighlight %}

{% highlight C# %}

 ColorEdit2.IsAlphaVisible = false;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsAlphaVisible](ScRGB-Color_images/ColorPicker_IsAlphaVisible.png)

## Gradient brush display mode

Brush representation of ColorPicker can be customized using [GradientBrushDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~GradientBrushDisplayMode.html) property.

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

[ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html) has option to get the contrast/inverted color of the selected color using [InvertColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~InvertColor.html) property.

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

ScRGB color can be obtained by setting [IsScRGBColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~IsScRGBColor.html) property in ColorEdit.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorEdit  x:Name="ColorEdit2"   IsScRGBColor="True"/>
{% endhighlight %}

{% highlight C# %}

 ColorEdit2.IsScRGBColor = true;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsAlphaVisible](ScRGB-Color_images/ColorPicker_IsScRGBColor.png)