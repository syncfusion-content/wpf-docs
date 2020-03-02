---
layout: post
title: Appearance| ColorPicker | wpf | Syncfusion
description: This page includes a brief description of ColorEdit, the ColoPicker Header customization options and themes.
platform: wpf
control: ColorPicker
documentation: ug
---

# Appearance in WPF ColorPicker

This section explains different UI customization, styling, theming options available in [ColoPicker](https://www.syncfusion.com/wpf-ui-controls/colorpicker) control.

## Change Header Template

We can customize the header of the `ColorPicker` by using the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~HeaderTemplate.html) property.

{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="CustomHeaderTemplate" DataType="syncfusion:ColorPicker">
    <StackPanel Orientation="Horizontal">
        <Ellipse Fill="{Binding Brush, RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:ColorPicker}}}"
                 Name="selectedColorEllipse" HorizontalAlignment="Left" Width="20" Height="20" Margin="2" />
    </StackPanel>
</DataTemplate>

<syncfusion:ColorPicker  HeaderTemplate="{StaticResource CustomHeaderTemplate}" Name="colorPicker" Width ="50" Height="30"/>

{% endhighlight %}
{% endtabs %}

![ColorPicker with custom header template](New-User-Interface-Support_images/CustomHeader_ColorPicker.png)

## Change flow direction

We can change the flow direction of the `ColorPicker` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The Default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker FlowDirection="RightToLeft" Name="colorPicker"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker= new ColorPicker();
colorPicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![ColorPicker with RightToLeft flow direction](Layout-Related-Features_images/ColorPicker_RightToLeft.png)

## Alpha Visibility

We can change the opacity of the selected color by using the A-Alpha value editor or delicate slider in the `ColorPicker`. We can hide the A-Alpha value editor and delicate slider by using the [IsAlphaVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~IsAlphaVisible.html) property value as `false`. The default value of the `IsAlphaVisible` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker IsAlphaVisible="False" x:Name="colorPicker" />

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.IsAlphaVisible = false;

{% endhighlight %}
{% endtabs %}

![ColorPicker hides the Alpha slider and vale editor](ScRGB-Color_images/ColorPicker_IsAlphaVisible.png)

## Setting ToolTip

ToolTip is used to show the information about the segment, when you mouse over on the segment. We can show information about the selected color name using tooltip when click and dragging the mouse on the color palette. Tooltip is enabled by default, you can disable it by setting [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~EnableToolTip.html) to `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:ColorPicker EnableToolTip="True"  Name="colorPicker"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.EnableToolTip = true;

{% endhighlight %}
{% endtabs %}

![ColorPicker with TooTip support](Selection-Mode_images/ColorPicker_Tooltip.png)

## Theme

We can customize the appearance of the `ColorPicker` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinmanager.Wpf~Syncfusion.SfSkinmanager.SfSkinmanager~SetVisualStyle.html) method and `SfSkinManager.VisualStyle` property . The following are the various built-in visual styles for `ColorPicker` control.

* Blend
* Default
* Lime
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
* SystemTheme
* VisualStudio2013
* VisualStudio2015

Here, the `Blend` style is applied to the `ColorPicker`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker syncfusionskin:SfSkinManager.VisualStyle="Blend" 
                         x:Name="colorPicker" />

{% endhighlight %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

ColorPicker colorPicker = new ColorPicker();
SfSkinManager.SetVisualStyle(colorPicker, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![ColorPicker with Blend visual style](Layout-Related-Features_images/ColorPicker_BlendTheme.png)
