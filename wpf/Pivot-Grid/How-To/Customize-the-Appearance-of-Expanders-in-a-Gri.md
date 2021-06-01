---
layout: post
title: 143-Customize-the-Appearance-of-Expanders-in-a-Gri | Syncfusion
description: Section helps to know how to customize the appearance of expanders using customized styles in PivotGrid control.
platform: wpf
control: PivotGridControl
documentation: ug
---

# How to customize the appearance of expanders in PivotGrid?

Define your own style for the expander and assign that style to the `ExpanderStyle` property of the PivotGrid control.

Please refer the below code sample. Here we have defined our own style for expander and assigned it to the `ExpanderStyle` property of the PivotGrid control.

{}

{% highlight xaml %}

    <Window.Resources>
        <Style TargetType="ToggleButton" x:Key="GridExpanderStyle">
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="{x:Type ToggleButton}">
                        <Border Padding="{TemplateBinding Padding}">
                            <Grid SnapsToDevicePixels="False" Background="Transparent">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="13"/>
                                    <ColumnDefinition Width="*"/>
                                </Grid.ColumnDefinitions>
                                <Ellipse x:Name="circle" Stroke="DarkGray" HorizontalAlignment="Center" VerticalAlignment="Center" Width="13" Height="13"/>
                                <Path x:Name="arrow" Stroke="#666" StrokeThickness="2" HorizontalAlignment="Center" VerticalAlignment="Center" SnapsToDevicePixels="false" Data="M 1,4.5  L 4.5,1  L 8,4.5"/>
                                <ContentPresenter HorizontalAlignment="Left" Margin="2,0,0,0" VerticalAlignment="Center" SnapsToDevicePixels="True" Grid.Column="1" RecognizesAccessKey="True"/>
                            </Grid>
                        </Border>
                        <ControlTemplate.Triggers>
                            <Trigger Property="IsChecked" Value="true">
                                <Setter Property="Data" TargetName="arrow" Value="M 1,1.5 L 4.5,5 L 8,1.5"/>
                            </Trigger>
                            <Trigger Property="IsMouseOver" Value="true">
                                <Setter Property="Stroke" TargetName="circle" Value="#FF3C7FB1"/>
                                <Setter Property="Stroke" TargetName="arrow" Value="#222"/>
                            </Trigger>
                            <Trigger Property="IsPressed" Value="true">
                                <Setter Property="Stroke" TargetName="circle" Value="#FF526C7B"/>
                                <Setter Property="StrokeThickness" TargetName="circle" Value="1.5"/>
                                <Setter Property="Stroke" TargetName="arrow" Value="#FF003366"/>
                            </Trigger>
                        </ControlTemplate.Triggers>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Window.Resources>

    <!--Binding the expander style to the grid-->
    <syncfusion:PivotGridControl Name="pivotGrid" ExpanderStyle="{StaticResource GridExpanderStyle}" HorizontalAlignment="Left" VerticalAlignment="Top"/>
    <Grid>

{% endhighlight %}