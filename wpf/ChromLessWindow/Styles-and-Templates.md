---
layout: post
title: Styles-and-Templates
description: styles and templates
platform: wpf
control: ChromelessWindow
documentation: ug
---

# Styles and Templates

This section deals with the following Styles and Templates supported by ChromelessWindow control. 

## Custom Template for Title Bar

ChromelessWindow enables you to write your own templates for the TitleBar. The TitleBarTemplate property is used to apply this custom template to the TitleBar.

The following code snippet illustrates how to set the TitleBarTemplate property.
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="http://schemas.syncfusion.com/wpf"

Title="ChromelessWindowTestSample" Height="300" Width="300"

TitleBarTemplate="{StaticResource TemplateKey}">

</shared:ChromelessWindow>

{% endhighlight  %}

For example, use the following code for a TitleBarTemplate.
{% highlight html %}
[XAML]



<ControlTemplate x:Key="TemplateKey" TargetType="{x:Type shared:TitleBar}">

    <Border Name="border" Height="30" CornerRadius="5,5,0,0" Background="Red">

        <Border BorderBrush="#4A4A4A" Background="Transparent" BorderThickness="0,0,0,1" Width="Auto" CornerRadius="5,5,0,0">

        </Border>

    </Border>

</ControlTemplate>

{% endhighlight %}

![](Styles-and-Templates_images/Styles-and-Templates_img1.jpeg)





![](Styles-and-Templates_images/Styles-and-Templates_img2.jpeg)



## Custom Template for Minimize Button

ChromelessWindow enables you to write your own templates for the Minimize button that is used in the TitleBar. MinimizeButtonTemplate property is used to apply the custom template for the Minimize button of the TitleBar.

The following code snippet illustrates how to set the MinimizeButtonTemplate property.
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300"  MinimizeButtonTemplate="{StaticResource  MinTemplateKey}">



</ shared:ChromelessWindow>

{% endhighlight %}

For example, use the following code for a MinimizeButtonTemplate.
{% highlight html %}
[XAML]



<!--Sample code for the Control Template-->

<ControlTemplate x:Key="MinTemplateKey" TargetType="{x:Type shared:TitleButton}">

    <Border Name="border"  Height="30"  Width="30"  CornerRadius="5,5,0,0"  Background="Red">

        <Border BorderBrush="#4A4A4A" Background="Transparent" BorderThickness="0,0,0,1" 	Width="Auto" CornerRadius="5,5,0,0">

        </Border>

    </Border>

</ControlTemplate>

{% endhighlight %}

## Custom Template for Maximize Button

ChromelessWindow enables you to write your own templates for the Maximize button that is used in the TitleBar. MaximizeButtonTemplate property is used to apply the template for the Maximize button of the TitleBar.

The following code snippet illustrates how to set the MaximizeButtonTemplate property.
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300"  MaximizeButtonTemplate="{StaticResource  MaxTemplateKey}">



</ shared:ChromelessWindow>

{% endhighlight %}

For example, use the following code for a MaximizeButtonTemplate.
{% highlight html %}
[XAML]



<!--Sample code for the Control Template-->

<ControlTemplate x:Key="MaxTemplateKey" TargetType="{x:Type shared:TitleButton}">

    <Border Name="border"  Height="30"  Width="30"  CornerRadius="5,5,0,0"  Background="Red">

        <Border BorderBrush="#4A4A4A" Background="Transparent" BorderThickness="0,0,0,1" 	Width="Auto" CornerRadius="5,5,0,0">

        </Border>

    </Border>

</ControlTemplate>

{% endhighlight %}

## Custom Template for Restore Button

ChromelessWindow enables you to write your own template for the Restore button in the TitleBar. RestoreButtonTemplate property is used to apply the template for the Restore button.

To set the RestoreButtonTemplate property, use the below code
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300"  RestoreButtonTemplate="{StaticResource  ResTemplateKey}">

</ shared:ChromelessWindow>

{% endhighlight  %}

For example, use the following code for a RestoreButtonTemplate.
{% highlight html %}
[XAML]



<!--Sample code for the Control Template-->

<ControlTemplate x:Key="ResTemplateKey" TargetType="{x:Type shared:TitleButton}">

    <Border Name="border"  Height="30"  Width="30"  CornerRadius="5,5,0,0"  Background="Red">

        <Border BorderBrush="#4A4A4A" Background="Transparent" BorderThickness="0,0,0,1" Width="Auto" CornerRadius="5,5,0,0">

        </Border>

    </Border>

</ControlTemplate>

{% endhighlight %}

## Custom Template for Close Button

ChromelessWindow enables you to write your own templates for the Close button in the TitleBar. CloseButtonTemplate property is used to apply the template for the close button.

To set the CloseButtonTemplate property, use the following code.
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300"  CloseButtonTemplate="{StaticResource  CloseTemplateKey}">

</ shared:ChromelessWindow>


{% endhighlight  %}
For example, use the following code for a CloseButtonTemplate.
{% highlight html %}
[XAML]



<!--Sample code for the Control Template-->

<ControlTemplate x:Key="CloseTemplateKey" TargetType="{x:Type shared:TitleButton}">

    <Border Name="border"  Height="30"  Width="30"  CornerRadius="5,5,0,0"  Background="Red">

        <Border BorderBrush="#4A4A4A" Background="Transparent" BorderThickness="0,0,0,1" 	Width="Auto" CornerRadius="5,5,0,0">

        </Border>

    </Border>

</ControlTemplate>

{% endhighlight  %}

