---
layout: post
title: Appearance and Styling in WPF Toast Notification control | Syncfusion®
description: Learn how to customize the appearance and visual behavior of Syncfusion® WPF Toast Notification (SfToastNotification) by using severity, variants, accent brush, placement, and animations.
platform: wpf
control: SfToastNotification
documentation: ug
---

# Appearance and Styling in WPF Toast Notification

This section explains how to customize the appearance and visual behavior of toast notifications by using severity, variants, accent brush, placement, and animations.

## Severity and Variant

Toast notifications support multiple severity levels with built-in visual styling and provide three visual variants to suit different design preferences.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Title = "Updates",
    Message = "Your project has been synchronized successfully",
    Mode = ToastMode.Screen,
    Severity = ToastSeverity.Success,
    Variant = ToastVariant.Filled
});

{% endhighlight %}
{% endtabs %}

![SfToastNotification Severity image](Images/wpf_toast_banner.png)

### Variant Behavior with Severity

| **Severity ↓ / Variant →** | **Text** | **Fill** | **Outlined** |
|----------------------------|----------|----------|--------------|
| **Info** | ![SfToastNotification Text Info image](Images/text-info-image.png) | ![SfToastNotification Text Fill image](Images/fill-info-image.png) | ![SfToastNotification Outlined Info image](Images/outline-info-image.png) |
| **Success** | ![SfToastNotification Text Success image](Images/text-success-image.png) | ![SfToastNotification Filled Success image](Images/filled-success-image.png) | ![SfToastNotification Outline Success image](Images/outline-success-image.png) |
| **Warning** | ![SfToastNotification Text Warning image](Images/text-warning-image.png) | ![SfToastNotification Fill Warning image](Images/fill-warning-image.png) | ![SfToastNotification Outline Warning image](Images/outline-warning-image.png) |
| **Error** | ![SfToastNotification Text Error image](Images/text-error-image.png) | ![SfToastNotification Fill Error image](Images/fill-error-image.png) | ![SfToastNotification Outline Error image](Images/outline-error-image.png) |

## Accent Brush

You can use the [AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SfToastNotification.ToastOptions.html#Syncfusion_UI_Xaml_SfToastNotification_ToastOptions_AccentBrush) property to further customize the appearance of a toast notification after severity and variant are applied. This property allows you to adjust the color accents and overall visual styling of the toast.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Title = "Error",
    Message = "Accent brush customizes error styling",
    Mode = ToastMode.Screen,
    Severity = ToastSeverity.Error,
    AccentBrush = new SolidColorBrush(Colors.Violet)
});

{% endhighlight %}
{% endtabs %}

![SfToastNotification Accent brush image](Images/accent-brush-image.png)

## Placement

Toast notifications support multiple placement options, allowing notifications to appear at different positions within the application window or screen.

The supported placement options are: `TopLeft`, `TopCenter`, `TopRight`, `LeftCenter`, `RightCenter`, `BottomLeft`, `BottomCenter`, and `BottomRight`.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Message = "Top-Left Position",
    Placement = ToastPlacement.TopLeft,
    Mode = ToastMode.Screen
});

{% endhighlight %}
{% endtabs %}

![SfToastNotification Placement image](Images/wpf_toast_placement.gif)

## Animations

Toast notifications support built-in animation types that control how notifications appear and disappear on the screen. You can configure the show and hide animations independently to customize the visual behavior of the toast.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{
    Message = "Fade effect",
    Mode = ToastMode.Screen,
    ShowAnimationType = ToastAnimation.FadeIn,
    CloseAnimationType = ToastAnimation.FadeOut
});

{% endhighlight %}
{% endtabs %}

![SfToastNotification Animation image](Images/wpf_toastnotification_animation.gif)

### Available Animations

| Animation | In | Out |
|-----------|----|-----|
| **Fade** | `FadeIn` | `FadeOut` |
| **Zoom** | `FadeZoomIn` | `FadeZoomOut` |
| **Slide** | `SlideBottomIn` | `SlideBottomOut` |
| **Flip Left Down** | `FlipLeftDownIn` | `FlipLeftDownOut` |
| **Flip Left Up** | `FlipLeftUpIn` | `FlipLeftUpOut` |
| **Flip Right Down** | `FlipRightDownIn` | `FlipRightDownOut` |
| **None** | `None` | `None` |