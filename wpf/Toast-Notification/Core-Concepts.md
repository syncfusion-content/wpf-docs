---
layout: post
title: Core Concepts of WPF Toast Notification | Syncfusion®
description: Learn about core concepts of Syncfusion® WPF Toast Notification control including modes, severity levels, variants, and placement.
platform: wpf
control: SfToastNotification
documentation: ug
---

# Core Concepts

## Toast Modes

The SfToastNotification control supports three different display modes to suit various application scenarios.

### 1. Default Mode

Uses the native operating system toast notifications. Ideal for applications that want to integrate with the OS notification system.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "System Notification",
    Message = "Using native OS toast",
    Mode = ToastMode.Default
});
```

**Characteristics:**
- Native OS appearance and behavior
- System-level notifications
- Limited customization options
- Best for critical system messages

### 2. Window Mode

Displays toast notifications within the owning window. Perfect for applications where you want toasts to stay within the application boundaries.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Window Toast",
    Message = "This notification appears within the window",
    Mode = ToastMode.Window,
    Placement = ToastPlacement.BottomRight
});
```

**Characteristics:**
- Constrained to window boundaries
- Full customization support
- Respects window activation state
- Good for application-specific feedback

### 3. Screen Mode

Displays custom toast overlay globally across the screen. Useful for application-wide notifications that should be visible regardless of window focus.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Global Notification",
    Message = "This notification appears globally on screen",
    Mode = ToastMode.Screen,
    Placement = ToastPlacement.TopCenter
});
```

**Characteristics:**
- Global screen-level display
- Full customization capabilities
- Visible regardless of window state
- Best for important application-wide events

## Severity Levels

Toast notifications support multiple severity levels that automatically apply appropriate visual styling.

### Severity Levels Available

| Level | Usage | Visual Style |
|-------|-------|--------------|
| **None** | Default state | Neutral colors |
| **Info** | Informational messages | Blue/Neutral tones |
| **Success** | Successful operations | Green colors |
| **Warning** | Warning messages | Yellow/Orange colors |
| **Error** | Error/failure messages | Red colors |

### Example Usage

```csharp
// Info notification
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Information",
    Message = "Your profile has been updated.",
    Severity = ToastSeverity.Info
});

// Success notification
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Success",
    Message = "File saved successfully!",
    Severity = ToastSeverity.Success
});

// Warning notification
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Warning",
    Message = "You have unsaved changes.",
    Severity = ToastSeverity.Warning
});

// Error notification
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Error",
    Message = "Operation failed. Please try again.",
    Severity = ToastSeverity.Error
});
```

## Toast Variants

The toast control supports three visual variants for different design preferences.

### 1. Text Variant

Minimal, text-only appearance without background fill.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Text Variant",
    Message = "Simple text-only notification",
    Variant = ToastVariant.Text
});
```

### 2. Outlined Variant

Border-based design with emphasis on outline styling.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Outlined Variant",
    Message = "Toast with outlined border",
    Variant = ToastVariant.Outlined
});
```

### 3. Filled Variant

Full-colored background using the accent brush.

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "Filled Variant",
    Message = "Toast with filled background",
    Variant = ToastVariant.Filled,
    AccentBrush = new SolidColorBrush(Colors.Blue)
});
```

## Toast Placement

The control supports nine different placement positions for displaying toasts on screen.

### Available Positions

```
┌─────────────────────────────────────┐
│ TopLeft    TopCenter    TopRight    │
│                                     │
│ LeftCenter                 RightCenter
│                                     │
│ BottomLeft BottomCenter BottomRight │
└─────────────────────────────────────┘
```

### Placement Examples

```csharp
// Top-Left corner
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Top-Left Position",
    Placement = ToastPlacement.TopLeft,
    Mode = ToastMode.Screen
});

// Top-Center
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Top-Center Position",
    Placement = ToastPlacement.TopCenter,
    Mode = ToastMode.Screen
});

// Bottom-Right corner
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Bottom-Right Position",
    Placement = ToastPlacement.BottomRight,
    Mode = ToastMode.Screen
});
```

## Action Buttons

Toast notifications can include interactive action buttons:

### Simple Action Button

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "File Saved",
    Message = "Your document has been saved.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Undo",
            Callback = () => UndoLastSave()
        },
        new ToastAction
        {
            Label = "OK",
            CloseOnClick = true
        }
    }
});

private void UndoLastSave()
{
    // Implement undo logic
}
```

### Action Button with Callback

```csharp
SfToastNotification.Show(this, new ToastOptions
{
    Title = "New Message",
    Message = "You have a new message.",
    Actions = new List<ToastAction>
    {
        new ToastAction
        {
            Label = "Reply",
            Callback = () => OpenReplyWindow(),
            CloseOnClick = true
        },
        new ToastAction
        {
            Label = "Later",
            CloseOnClick = true
        }
    }
});

private void OpenReplyWindow()
{
    // Open reply window
}
```

## Toast Lifecycle

Understanding the lifecycle of a toast helps in managing notifications effectively.

### States

1. **Creation** - Toast is created with ToastOptions
2. **Display** - Toast appears on screen according to placement and mode
3. **Duration** - Toast remains visible for specified duration
4. **Dismissal** - Toast closes via auto-close timeout, close button, or programmatic close

### Managing Toast Lifecycle

```csharp
// Create a toast with custom ID
var options = new ToastOptions
{
    Id = "unique-toast-id",
    Title = "Tracked Toast",
    Message = "This toast can be managed",
    Duration = TimeSpan.FromSeconds(10)
};

SfToastNotification.Show(this, options);

// Manually close specific toast
SfToastNotification.Close("unique-toast-id");

// Close all toasts
SfToastNotification.CloseAll();
```

## Animation Types

Toast notifications support 14+ built-in animations:

```csharp
// Fade animations
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Fade effect",
    ShowAnimationType = ToastAnimation.FadeIn,
    CloseAnimationType = ToastAnimation.FadeOut
});

// Zoom animations
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Zoom effect",
    ShowAnimationType = ToastAnimation.FadeZoomIn,
    CloseAnimationType = ToastAnimation.FadeZoomOut
});

// Slide animations
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Slide effect",
    ShowAnimationType = ToastAnimation.SlideBottomIn,
    CloseAnimationType = ToastAnimation.SlideBottomOut
});

// Flip animations
SfToastNotification.Show(this, new ToastOptions
{
    Message = "Flip effect",
    ShowAnimationType = ToastAnimation.FlipLeftDownIn,
    CloseAnimationType = ToastAnimation.FlipLeftDownOut
});

// No animation
SfToastNotification.Show(this, new ToastOptions
{
    Message = "No animation",
    ShowAnimationType = ToastAnimation.None,
    CloseAnimationType = ToastAnimation.None
});
```

### Available Animations

| Animation | In | Out |
|-----------|----|----|
| **Fade** | FadeIn | FadeOut |
| **Zoom** | FadeZoomIn | FadeZoomOut |
| **Slide** | SlideBottomIn | SlideBottomOut |
| **Flip Left Down** | FlipLeftDownIn | FlipLeftDownOut |
| **Flip Left Up** | FlipLeftUpIn | FlipLeftUpOut |
| **Flip Right Down** | FlipRightDownIn | FlipRightDownOut |
| **None** | None | None |

## Summary

| Concept | Purpose | Key Options |
|---------|---------|------------|
| **Modes** | Where toast appears | Default, Screen, Window |
| **Severity** | Toast importance level | None, Info, Success, Warning, Error |
| **Variants** | Visual styling | Text, Outlined, Filled |
| **Placement** | Screen position | 9 positions available |
| **Actions** | Interactive buttons | Custom labels and callbacks |
| **Animations** | Show/hide effects | 14+ animation types |

Master these core concepts to effectively use Toast Notifications in your applications!
