---
layout: post
title: Styling in WPF Chromeless Window Control | Syncfusion
description: Learn about Styling the ChromelessWindow support in Syncfusion WPF Chromeless Window control and more.
platform: wpf
control: ChromelessWindow
documentation: ug
---
# Styling the ChromelessWindow in WPF Chromeless Window

This section describes the styles and templates supported by the ChromelessWindow control.

## Custom template for the TitleBar

ChromelessWindow allows you to write your own templates for the TitleBar. The TitleBar can be customized by using the [TitleBarTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_TitleBarTemplate)property. The following code snippet illustrates how to set the `TitleBarTemplate` property.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525" TitleBarTemplate="{StaticResource TitleBarTemplateKey}"   
syncfusion:SkinStorage.VisualStyle="Metro" x:Name="_chromelessWindow"    
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"  >
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

For example, use the following code for a `TitleBarTemplate`.

{% tabs %}

{% highlight XAML %}

<ControlTemplate x:Key="TitleBarTemplateKey" TargetType="{x:Type syncfusion:TitleBar}">
<Border x:Name="MainGrid"  Height="30" CornerRadius="5,5,0,0" Background="Bisque" >
<Border BorderBrush="Transparent" Background="Transparent" BorderThickness=".5" Width="Auto" CornerRadius="0,0,0,0">
<ContentPresenter   HorizontalAlignment="Stretch" VerticalAlignment="Center" />
</Border>
</Border>
</ControlTemplate>

{% endhighlight %}

{% endtabs %}

N> The drag-and-drop feature for the ChromelessWindow is available only when a TitleBar is present. To enable this feature, include a TitleBar in your ChromelessWindow and specify its name as `PART_TitleBar`.

![Styling-the-ChromelessWindow_img1](Styling-the-ChromelessWindow_images/Styling-the-ChromelessWindow_img1.jpeg)

## Custom template for the TitleButton

ChromelessWindow enables you to write your own templates for the title buttons that are used in the TitleBar. The **Maximize**, **Minimize**, **Restore**, and **Close** buttons can be edited with the `MaximizeButtonTemplate`, `MinimizeButtonTemplate`, `RestoreButtonTemplate`, and `CloseButtonTemplate` properties, respectively. The following example changes the template of the Maximize button using the `MaximizeButtonTemplate` property.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525" MaximizeButtonTemplate="{StaticResource MaxTemplateKey}" 
syncfusion:SkinStorage.VisualStyle="Metro"    x:Name="_chromelessWindow"    
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
<Grid>
</Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

For example, use the following code for a `MaximizeButtonTemplate`.

{% tabs %}

{% highlight XAML %}

<ControlTemplate x:Key="MaxTemplateKey" TargetType="{x:Type syncfusion:TitleButton}">
<Border SnapsToDevicePixels="true" x:Name="maxborder" Width="15" Height="15" Background="Coral"  
BorderThickness="0" BorderBrush="Transparent">
<Grid SnapsToDevicePixels="true" x:Name="grid" HorizontalAlignment="Center" VerticalAlignment="Center" Width="9" Height="8">
<Path Name="pathButton" SnapsToDevicePixels="True"  Stretch="Fill" StrokeThickness="1"               
Data="M1,1 L8,1 L8,8 L1,8 z M1,2 L8,2" Stroke="Green"
HorizontalAlignment="Center" VerticalAlignment="Center"  Width="9" Height="8">
</Path>                  
</Grid>
</Border>
</ControlTemplate>

{% endhighlight %}

{% endtabs %}

![Styling-the-ChromelessWindow_img2](Styling-the-ChromelessWindow_images/Styling-the-ChromelessWindow_img2.jpeg)

Similarly, the template for any other button can be changed by using the corresponding button property.

## Overriding the default style

ChromelessWindow can be customized by editing the default template. The default style can be downloaded from the following link:

[https://www.syncfusion.com/downloads/support/directtrac/general/ze/DefaultStyle-1700710349](https://www.syncfusion.com/downloads/support/directtrac/general/ze/DefaultStyle-1700710349)

This default style needs to be included in the `App.xaml` file of your application, and you can override this style as you desire.

N> All the templates should be written in `App.xaml`. To register the default style, merge the downloaded `ResourceDictionary` in `App.xaml` as shown below.

The below example is illustrated to override the ChromelessWindow's full style 

{% tabs %}

{% highlight XAML %}

<ControlTemplate x:Key="TitleBarTemplateKey" TargetType="{x:Type syncfusion:TitleBar}">
<Border Name="border" Background="#AA161616" Height="30">
<ContentPresenter HorizontalAlignment="Stretch" VerticalAlignment="Bottom" Margin="0,0,0,0"/>
</Border>
</ControlTemplate>
<ControlTemplate x:Key="ChromelessWindowTemplate" TargetType="{x:Type syncfusion:ChromelessWindow}">
<AdornerDecorator>
<Border Name="OuterBorder" Background="#F1401013" BorderThickness="2" CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}" BorderBrush="#401013">
......
......
......
<syncfusion:TitleBar Name="PART_TitleBar" Grid.Row="0" Template="{StaticResource TitleBarTemplateKey}" >
<Grid VerticalAlignment="Top" Height="30">
<StackPanel Orientation="Horizontal">
<Image x:Name="PART_Icon" Source="{Binding RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type syncfusion:ChromelessWindow}}, Path=Icon}" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="4,4,2,4"  MaxWidth="16" MaxHeight="16" MinWidth="16" MinHeight="16" />
<ContentControl Foreground="White" Content="{TemplateBinding Title}" VerticalAlignment="Center" HorizontalAlignment="Left" x:Name="TitlePresenter" Margin="5,5,5,5" />
</StackPanel>
......
......
</Grid>
</syncfusion:TitleBar>
......
......
</Grid>
</Border>               
</AdornerDecorator>
</ControlTemplate>

{% endhighlight %}

{% endtabs %}

Then apply this style to the ChromelessWindow using the `Template` property.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525" Template="{StaticResource ChromelessWindowTemplate}"   
syncfusion:SkinStorage.VisualStyle="Metro" x:Name="_chromelessWindow"    
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"  >
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

The following screenshot shows the custom ChromelessWindow control created using the preceding code.

![Styling-the-ChromelessWindow_img3](Styling-the-ChromelessWindow_images/Styling-the-ChromelessWindow_img3.jpeg)
