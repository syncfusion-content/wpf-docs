---
layout: post
title: Appearance in WPF GridSplitter control | Syncfusion
description: Learn here all about Appearance support in Syncfusion WPF GridSplitter (SfGridSplitter) control and more.
platform: wpf
control: SfGridSplitter
documentation: ug
---

# Appearance in WPF GridSplitter (SfGridSplitter)

This section explains different UI customization and styling support available in [SfGridSplitter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfGridSplitter.html) control.

## Setting the Background

We can change the background color of `SfGridSplitter` by setting the `Background` property. The default color value of `Background` property is `Light Gray`.

{% tabs %}
{% highlight XAML %}

<Border
    Margin="10"
    BorderBrush="DarkGray"
    BorderThickness="1">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition />
            <RowDefinition Height="auto" />
            <RowDefinition />
        </Grid.RowDefinitions>
        <TextBlock Grid.Row="0" 
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center"
                   TextAlignment="Center"
                   Text="Panel 1">
        </TextBlock>
        <TextBlock Grid.Row="2"
                   HorizontalAlignment="Center" 
                   VerticalAlignment="Center" 
                   TextAlignment="Center"
                   Text="Panel 2">
        </TextBlock>
        
        <!--Grid Splitter-->
        <syncfusion:SfGridSplitter Background="Green"
                                   HorizontalAlignment="Stretch"
                                   Width="auto"
                                   Grid.Row="1">
        </syncfusion:SfGridSplitter>
    </Grid>
</Border>

{% endhighlight %}
{% endtabs %}

![SfGridSplitter with green background](Positioning-GridSplitter-images/Background.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-gridsplitter-control-examples/tree/master/Samples/Appearance) 

### Custom drag preview

We can change the custom UI of the preview grid splitter by using the [SfGridSplitter.PreviewStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfGridSplitter.html) property. We can see the effect of `PreviewStyle` only on when `ShowsPreview` property value is `true`.

{% tabs %}
{% highlight XAML %}

<Border
    Margin="10"
    BorderBrush="DarkGray"
    BorderThickness="1">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition />
            <RowDefinition Height="auto" />
            <RowDefinition />
        </Grid.RowDefinitions>
        <TextBlock Grid.Row="0" 
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center"
                   TextAlignment="Center"
                   Text="Panel 1">
        </TextBlock>
        <TextBlock Grid.Row="2"
                   HorizontalAlignment="Center" 
                   VerticalAlignment="Center" 
                   TextAlignment="Center"
                   Text="Panel 2">
        </TextBlock>
        
        <!--Grid Splitter-->
        <syncfusion:SfGridSplitter ShowsPreview="True"
                           HorizontalAlignment="Stretch"
                           Width="auto"
                           Grid.Row="1" >
            <syncfusion:SfGridSplitter.PreviewStyle>
                <Style TargetType="Control">
                    <Setter Property="Background" Value="Red"/>
                    <Setter Property="Template">
                        <Setter.Value>
                            <ControlTemplate TargetType="Control">
                                <Grid x:Name="Root" Opacity="0.5">
                                    <Ellipse Fill="{TemplateBinding Background}"/>
                                </Grid>
                            </ControlTemplate>
                        </Setter.Value>
                    </Setter>
                </Style>
            </syncfusion:SfGridSplitter.PreviewStyle>
        </syncfusion:SfGridSplitter>
    </Grid>
</Border>

{% endhighlight %}
{% endtabs %}

![SfGridSplitter with ellipse shape preview grid splitter](Positioning-GridSplitter-images/PreviewStyle.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-gridsplitter-control-examples/tree/master/Samples/Appearance) 

## Theme

SfGridSplitter supports various built-in themes. Refer to the below links to apply themes for the SfGridSplitter,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfGridSplitter](Getting-Started-images/WPF-Grid-Splitter-theme-support.png)
