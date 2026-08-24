---
layout: post
title: Appearance in WPF color picker control | Syncfusion®
description: Learn here all about Appearance support in Syncfusion® WPF color picker (ColorPicker) control and more.
platform: wpf
control: ColorPicker
documentation: ug
---

# Appearance in WPF color picker (ColorPicker)

This section explains the UI customization, styling, and theming options available for the [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) control.

## Change Header Template

You can customize the header of the `ColorPicker` by using the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_HeaderTemplate) property.

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

You can change the flow direction of the `ColorPicker` layout to right-to-left by setting the `FlowDirection` property to `RightToLeft`. The default value of `FlowDirection` is `LeftToRight`.

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

The tooltip shows information about the color under the cursor. The selected color name is shown in a tooltip when you click and drag the mouse on the color palette. The tooltip is enabled by default; you can disable it by setting [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_EnableToolTip) to `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:ColorPicker EnableToolTip="True"  Name="colorPicker"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.EnableToolTip = true;

{% endhighlight %}
{% endtabs %}

![ColorPicker with ToolTip support](Selection-Mode_images/ColorPicker_Tooltip.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Appearance)

## Theme

ColorPicker supports various built-in themes. Refer to the below links to apply themes for the ColorPicker,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting theme to WPF ColorPicker](Getting-Started_images/wpf-color-picker-theme-support.png)
