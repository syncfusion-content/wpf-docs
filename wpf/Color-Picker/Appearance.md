---
layout: post
title: Appearance| ColorPicker | wpf | Syncfusion
description: This page includes a brief description of ColorEdit, the ColoPicker Header customization options and themes.
platform: wpf
control: ColorPicker
documentation: ug
---

# Appearance in WPF ColorPicker

This page contains a brief description of the WPF ColoPicker Header customization options, built-in themes, and other related layout resources.

## Header Template

Header of the ColorPicker can be customized using [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~HeaderTemplate.html) property.

{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="CustomHeaderTemplate" DataType="syncfusion:ColorPicker">
  <StackPanel Orientation="Horizontal">
    <Border Name="selectedColorRect"
     HorizontalAlignment="Left" 
     Width="20" Height="20" Margin="2" 
     Background="{Binding Color,RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:ColorPicker}}, Converter={StaticResource ColorToBrush}}"/>
  </StackPanel>
</DataTemplate>

<sync:ColorPicker  HeaderTemplate="{StaticResource CustomHeaderTemplate}"/>

{% endhighlight %}
{% endtabs %}

![ColorPicker-HeaderTemplate-WPF](New-User-Interface-Support_images/CustomHeader_ColorPicker.png)


## Setting flow direction

Right to left layout of the ColorPicker is set by using the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.flowdirection?view=netframework-4.8) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker FlowDirection="RightToLeft" Name="colorPicker"/>

{% endhighlight %}

{% highlight C# %}

colorPicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![ColorPicker RightToLeft](Layout-Related-Features_images/ColorPicker_RightToLeft.png)


## Alpha Visibility

Alpha/Opacity parameter of the color can be altered using delicate slider which handle alpha visibility. This can be disabled by [IsAlphaVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~IsAlphaVisible.html) property.

{% tabs %}
{% highlight xaml %}
 <syncfusion:ColorPicker x:Name="colorPicker" IsAlphaVisible="False"/>
{% endhighlight %}

{% highlight C# %}

 colorPicker.IsAlphaVisible = false;

{% endhighlight %}
{% endtabs %}

![WPF ColorPicker IsAlphaVisible](ScRGB-Color_images/ColorPicker_IsAlphaVisible.png)

## Setting VisualStyle for ColorPicker control

WPF ColorPicker provides built-in themes which can be applied using SkinStorage and SfSkinManager. Also provides support to create custom theme using theme studio.

You can enhance the appearance of the [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) by using the [VisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.SkinStorage~VisualStyleProperty.html) property. VisualStyle is an attached property that gets or sets the value for the visual style. Use the following code to set the visual style for the ColorPicker control.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker  syncfusion:SkinStorage.VisualStyle="Office2013" Name="colorPicker"/>

{% endhighlight %}

{% highlight C# %}

 SkinStorage.SetVisualStyle(colorPicker, "Office2013"); 

{% endhighlight %}
{% endtabs %}

![ColorPicker Blend](Layout-Related-Features_images/ColorPicker_BlendTheme.png)

![ColorPicker Office2016](Layout-Related-Features_images/ColorPicker_Office2016.png)

![ColorPicker VisualStudio2013](Layout-Related-Features_images/ColorPicker_VisualStudio2013.png)

![ColorPicker Office2010](Layout-Related-Features_images/ColorPicker_Office2010.png)

![ColorPicker Office2007](Layout-Related-Features_images/ColorPicker_Office2007.png)

![ColorPicker Office2013](Layout-Related-Features_images/ColorPicker_Office2013.png)