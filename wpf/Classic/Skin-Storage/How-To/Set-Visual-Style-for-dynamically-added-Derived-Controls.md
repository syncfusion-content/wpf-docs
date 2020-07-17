---
layout: post
title: Set Visual Style for dynamically added Derived Controls| SkinStorage (Classic) | Wpf | Syncfusion
description: set visual style for dynamically added derived controls
platform: wpf
control: SkinStorage (Classic)
documentation: ug
---

# Set Visual Style for dynamically added Derived Controls

Normally, a control added to an application will dynamically pick up the existing style using the Skin Manager. But when an user control derived from the existing control is added to an application, a style based on the Base class should be defined in the application. 

The following code snippet explains the scenario where an user control of Button type is exposed here.


{% tabs %}
{% highlight xaml %}

<Button x:Class="WpfApplication2.TestButton"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 
Height="300" Width="300" xmlns:theme="http://schemas.syncfusion.com/wpf" theme:SkinStorage.VisualStyle="Blend">  
</Button>

{% endhighlight %}

{% highlight C# %}

public partial class TestButton : Button
{
    public TestButton()
    {
        InitializeComponent();
    }
}

{% endhighlight %}
{% endtabs %}

Styles based on the button style should be defined in the application as follows. You have to merge the corresponding Resource Dictionary when overriding the style in the application.

{% tabs %}
{% highlight xaml %}

<Application.Resources>
<ResourceDictionary>
<ResourceDictionary.MergedDictionaries>
<ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/BlendStyle.xaml"/>
</ResourceDictionary.MergedDictionaries>        
<Style TargetType="local:TestButton" BasedOn="{StaticResource BlendButtonStyle}">
<Setter Property="Background" Value="GoldenRod"/>
</Style>
</ResourceDictionary>
</Application.Resources>

{% endhighlight %}
{% endtabs %}

The output is displayed as shown below.

![](Set-Visual-Style-for-dynamically-added-Derived-Controls_images/Set-Visual-Style-for-dynamically-added-Derived-Controls_img1.png)
