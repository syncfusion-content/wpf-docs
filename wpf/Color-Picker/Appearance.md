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

We can customize the header of the `ColorPicker` by using the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_HeaderTemplate) property.

{% tabs %}
{% highlight xaml %}

<DataTemplate x:Key="CustomHeaderTemplate" 
              DataType="syncfusion:ColorPicker">
    <StackPanel Orientation="Horizontal">
        <Ellipse Fill="{Binding Brush,
            RelativeSource={RelativeSource FindAncestor,
            AncestorType={x:Type syncfusion:ColorPicker}}}"
                 Name="selectedColorEllipse" 
                 HorizontalAlignment="Left"
                 Width="20" Height="20"
                 Margin="2" />
    </StackPanel>
</DataTemplate>

<syncfusion:ColorPicker  HeaderTemplate="{StaticResource CustomHeaderTemplate}"
                         Name="colorPicker" 
                         Width ="50" Height="30"/>


{% endhighlight %}
{% endtabs %}

![ColorPicker with custom header template](New-User-Interface-Support_images/CustomHeader_ColorPicker.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Appearance)

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

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Appearance)

## Setting ToolTip

ToolTip is used to show the information about the segment, when you mouse over on the segment. We can show information about the selected color name using tooltip when click and dragging the mouse on the color palette. Tooltip is enabled by default, you can disable it by setting [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_EnableToolTip) to `false`.

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

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Appearance)

## Theme

ColorPicker supports various built-in themes. Refer to the below links to apply themes for the ColorPicker,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![ColorPicker with Blend visual style](Layout-Related-Features_images/ColorPicker_BlendTheme.png)
