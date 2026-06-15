---
layout: post
title: Appearance and Styling in WPF Toast Notification control | Syncfusion®
description: Learn how to customize Syncfusion® WPF Toast Notification (SfToastNotification) using severity, variants, accent brush, placement, and animations.
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

## ToastSound

Toast notification supports multiple sound options when displaying notifications, helping to improve user awareness and ensuring important messages are not easily missed.

Custom toasts support three predefined sound values (Silent, Beep, and Hand) from the ToastSound enum, allowing developers to enhance notifications with simple audio cues.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{  
    Title = "Notification",
    Header = "Custom Toast",
    Message = "Notification with Beep sound",
    Mode = ToastMode.Screen,
    ToastSound = ToastSound.Beep
});

{% endhighlight %}
{% endtabs %}

System toast notifications support the remaining 26 predefined sounds from the ToastSound enum (excluding Beep and Hand), enabling developers to choose from a wide range of standard notification tones that align with the operating system’s native look and feel.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{ 
    Title = "Notification",
    Header = "System Toast",
    Message = "New messages were received", 
    Mode = ToastMode.Default,
    ToastSound = ToastSound.LoopingAlarm
});

{% endhighlight %}
{% endtabs %}

## ToastSoundPath

Toast notification allows you to play a custom audio file for custom toasts using the ToastSoundPath property. This enables developers to provide a more personalized notification experience by using their own sound files.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{  
    Title = "Notification",
    Header = "Custom Toast",
    Message = "Notification with Beep sound",
    Mode = ToastMode.Screen,
    ToastSoundPath = new Uri(@"C:\Windows\Media\chimes.wav")
});

{% endhighlight %}
{% endtabs %}

N> Supported audio formats include:
.mp3, .wav, .flac, .m4a, .aac, and .wma.

## MaxToastVisibleCount

Toast notification supports the MaxToastVisibleCount property to control how many toast notifications are displayed at the same time. This helps manage multiple notifications efficiently and prevents clutter in the user interface.

By default, the value is set to 2, allowing only two notifications to be visible simultaneously.

{% tabs %}
{% highlight C# %}

SfToastNotification.Show(this, new ToastOptions
{   
    Title = "Notification",
    Header = "Custom Toast",
    Message = "New messages arrived",
    Mode = ToastMode.Screen,
    MaxToastVisibleCount = 4
});

{% endhighlight %}
{% endtabs %}

![MaxToastVisibleCount video](Images/MaxToastVisibleCount.gif)

N> Supported audio formats include:
.mp3, .wav, .flac, .m4a, .aac, and .wma.

N> Appearance customization features such as Severity, Variant, and AccentBrush, as well as behavior-related options like Placement, ShowAnimationType, CloseAnimationType, MaxToastVisibleCount and Duration, are supported only for custom toast notifications displayed in Window or Screen mode. These are not supported in Default mode, as OS-level toast appearance, placement, animation, and timing are controlled by the operating system. Additionally, Variant and AccentBrush are applicable only when Severity is set to Info, Success, Warning, or Error, and not when it is set to None.
