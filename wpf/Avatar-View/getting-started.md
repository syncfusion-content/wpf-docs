---
layout: post
title: Getting Started with WPF AvatarView Control | Syncfusion
description: Learn about getting started with the Syncfusion Essential WPF AvatarView (SfAvatarView) control, its elements, and more.
platform: wpf
control: AvatarView
documentation: ug
---

# Getting Started with WPF AvatarView

This section explains the steps required to add the WPF [SfAvatarView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SfAvatarView.html) control with its basic features.

## Creating an application with WPF AvatarView

Follow these steps to integrate the SfAvatarView control into your WPF application:
1. Create a new WPF application.
2. Add the [Syncfusion.Shared.WPF](https://www.nuget.org/packages/Syncfusion.Shared.WPF) NuGet package to your project.
3. Import the Syncfusion WPF schema in your XAML file: `xmlns:syncfusion="http://schemas.syncfusion.com/wpf"`.
4. Initialize the SfAvatarView control in your XAML file.

## Initialize AvatarView 

By default, AvatarView control is displayed with the [Avatar1](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.AvatarCharacter.html#Syncfusion_Windows_Shared_AvatarCharacter_Avatar1) character image, AvatarShape of [Circle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.AvatarShape.html#Syncfusion_Windows_Shared_AvatarShape_Circle), and AvatarSize of [Small](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.AvatarSize.html#Syncfusion_Windows_Shared_AvatarSize_Small).

{% tabs %}
{% highlight xaml %}

<Window x:Class="GettingStarted.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:GettingStarted"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:SfAvatarView />
    </Grid>
</Window>

{% endhighlight %} 
{% highlight C# %}

// Creating an instance of the AvatarView control.
SfAvatarView avatarView = new SfAvatarView();
           
{% endhighlight %}
{% endtabs %}

![WPF AvatarView control](avatarview_images/wpf_avatarview.png)

## Initialize AvatarView with ImageSource

Add any custom image as an avatar in WPF AvatarView control using the [ImageSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SfAvatarView.html#Syncfusion_Windows_Shared_SfAvatarView_ImageSource) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfAvatarView ContentType="CustomImage"
                         AvatarSize="ExtraLarge"
                         ImageSource="Images\person.png">
</syncfusion:SfAvatarView>

{% endhighlight %} 
{% highlight C# %}

SfAvatarView avatarView = new SfAvatarView();
avatarView.ContentType = AvatarContentType.CustomImage;
avatarView.AvatarSize = AvatarSize.ExtraLarge;
avatarView.ImageSource = new BitmapImage(new Uri("ms-appx:///Images\\person.png"));
           
{% endhighlight %}
{% endtabs %}

![WPF AvatarView control with custom image](avatarview_images/wpf_avatarview_imagesource.png)
