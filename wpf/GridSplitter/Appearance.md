---
layout: post
title: Appearance of the WPF SfGridSplitter control | Syncfusion
description: Learn about UI customization and  styling support in Syncfusion WPF SfGridSplitter control and more details about the control features.
platform: wpf
control: SfGridSplitter
documentation: ug
---

# Appearance in WPF SfGridSplitter

This section explains different UI customization and styling support available in [SfGridSplitter](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfGridSplitter.html) control.

## Setting the Background

We can change the background color of `SfGridSplitter` by setting the `Background` property. The default color value of `Background` property is `Light Gray`.

{% tabs %}
{% highlight XAML %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition />
        <RowDefinition Height="auto" />
        <RowDefinition />
    </Grid.RowDefinitions>
    <Border BorderThickness="1"
            BorderBrush="Black"  
            Grid.Row="0">
        <TextBlock Text="Capturing and extracting information is one of the most important tasks a developer can perform, and making this task more engaging without relying entirely on specialized tools is an efficient way to improve productivity. In Data Capture and Extraction with C# Succinctly, author Ed Freitas guides readers toward getting more out of C# in minimal time. Email has become a pillar of our modern and connected society, and it now serves as a primary means of communication. Because each email is filled with valuable information, data extraction has emerged as a worthwhile skill set for developers in today's business world."
                   TextWrapping="Wrap" />
    </Border>
    <syncfusion:SfGridSplitter Background="Green"
                               HorizontalAlignment="Stretch"
                               Width="auto"
                               Grid.Row="1">
    </syncfusion:SfGridSplitter>
    <syncfusion:SfCalculator Grid.Row="2">           
    </syncfusion:SfCalculator>
</Grid>

{% endhighlight %}
{% endtabs %}

![SfGridSplitter with green background](Positioning-GridSplitter-images/Background.png)

## Collapse button templates

We change the `ControlTemplate` of the UpButton and DownButton templates by using the `UpButtonTemplate` and `DownButtonTemplate` properties. We can see the effect of collapse button templates only on when `EnableCollapseButton` property value is `true`.

{% tabs %}
{% highlight XAML %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition />
        <RowDefinition Height="auto" />
        <RowDefinition />
    </Grid.RowDefinitions>
    <Border BorderThickness="1" BorderBrush="Black"  Grid.Row="0">
        <TextBlock Text="Capturing and extracting information is one of the most important tasks a developer can perform, and making this task more engaging without relying entirely on specialized tools is an efficient way to improve productivity. In Data Capture and Extraction with C# Succinctly, author Ed Freitas guides readers toward getting more out of C# in minimal time. Email has become a pillar of our modern and connected society, and it now serves as a primary means of communication. Because each email is filled with valuable information, data extraction has emerged as a worthwhile skill set for developers in today's business world."
                   TextWrapping="Wrap" />
    </Border>
    <syncfusion:SfGridSplitter EnableCollapseButton="True"
                               HorizontalAlignment="Stretch"
                               Width="auto" 
                               Grid.Row="1">
        <!--Up button template-->
        <syncfusion:SfGridSplitter.UpButtonTemplate>
            <ControlTemplate>
                <TextBlock Background="Yellow">Up CollapseButton</TextBlock>
            </ControlTemplate>
        </syncfusion:SfGridSplitter.UpButtonTemplate>
        
        <!--Down button template-->
        <syncfusion:SfGridSplitter.DownButtonTemplate>
            <ControlTemplate>
                <TextBlock Background="Yellow">Down CollapseButton</TextBlock>
            </ControlTemplate>
        </syncfusion:SfGridSplitter.DownButtonTemplate>
    </syncfusion:SfGridSplitter>
    <syncfusion:SfCalculator Grid.Row="2">           
    </syncfusion:SfCalculator>
</Grid>

{% endhighlight %}
{% endtabs %}

![SfGridSplitter with expand or collapse button template](Positioning-GridSplitter-images/Collapsebuttontemplate.png)

### Setting style for Preview GridSplitter

We can change the UI and style of the preview grid splitter by using the [SfGridSplitter.PreviewStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfGridSplitter~PreviewStyle.html) property. We can see the effect of `PreviewStyle` only on when `ShowsPreview` property value is `true`.

{% tabs %}
{% highlight XAML %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition />
        <RowDefinition Height="auto" />
        <RowDefinition />
    </Grid.RowDefinitions>
    <Border BorderThickness="1" BorderBrush="Black"  Grid.Row="0">
        <TextBlock Text="Capturing and extracting information is one of the most important tasks a developer can perform, and making this task more engaging without relying entirely on specialized tools is an efficient way to improve productivity. In Data Capture and Extraction with C# Succinctly, author Ed Freitas guides readers toward getting more out of C# in minimal time. Email has become a pillar of our modern and connected society, and it now serves as a primary means of communication. Because each email is filled with valuable information, data extraction has emerged as a worthwhile skill set for developers in today's business world."
                   TextWrapping="Wrap" />
    </Border>
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
    <syncfusion:SfCalculator Grid.Row="2">            
    </syncfusion:SfCalculator>
</Grid>

{% endhighlight %}
{% endtabs %}

![SfGridSplitter with ellipse shape preview grid splitter](Positioning-GridSplitter-images/PreviewStyle.gif)