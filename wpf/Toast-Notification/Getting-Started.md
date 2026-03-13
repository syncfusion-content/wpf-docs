---
layout: post
title: Getting Started with WPF Toast Notification | Syncfusion®
description: Learn here about getting started with Syncfusion® WPF Toast Notification (SfToastNotification) control and more details.
platform: wpf
control: SfToastNotification
documentation: ug
---

# Getting Started with WPF Toast Notification

This guide will help you get started with the SfToastNotification control in your WPF application.

## Installation

### NuGet Package

You can install the Toast Notification control via NuGet package manager:

```
Install-Package Syncfusion.SfToastNotification.WPF
```

Alternatively, add the reference directly in your project file:

```xml
<ItemGroup>
    <PackageReference Include="Syncfusion.SfToastNotification.WPF" Version="*" />
</ItemGroup>
```

## Initializing the Toast Notification

### Application Startup Configuration

The SfToastNotification control is a non-UI control that handles native Windows toasts. Initialize it in your `App.xaml.cs` `ApplicationStartup` event:

```csharp
using System.Windows;
using Syncfusion.UI.Xaml.SfToastNotification;

namespace ToastNotificationDemo
{
    public partial class App : Application
    {
        private void Application_Startup(object sender, StartupEventArgs e)
        {
            // Initialize the Toast Notification bootstrapper
            WindowsToastBootstrapper.RemoveShortcutOnUnload = true;
            WindowsToastBootstrapper.Initialize("ToastNotificationDemo.App", "ToastNotificationDemo");
        }
    }
}
```

### App.xaml Configuration

```xaml
<Application x:Class="ToastNotificationDemo.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             StartupUri="MainWindow.xaml"
             Startup="Application_Startup">
    <Application.Resources>
    </Application.Resources>
</Application>
```

## Basic Setup - C# Only

Since SfToastNotification is a non-UI control, you can create and display toasts entirely through C# code. No XAML markup is required:

```csharp
using System;
using System.Windows;
using Syncfusion.UI.Xaml.SfToastNotification;

namespace ToastNotificationDemo
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void ShowSuccessToast_Click(object sender, RoutedEventArgs e)
        {
            SfToastNotification.Show(this, new ToastOptions
            {
                Title = "Success",
                Message = "Operation completed successfully!",
                Severity = ToastSeverity.Success,
                Duration = TimeSpan.FromSeconds(3)
            });
        }

        private void ShowErrorToast_Click(object sender, RoutedEventArgs e)
        {
            SfToastNotification.Show(this, new ToastOptions
            {
                Title = "Error",
                Message = "An error occurred. Please try again.",
                Severity = ToastSeverity.Error,
                Duration = TimeSpan.FromSeconds(5)
            });
        }

        private void ShowInfoToast_Click(object sender, RoutedEventArgs e)
        {
            SfToastNotification.Show(this, new ToastOptions
            {
                Title = "Information",
                Message = "This is an informational message.",
                Severity = ToastSeverity.Info,
                Duration = TimeSpan.FromSeconds(4)
            });
        }
    }
}
```

## Displaying Your First Toast

### Simple Toast Example

```csharp
// Show a simple information toast from any location in your application
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Welcome",
    Message = "Hello! This is your first toast notification.",
    Duration = TimeSpan.FromSeconds(5)
});
```

### Toast with Custom Duration

```csharp
// Toast with 10 second duration
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Processing",
    Message = "Your request is being processed...",
    Duration = TimeSpan.FromSeconds(10)
});
```

### Toast without Auto-Close

```csharp
// Toast remains until user closes it manually
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Important",
    Message = "Please review this important notification.",
    PreventAutoClose = true,
    ShowCloseButton = true
});
```

## Next Steps

- Explore [Core Concepts](Core-Concepts.md) to understand Toast Modes, Severity Levels, Variants, and practical usage patterns
