---
layout: post
title: Custom view of Syncfusion SfImageEditor control in WPF
description: This section explains how to add custom shapes or views to an image and configure custom view settings in the SfImageEditor control for WPF platform.
platform: wpf
control: SfImageEditor
documentation: ug
---

# CustomView in SfImageEditor

This feature allows you to add a custom view in the Image Editor and provides several customization options.

## Add a custom view on the image editor

You can add any custom shape or view to an image using the `AddCustomView` method in the Image Editor control. To add a custom view, specify the view and its desired `CustomViewSettings`, as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:editor="clr-namespace:Syncfusion.UI.Xaml.ImageEditor;assembly=Syncfusion.SfImageEditor.WPF">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="100"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <Button x:Name="but" Click="Button_Click" Content="CustomView" />
        <editor:SfImageEditor Grid.Row="1" x:Name="editor" ImageSource="Assets\RoadView.jpeg" />
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

using System;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Media.Imaging;
using Syncfusion.UI.Xaml.ImageEditor;

private void Button_Click(object sender, RoutedEventArgs e)
{
    BitmapImage bitmapImage = new BitmapImage();
    bitmapImage.BeginInit();
    bitmapImage.UriSource = new Uri(@"Assets/adventure.jpg", UriKind.Relative);
    bitmapImage.EndInit();
    Image image = new Image() { Height = 100, Width = 100, Source = bitmapImage };
    editor.AddCustomView(image, new CustomViewSettings());
}

{% endhighlight %}

{% endtabs %}

## Customize the custom view

`CustomViewSettings` is defined to set the values for `CanMaintainAspectRatio`, `Bounds`, `Angle`, `IsResizable`, and `IsRotatable`.

* `CanMaintainAspectRatio` property is used to decide whether the aspect ratio value needs to be maintained when resizing the custom view.

* `Bounds` property is used to set the bounds of the custom view. Using this property, you can position the custom view wherever you want on the image. In percentage, the value should fall between 0 and 100.

* `Angle` property is used to set the angle of the custom view. Using this property, you can rotate the custom view at the desired angle.

* `IsResizable` property indicates whether the custom view can be resized. The default value of `IsResizable` is `true`.

* `IsRotatable` property indicates whether the custom view can be rotated. The default value of `IsRotatable` is `false`.

{% tabs %}

{% highlight C# %}

using System.Windows;
using Syncfusion.UI.Xaml.ImageEditor;

CustomViewSettings customViewSettings = new CustomViewSettings()
{
    CanMaintainAspectRatio = false,
    Bounds = new Rect(0, 0, 100, 100),
    IsResizable = false,
    IsRotatable = true,
    Angle = 45
};

{% endhighlight %}

{% endtabs %}

![SfImageEditor](Images/CustomView.jpg)