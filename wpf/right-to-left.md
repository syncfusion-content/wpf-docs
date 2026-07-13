---
layout: post
title: Right-to-Left support in Syncfusion WPF UI Controls | Syncfusion
description: Learn about Right-to-Left (RTL) support in Syncfusion WPF UI Controls and more. All Syncfusion controls support Right-to-Left.
platform: wpf
control: RightToLeft
documentation: ug
---

# Right-to-Left support in Syncfusion<sup>&reg;</sup> WPF Controls

Right-to-Left (RTL) support displays the content from right-to-left direction by setting the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/system.windows.flowdirection) property to `RightToLeft`. This is helpful to support the Right-to-Left scripted languages like Arabic, Hebrew, Urdu, etc.

All WPF Syncfusion<sup>&reg;</sup> controls support Right-to-Left (RTL) based on the `FlowDirection` property. In addition to that, most controls provide [localization](Localization.md) support to change the language of strings used in the control for any specific culture.

## Prerequisites

* A Syncfusion WPF application project must be available with at least one Syncfusion control hosted on a window or page.
* For supported .NET Framework / .NET versions and Visual Studio versions, see [System Requirements](System-Requirements.md).
* RTL support relies on the WPF `FlowDirection` property and works on any control that inherits from `FrameworkElement`.

## FlowDirection enum values

The `FlowDirection` property accepts the following values from the `System.Windows.FlowDirection` enumeration:

* `LeftToRight` – Default value. Content flows from left to right.
* `RightToLeft` – Content flows from right to left; used for RTL languages.
* `Inherit` – Inherits the `FlowDirection` value from the parent element in the visual tree.

## Enabling Right-to-Left

RTL can be enabled at the application/window level (so all child controls inherit it) or at the individual control level.

### Enable RTL at the window level (XAML)

Set `FlowDirection` on the `Window` (or `Page`) so that all contained Syncfusion controls inherit the RTL layout:

```xml
<Window x:Class="SyncfusionApp.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.Wpf"
        FlowDirection="RightToLeft">
    <Grid>
        <syncfusion:ButtonAdv Content="مرحبا" Width="120" Height="40"/>
    </Grid>
</Window>
```

### Enable RTL on a single control (XAML)

To scope RTL to a specific Syncfusion control, set `FlowDirection` directly on that control:

```xml
<syncfusion:ButtonAdv Content="مرحبا"
                      Width="120" Height="40"
                      FlowDirection="RightToLeft"/>
```

### Enable RTL in code-behind (C#)

```csharp
using System.Windows;

// Set RTL on the window so all child controls inherit it.
this.FlowDirection = FlowDirection.RightToLeft;

// Or set RTL on a specific control.
buttonAdv.FlowDirection = FlowDirection.RightToLeft;
```

## Version compatibility

RTL support through `FlowDirection` is available in all Syncfusion WPF control releases that target .NET Framework 4.0+ and .NET (Core) 3.1+, since it is inherited from the WPF framework. Refer to the [Syncfusion WPF release notes](Release-notes/) for version-specific behavior.

## Supported controls and limitations

* All Syncfusion WPF controls that derive from `FrameworkElement` honor `FlowDirection="RightToLeft"`.
* Complex composite controls (for example, data grids, schedulers, and diagrams) mirror their layout; however, some nested graphical elements may not fully mirror and should be visually verified after enabling RTL.
* RTL affects layout direction only; to translate display strings, combine RTL with [localization](Localization.md).

## See also

* [Localization](Localization.md)
* [System Requirements](System-Requirements.md)