---
layout: post
title: Collapse button options | SfGridSplitter | WPF | Syncfusion
description: Collapse button options of SfGridSplitter control for WPF
platform: WPF
control: SfGridSplitter
documentation: ug
---

# Customize Collapse button

`SfGridSplitter` has options to collapse the element in either side of the splitter using buttons.

## Enable collapse buttons

The collapse buttons can be enabled or disabled using the [EnableCollapseButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfGridSplitter~EnableCollapseButton.html) property.

{% tabs %}

{% highlight XAML %}

    <input:SfGridSplitter Grid.Row="1" EnableCollapseButton="True" x:Name="gridSplitter"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

    gridSplitter.EnableCollapseButton = true;            

{% endhighlight %}

{% highlight VB %}

    gridSplitter.EnableCollapseButton = True        

{% endhighlight %}

{% endtabs %}

Pressing the down button

![Pressing the down button](Collapse-button-options-images/Collapse-button-options-img1.jpeg)

Pressing the up button

![Pressing the up button](Collapse-button-options-images/Collapse-button-options-img2.jpeg)

## Style collapse buttons

The template collapse buttons can be customized using the properties [UpButtonTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfGridSplitter~UpButtonTemplate.html) and [DownButtonTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfGridSplitter~DownButtonTemplate.html).

{% tabs %}

{% highlight XAML %}

    <input:SfGridSplitter Grid.Row="1" ShowsPreview="True"
                        EnableCollapseButton="True" x:Name="gridSplitter">

    <input:SfGridSplitter.UpButtonTemplate>

    <ControlTemplate TargetType="Button">

    <Grid>

    <VisualStateManager.VisualStateGroups>

    <VisualStateGroup x:Name="CommonStates">

    <VisualState x:Name="Normal"/>

    <VisualState x:Name="Disabled">

    <Storyboard>

    <DoubleAnimation Duration="0" To="0.4" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="Border"/>

    <DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualWhite"/>

    <DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualBlack"/>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="PointerOver">

    <Storyboard>

    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Fill"
                                Storyboard.TargetName="Rectangle">

    <DiscreteObjectKeyFrame KeyTime="0" Value="#414242"/>

    </ObjectAnimationUsingKeyFrames>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="Pressed"></VisualState>

    </VisualStateGroup>

    <VisualStateGroup x:Name="FocusStates">

    <VisualState x:Name="Focused">

    <Storyboard>

    <DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualWhite"/>

    <DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualBlack"/>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="Unfocused"/>

    <VisualState x:Name="PointerFocused"/>

    </VisualStateGroup>

    </VisualStateManager.VisualStateGroups>

    <Border x:Name="Border">

    <Grid Width="22" Height="22">

    <Rectangle x:Name="Rectangle" Fill="Transparent" Width="22" Height="22"/>

    <Path x:Name="up" Width="13" Height="11" Stretch="Fill" Fill="White" Data="F1 M 143.011,160.869L 143.021,160.879L 143.001,160.898L 140.771,163.129L 140.771,165.325L 143.303,162.794L 144.1,161.995L 144.118,161.979L 144.906,162.764L 147.438,165.296L 147.438,163.101L 145.207,160.869L 144.108,159.773L 143.011,160.869 Z" HorizontalAlignment="Center" UseLayoutRounding="False" VerticalAlignment="Center"/>

    </Grid>

    </Border>

    <Rectangle x:Name="FocusVisualWhite" IsHitTestVisible="False"
            Opacity="0" StrokeDashOffset="1.5" StrokeEndLineCap="Square"
            Stroke="{StaticResource FocusVisualWhiteStrokeThemeBrush}"
            StrokeDashArray="1,1"/>

    <Rectangle x:Name="FocusVisualBlack" IsHitTestVisible="False"
            Opacity="0" StrokeDashOffset="0.5" StrokeEndLineCap="Square"
            Stroke="{StaticResource FocusVisualBlackStrokeThemeBrush}"
            StrokeDashArray="1,1"/>

    </Grid>

    </ControlTemplate>

    </input:SfGridSplitter.UpButtonTemplate>

    <input:SfGridSplitter.DownButtonTemplate>

    <ControlTemplate TargetType="Button">

    <Grid>

    <VisualStateManager.VisualStateGroups>

    <VisualStateGroup x:Name="CommonStates">

    <VisualState x:Name="Normal"/>

    <VisualState x:Name="PointerOver">

    <Storyboard>

    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Fill"
                                Storyboard.TargetName="Rectangle">

    <DiscreteObjectKeyFrame KeyTime="0" Value="#414242"/>

    </ObjectAnimationUsingKeyFrames>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="Disabled">

    <Storyboard>

    <DoubleAnimation Duration="0" To="0.4" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="Border"/>

    <DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualWhite"/>

    <DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualBlack"/>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="Pressed">

    </VisualState>

    </VisualStateGroup>

    <VisualStateGroup x:Name="FocusStates">

    <VisualState x:Name="Focused">

    <Storyboard>

    <DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualWhite"/>

    <DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity"
                                        Storyboard.TargetName="FocusVisualBlack"/>

    </Storyboard>

    </VisualState>

    <VisualState x:Name="Unfocused"/>

    <VisualState x:Name="PointerFocused"/>

    </VisualStateGroup>

    </VisualStateManager.VisualStateGroups>

    <Border x:Name="Border">

    <Grid Width="22" Height="22">

    <Rectangle x:Name="Rectangle" Fill="Transparent" Width="22" Height="22"/>

    <Path x:Name="down_enabled" Width="13" Height="11" Stretch="Fill"
        Fill="White" Data="F1 M 132.911,164.227L 132.921,164.217L 132.902,164.197L 130.671,161.967L 130.671,159.773L 133.203,162.304L 134,163.101L 134.019,163.119L 134.807,162.333L 137.338,159.8L 137.338,161.995L 135.107,164.227L 134.009,165.325L 132.911,164.227 Z"
        HorizontalAlignment="Center" VerticalAlignment="Center" />

    </Grid>

    </Border>

    <Rectangle x:Name="FocusVisualWhite" IsHitTestVisible="False" Opacity="0"
            StrokeDashOffset="1.5" StrokeEndLineCap="Square"
            Stroke="{StaticResource FocusVisualWhiteStrokeThemeBrush}"
            StrokeDashArray="1,1"/>

    <Rectangle x:Name="FocusVisualBlack" IsHitTestVisible="False" Opacity="0"
            StrokeDashOffset="0.5" StrokeEndLineCap="Square"
            Stroke="{StaticResource FocusVisualBlackStrokeThemeBrush}"
            StrokeDashArray="1,1"/>

    </Grid>

    </ControlTemplate>

    </input:SfGridSplitter.DownButtonTemplate>

    </input:SfGridSplitter>

{% endhighlight %}

{% endtabs %}

