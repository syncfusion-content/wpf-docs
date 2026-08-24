---
layout: post
title: Appearance and Styling in WPF SfDomainUpdown | Syncfusion®
description: Customize the look and feel of the Syncfusion WPF SfDomainUpDown control with built-in themes, custom templates, and styling.
platform: wpf
control: DomainUpDown
documentation: ug
---

# Appearance and Styling in WPF SfDomainUpdown

## Spin animation

Items will spin up or down with a smooth transition. The transition can be disabled using the `EnableSpinAnimation` property. The default value of `EnableSpinAnimation` is `True`.

{% tabs %}
{%highlight xaml%}

<syncfusion:SfDomainUpDown x:Name="domain"
                         HorizontalAlignment="Center"
                         VerticalAlignment="Center"
                         Width="200" EnableSpinAnimation="True"/>

{%endhighlight%}
{% endtabs %}

## Accent brush

The `AccentBrush` property is used to decorate the hot spots of the `SfDomainUpDown` control with a solid color. The default value is the system accent color.

{% tabs %}
{%highlight xaml%}

<Window x:Class="DomainUpDownSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.WPF">
    <Grid>
        <editors:SfDomainUpDown x:Name="domainUpDown"
                               HorizontalAlignment="Center"
                               VerticalAlignment="Center"
                               Width="200"
                               AccentBrush="Black"
                               Value="James" />
    </Grid>
</Window>

{%endhighlight%}
{% endtabs %}

## Customize Up, Down button Style

You can customize the appearance of the up/down buttons in the [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control by using the [UpDownStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html#Syncfusion_Windows_Controls_Input_SfDomainUpDown_UpDownStyle) property.

This property allows you to apply a custom style and template to the internal `SfUpDown` control, which hosts the up/down buttons.

{% tabs %}
{%highlight xaml%}

<Window x:Class="DomainUpDownSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfInput.WPF">
<Window.DataContext>
    <local:ViewModel />
</Window.DataContext>
<Window.Resources>

    <!-- Style for Up/Down Buttons-->
    <Style x:Key="CustomUpDownButtonStyle" TargetType="editors:SfUpDown">
        <Setter Property="BorderBrush" Value="Black"/>
        <Setter Property="FontWeight" Value="Bold"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="editors:SfUpDown">
                    <Border 
                            BorderBrush="{TemplateBinding BorderBrush}"
                            BorderThickness="1"
                            CornerRadius="2">
                        <Grid x:Name="PART_OuterGrid">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="*" />
                                <ColumnDefinition Width="Auto" />
                                <ColumnDefinition Width="Auto" />
                            </Grid.ColumnDefinitions>
                            <ContentControl x:Name="PART_Content" IsTabStop="False" Focusable="False" Content="{TemplateBinding UpDownContent}" 
                                        />
                            <Button
                            x:Name="PART_DownButton"
                            Grid.Column="1"
                            HorizontalAlignment="Stretch"
                            VerticalAlignment="Stretch"
                            Background="{TemplateBinding AccentBrush}"
                            BorderBrush="{TemplateBinding BorderBrush}"
                            Foreground="{TemplateBinding Foreground}"
                            BorderThickness="1"
                            Padding="5"
                            FontSize="20"
                            Command="{TemplateBinding DownCommand}"
                            IsTabStop="False"
                            Content="-"
                            />
                            <Button
                            x:Name="PART_UpButton"
                            Grid.Column="2"
                            HorizontalAlignment="Stretch"
                            VerticalAlignment="Stretch"
                            Background="{TemplateBinding AccentBrush}"
                            BorderBrush="{TemplateBinding BorderBrush}"
                            Foreground="{TemplateBinding Foreground}"
                            BorderThickness="1"
                            Padding="5"
                            FontSize="20"
                            Command="{TemplateBinding UpCommand}"
                            Content="+"
                            IsTabStop="False"
                            />
                        </Grid>
                    </Border>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>

    <!-- Customized SfDomainUpDown Style -->
    <Style  TargetType="syncfusion:SfDomainUpDown">
        <Setter Property="AccentBrush" Value="LightBlue" />
        <Setter Property="Foreground" Value="Black" />
        <Setter Property="Background" Value="Lavender" />
        <Setter Property="BorderBrush" Value="Black" />
        <Setter Property="BorderThickness" Value="1" />
        <Setter Property="FontSize" Value="15" />
        <Setter Property="VerticalContentAlignment" Value="Center" />
        <Setter Property="HorizontalAlignment" Value="Center" />
        <Setter Property="Padding" Value="3" />
        <Setter Property="UpDownStyle" Value="{StaticResource CustomUpDownButtonStyle}"/>
    </Style>
</Window.Resources>
<Grid>
<syncfusion:SfDomainUpDown x:Name="DomainUpDown" Height="44" Width="231" ItemsSource="{Binding Employees}">
    <syncfusion:SfDomainUpDown.ContentTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" VerticalAlignment="Center">
                <TextBlock Text="{Binding Name}" VerticalAlignment="Center" Margin="5"/>
            </StackPanel>
        </DataTemplate>
    </syncfusion:SfDomainUpDown.ContentTemplate>
</syncfusion:SfDomainUpDown>
</Grid>
</Window>

{%endhighlight%}
{% endtabs %}

![UpDown_Button Customization](Appearance-and-Styling_images/UpDown_Button.png)

## Theme

SfDomainUpDown supports various built-in themes. Refer to the below links to apply themes for the SfDomainUpDown,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
    
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting theme to WPF SfDomainUpDown](Getting-Started_images/SfDomainUpDown_theme_support.png)