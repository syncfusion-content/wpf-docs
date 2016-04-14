---
layout: post
title: Getting Started with SfAccordion control for WPF
description: A quick tour to initial users on SfAccordion control for WPF
platform: wpf
control: SfAccordion
documentation: ug
---

# Getting Started

This section explains how to create a long list of expandable items using SfAccordion control.

## Adding SfAccordion control

Create a WPF Application project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfAccordion.WPF

* Syncfusion.SfShared.WPF

1.Include the namespace for Syncfusion.SfAccordion.WPF assembly in MainWindow.xaml

{% tabs %}

{% highlight XAML %}

    <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:layout="using:Syncfusion.Windows.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfAccordion` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion x:Name="accordion">

{% endhighlight %}

{% endtabs %}

## Adding children to SfAccordion control

`SfAccordion` accepts `SfAccordionItem` as its children when added directly. Here five SfAccordionItems are added as the children of the SfAccordion.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion x:Name="accordion">

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

## Setting header for Accordion items

SfAccordionItem has `Header` property to set header for the accordion items. Set the header as “WinRT” and repeat the same procedure for remaining children with the value as “Windows Phone”, “Silverlight”, “WPF” and “Windows Forms”.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion x:Name="accordion">

    <layout:SfAccordionItem Header="WPF"/>

    <layout:SfAccordionItem Header="Silverlight"/>

    <layout:SfAccordionItem Header="WinRT"/>

    <layout:SfAccordionItem Header="Windows Phone"/>

    <layout:SfAccordionItem Header="Universal"/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

## Applying template for item header

SfAccordion provides `HeaderTemplate` property that allows to apply a common data template for all accordion items header.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion x:Name="accordion">

    <layout:SfAccordion.HeaderTemplate>

    <DataTemplate>

    <Grid>

    <TextBlock Text="{Binding}" Margin="10" FontSize="18"/>

    </Grid>

    </DataTemplate>

    </layout:SfAccordion.HeaderTemplate>

{% endhighlight %}

{% endtabs %}

## Setting content for children

Any object can be set as the content of `SfAccordionItem`. SfAccordionItem.Content property helps to set the content.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion x:Name="accordion" SelectedIndex="0"
                                            AccentBrush="#FF1196CD">
    <layout:SfAccordion.HeaderTemplate>

    <DataTemplate>

    <Grid>

    <TextBlock Text="{Binding}" Margin="10" FontSize="18"/>

    </Grid>

    </DataTemplate>

    </layout:SfAccordion.HeaderTemplate>

    <layout:SfAccordionItem Header="WinRT">

    <Grid Height="256" Background="#FFF4F3F2" Width="350">

    <Grid.RowDefinitions>

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    <RowDefinition />

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    </Grid.RowDefinitions>

    <TextBlock Text="Essential Studio" Margin="10,10,10,2" FontSize="13.333"/>

    <TextBlock Text="WinRT" Grid.Row="1" Margin="10,-2,10,10" FontSize="32" />

    <RichTextBlock Margin="10,-6,10,10" Grid.Row="2" TextAlignment="Justify">

    <Paragraph>

    <Run Text="Essential Studio for WinRT contains all the controls you need to build line-of-business applications, including charts, gauges, maps, diagrams, and radial menus. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps."
    FontSize="12"/>

    </Paragraph>

    <Paragraph />

    <Paragraph>

    <Run Text="All WinRT controls are optimized for touch, supporting common gestures: zooming, panning, selecting, double-tapping, rotating, resizing. Interaction feels natural, letting you build a native user interface to delight your users."
    FontSize="12"/>

    </Paragraph>

    </RichTextBlock>

    <Border Grid.Row="3" Padding="10" Margin="10" Width="170"
            HorizontalAlignment="Right" Background="#FF86BA35">
            
    <TextBlock Text="Download free evaluation"
            Foreground="White" FontSize="13.333"/>
            
    </Border>

    </Grid>

    </layout:SfAccordionItem>

    <layout:SfAccordionItem Header="Windows Phone">

    <Grid Height="256" Background="#FFF4F3F2" Width="350">

    <Grid.RowDefinitions>

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    <RowDefinition />

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    </Grid.RowDefinitions>

    <TextBlock Text="Essential Studio" Margin="10,10,10,2"
                                    FontSize="13.333"/>
                                    
    <TextBlock Text="Windows Phone" Grid.Row="1"
            Margin="10,-2,10,10" FontSize="32" />
            
    <RichTextBlock Margin="10,-6,10,10" Grid.Row="2"
                TextAlignment="Justify">
                
    <Paragraph>

    <Run Text="Essential Studio for Windows Phone 7 contains all the controls you need to build line-of-business mobile applications including charts, gauges, maps, editors, and much more."
    FontSize="12"/>

    </Paragraph>

    <Paragraph />

    <Paragraph>

    <Run Text="All components in the toolkit solve real problems; we never include controls just to increase the total count. Every component has been built as a solution to a real problem that developers face when creating enterprise applications."
    FontSize="12"/>

    </Paragraph>

    </RichTextBlock>

    <Border Grid.Row="3" Padding="10" Margin="10"
            Width="170" HorizontalAlignment="Right"
            Background="#FF86BA35">
            
    <TextBlock Text="Download free evaluation"
            Foreground="White" FontSize="13.333"/>
            
    </Border>

    </Grid>

    </layout:SfAccordionItem>

    <layout:SfAccordionItem Header="Silverlight">

    <Grid Height="256" Background="#FFF4F3F2" Width="350">

    <Grid.RowDefinitions>

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    <RowDefinition />

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    </Grid.RowDefinitions>

    <TextBlock Text="Essential Studio" Margin="10,10,10,2"
                                    FontSize="13.333"/>
                                    
    <TextBlock Text="Silverlight" Grid.Row="1"
            Margin="10,-2,10,10" FontSize="32" />
            
    <RichTextBlock Margin="10,-6,10,10" Grid.Row="2"
                TextAlignment="Justify">
                
    <Paragraph>

    <Run Text="Essential Studio for Silverlight contains all the controls you need for building typical line-of-business web applications including grids, charts, gauges, menus, calendars, editors, and much more. It also includes some unique controls that enable your applications to read and write Excel, Word, and PDF documents." FontSize="12"/>

    </Paragraph>

    <Paragraph />

    <Paragraph>

    <Run Text="All components in the toolkit solve real problems; we never include controls just to increase the total count. Every component has been built as a solution to a real problem that developers face when creating enterprise applications."
    FontSize="12"/>

    </Paragraph>

    </RichTextBlock>

    <Border Grid.Row="3" Padding="10" Margin="10" Width="170"
            HorizontalAlignment="Right" Background="#FF86BA35">
            
    <TextBlock Text="Download free evaluation"
            Foreground="White" FontSize="13.333"/>
            
    </Border>

    </Grid>

    </layout:SfAccordionItem>

    <layout:SfAccordionItem Header="WPF">

    <Grid Height="256" Background="#FFF4F3F2" Width="350">

    <Grid.RowDefinitions>

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    <RowDefinition />

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    </Grid.RowDefinitions>

    <TextBlock Text="Essential Studio"
            Margin="10,10,10,2" FontSize="13.333"/>

    <TextBlock Text="WPF" Grid.Row="1"
            Margin="10,-2,10,10" FontSize="32" />

    <RichTextBlock Margin="10,-6,10,10"
                Grid.Row="2" TextAlignment="Justify">
                
    <Paragraph>

    <Run Text="Essential Studio for WPF contains all the controls that you need for building typical line-of-business web applications including grids, charts, gauges, menus, calendars, editors, and much more. It also includes some unique controls that enable your applications to read and write Excel, Word, and PDF documents." FontSize="12"/>

    </Paragraph>

    <Paragraph />

    <Paragraph>

    <Run Text="All components in the toolkit solve real problems; we never include controls just to increase the total count. Every component has been built as a solution to a real problem that developers face when creating enterprise applications."
    FontSize="12"/>

    </Paragraph>

    </RichTextBlock>

    <Border Grid.Row="3" Padding="10" Margin="10"
            Width="170" HorizontalAlignment="Right"
            Background="#FF86BA35">
            
    <TextBlock Text="Download free evaluation"
            Foreground="White" FontSize="13.333"/>
            
    </Border>

    </Grid>

    </layout:SfAccordionItem>

    <layout:SfAccordionItem Header="Windows Forms">

    <Grid Height="256" Background="#FFF4F3F2" Width="350">

    <Grid.RowDefinitions>

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    <RowDefinition />

    <RowDefinition Height="Auto"/>

    <RowDefinition Height="Auto"/>

    </Grid.RowDefinitions>

    <TextBlock Text="Essential Studio"
            Margin="10,10,10,2" FontSize="13.333"/>
            
    <TextBlock Text="Windows Forms" Grid.Row="1"
            Margin="10,-2,10,10" FontSize="32" />
            
    <RichTextBlock Margin="10,-6,10,10" Grid.Row="2"
                TextAlignment="Justify">
                
    <Paragraph>

    <Run Text="Essential Studio for Windows Forms contains all the controls that you need for building typical line-of-business web applications including grids, charts, gauges, menus, calendars, editors, and much more. It also includes some unique controls that enable your applications to read and write Excel, Word, and PDF documents." FontSize="12"/>

    </Paragraph>

    <Paragraph />

    <Paragraph>

    <Run Text="All components in the toolkit solve real problems; we never include controls just to increase the total count. Every component has been built as a solution to a real problem that developers face when creating enterprise applications."
    FontSize="12"/>

    </Paragraph>

    </RichTextBlock>

    <Border Grid.Row="3" Padding="10" Margin="10"
            Width="170" HorizontalAlignment="Right"
            Background="#FF86BA35">
            
    <TextBlock Text="Download free evaluation"
            Foreground="White" FontSize="13.333"/>
            
    </Border>

    </Grid>

    </layout:SfAccordionItem>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}